# Arquitectura UML — Turno de Guardacostas

Este documento explica el propósito, la lógica y la relación entre los dos diagramas UML que definen el diseño de **Turno de Guardacostas**: el [Diagrama de Casos de Uso](casos-de-uso.md) y el [Diagrama de Clases](diagrama-de-clases.md).

---

## 1. Visión General: ¿Cómo se conectan ambos diagramas?

Ambos modelos representan las dos caras del mismo sistema:

* **El qué (Comportamiento):** El [Diagrama de Casos de Uso](casos-de-uso.md) define el alcance funcional desde la perspectiva externa. Responde a la pregunta: *¿Qué puede hacer el usuario con el juego?*
* **El cómo (Estructura):** El [Diagrama de Clases](diagrama-de-clases.md) traduce esas interacciones en una arquitectura interna de software orientada a objetos. Responde a la pregunta: *¿Qué piezas de código existen y cómo colaboran para hacer posible lo anterior?*

---

## 2. Explicación del Diagrama de Casos de Uso (`casos-de-uso.md`)

Este diagrama delimita la frontera entre el usuario y el sistema:

* **Un único actor (`Jugador`):** No existen roles secundarios, administradores ni sistemas externos. Toda la interacción parte de una sola persona.
* **Dependencias obligatorias (`<<include>>`):** El diagrama establece reglas de flujo estrictas. Ninguna acción de limpieza (`Limpiar plástico`, `Contener mancha`, `Absorber hidrocarburo`) puede ejecutarse de forma aislada; todas dependen obligatoriamente de haber ejecutado antes `Seleccionar herramienta`. De igual forma, `Avanzar de nivel` fuerza siempre la ejecución de `Leer ficha educativa`.
* **Frontera del sistema (Lo que queda fuera):** El diagrama excluye deliberadamente procesos como la generación de basura por los barcos, el cálculo de penalizaciones o el comportamiento de la fauna. En UML, los casos de uso solo modelan acciones iniciadas por un actor o que le devuelven un valor directo; los procesos internos autónomos pertenecen a la lógica del motor.

---

## 3. Explicación del Diagrama de Clases (`diagrama-de-clases.md`)

Este diagrama modela la estructura estática del código y cómo se materializan los casos de uso en entidades de software:

* **Núcleo y ciclo de vida (Composición `*--`):** La clase `Juego` actúa como el controlador central. Posee una relación de composición fuerte con exactamente `3` instancias de `Nivel` y `1` de `SaludDelMar`. Si la partida se destruye, estos elementos desaparecen con ella.
* **Polimorfismo y extensibilidad (Herencia `<|--`):** 
  * **`Residuo`:** Define el contrato base (posición y verificación de limpieza) del cual heredan `Plastico` e `Hidrocarburo`. Esto permite que el sistema trate a ambos como amenazas genéricas, pero delegue sus comportamientos únicos (por ejemplo, solo el hidrocarburo puede expandirse o ser contenido).
  * **`Herramienta`:** Abstrae las acciones de limpieza. `Jugador` tiene acceso a `3` herramientas y las aplica sobre cualquier `Residuo` sin necesidad de conocer su implementación interna.
* **Desacoplamiento por diseño:**
  * **Control de derrota:** `SaludDelMar` centraliza el estado vital del océano, evitando que la lógica de fin de juego quede repartida entre los niveles o los residuos.
  * **Bajo acoplamiento visual:** `Fauna` observa a `SaludDelMar` en una sola dirección (`-->`). La salud del mar no sabe que la fauna existe, lo que permite modificar o eliminar los elementos visuales del ecosistema sin romper la mecánica principal del juego.
* **Objetos dinámicos (Agregación `o--`):** Un `Nivel` agrupa múltiples instancias de `Barco`, los cuales a su vez instancian y sueltan objetos `Residuo` en tiempo de ejecución.

---

## 4. Trazabilidad entre Diagramas

| Acción en Casos de Uso | Materialización en el Diagrama de Clases |
| :--- | :--- |
| **Iniciar / Avanzar de nivel** | `Juego` gestiona el cambio de estado mediante `iniciar()` y `avanzarNivel()`, coordinando las instancias de `Nivel` y disparando `FichaEducativa.mostrar()`. |
| **Seleccionar herramienta** | `Jugador` actualiza su atributo `herramientaActiva` eligiendo entre `Red`, `BarreraContencion` o `MaterialAbsorbente`. |
| **Limpiar / Contener / Absorber** | `Jugador.usarHerramienta(residuo)` delega la acción a `Herramienta.usar(residuo)`, ejecutando `esLimpiadoPor()` en `Plastico` o métodos específicos como `contener()` y `reducir()` en `Hidrocarburo`. |
| **Consultar salud del mar** | Lectura del estado de `SaludDelMar`, el cual se modifica mediante `disminuir()` o `recuperar()` y notifica indirectamente a `Fauna.actualizar(salud)`. |
