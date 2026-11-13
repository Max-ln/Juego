# Especificación de Requerimientos de Software (SRS)

## Turno de Guardacostas

| | |
|---|---|
| **Versión** | 1.0 (borrador) |
| **Fecha** | 13 de noviembre de 2026 |
| **Autores** | Maximiliano García Espinoza y Jonathan Oswaldo Vázquez Moreno |
| **Plantilla** | Estructura de IEEE 830 (secciones 1 a 3), ver `investigacion-srs.md` |

Los valores marcados como **[propuesto]** son cifras iniciales que el equipo debe confirmar en las Actividades 8 y 9. Lo marcado como **[COMPLETAR]** depende de decisiones que aún no se toman.

---

## 1. Introducción

### 1.1 Propósito

Este documento especifica qué debe hacer el videojuego "Turno de Guardacostas" (nombre provisional) para que el equipo de desarrollo y quienes lo evalúen compartan la misma idea del producto antes de construirlo. Está dirigido a los dos integrantes del equipo y al profesor de la materia.

### 1.2 Alcance

**El producto** es un videojuego 2D de escritorio, jugado con el mouse, cuyo objetivo es concientizar sobre la contaminación marina (ODS 14, 12 y 6, tentativos). El jugador vigila una vista fija del mar por la que pasan barcos que sueltan residuos; debe limpiarlos con la herramienta adecuada antes de que la "salud del mar" llegue a cero.

**El producto sí incluye:**
- Una vista fija del mar con barcos que pasan y sueltan residuos.
- Tres herramientas: red, barrera de contención y material absorbente.
- Dos tipos de residuo: plásticos y una mancha de hidrocarburo que crece con el tiempo.
- Una barra de salud del mar con condiciones de ganar y perder.
- Fauna (peces y tortugas) que refleja el estado del mar.
- Tres niveles, con una ficha educativa al terminar cada uno.

**El producto no incluye (por ahora):**
- Movimiento del jugador ni físicas.
- Mejoras con dinero ni economía.
- Dispersantes ni nubes químicas.
- Varios tipos de barcos.
- Multijugador, guardado de partida ni conexión a internet.

### 1.3 Definiciones, siglas y abreviaturas

| Término | Significado |
|---|---|
| SRS / ERS | Especificación de Requerimientos de Software: documento que describe lo que debe hacer un sistema |
| RF | Requerimiento funcional: algo que el sistema debe hacer |
| RNF | Requerimiento no funcional: una cualidad que el sistema debe tener (rendimiento, usabilidad, etc.) |
| ODS | Objetivos de Desarrollo Sostenible de la ONU |
| Residuo | Objeto contaminante que aparece en el mar: plástico o hidrocarburo |
| Hidrocarburo | Mancha de petróleo que se expande con el tiempo si no se contiene |
| Red | Herramienta que recoge plásticos y basura sólida |
| Barrera de contención | Herramienta que detiene temporalmente la expansión de una mancha de hidrocarburo |
| Material absorbente | Herramienta que reduce el tamaño de una mancha de hidrocarburo |
| Salud del mar | Barra de 0 a 100 que baja mientras haya residuos sin limpiar |
| Ficha educativa | Pantalla con un dato real sobre contaminación marina y su fuente, que se muestra al terminar un nivel |
| Nivel | Partida de duración fija con cierto tipo y cantidad de residuos |

### 1.4 Referencias

Las referencias en formato APA 7 se registran en `investigacion-srs.md`. [COMPLETAR]

### 1.5 Visión general del documento

La sección 2 describe el producto en general (usuarios, restricciones y supuestos). La sección 3 detalla los requerimientos funcionales y no funcionales, cada uno en una ficha con ID, título, descripción, prioridad y criterio de aceptación. Los diagramas UML están en `docs/uml/`.

---

## 2. Descripción general

### 2.1 Perspectiva del producto

Es un producto independiente. No se conecta con otros sistemas ni requiere internet. Se ejecuta de forma local en una computadora de escritorio.

### 2.2 Funciones del producto (resumen)

- Mostrar el mar y generar residuos que sueltan los barcos.
- Permitir elegir una herramienta y usarla con clics del mouse.
- Retroalimentar al jugador cuando usa la herramienta equivocada.
- Llevar la cuenta de la salud del mar y decidir si se gana o se pierde.
- Mostrar una ficha educativa al terminar cada nivel.

### 2.3 Usuarios

| Usuario | Descripción | Conocimientos previos |
|---|---|---|
| Jugador | Estudiante o público general interesado en un juego corto con tema ambiental. Rango de edad: [COMPLETAR] | Ninguno sobre contaminación marina; sabe usar mouse |

No hay administradores ni usuarios registrados.

### 2.4 Restricciones

- El equipo es de dos personas, sin experiencia previa en proyectos de este tamaño.
- El plazo y las horas disponibles son limitados; el alcance se acota al de la sección 1.2.
- Los recursos gráficos y de sonido deben ser propios o de licencia libre.
- El juego se controla solo con el mouse.
- Tecnología de desarrollo: [COMPLETAR, se define en la Actividad 7].
- Los datos de las fichas educativas deben provenir de fuentes verificables.

### 2.5 Supuestos y dependencias

- Se asume que los jugadores tienen una computadora de escritorio o portátil con mouse.
- Las herramientas de respuesta a derrames del juego están inspiradas en las reales; se verifican en las Actividades 6 y 7.
- La duración de los niveles, la cantidad de barcos y las cifras de los criterios de aceptación son valores iniciales y pueden cambiar tras las pruebas.
- Los ODS finales se confirman en la Actividad 6.

---

## 3. Requisitos específicos

### 3.1 Interfaces externas

- **Interfaz de usuario:** una sola ventana con la escena del mar, una barra de herramientas, la barra de salud del mar, el puntaje y el tiempo restante.
- **Dispositivo de entrada:** mouse (clic izquierdo).
- **Salida:** pantalla y, opcionalmente, sonido.

### 3.2 Requerimientos funcionales

Prioridad: **Alta** (sin esto el juego no funciona), **Media** (importante), **Baja** (deseable).

---

#### RF-01 — Iniciar partida

- **Descripción:** el sistema muestra un menú principal con la opción "Jugar". Al seleccionarla, comienza el nivel 1.
- **Prioridad:** Alta
- **Criterio de aceptación:** al hacer clic en "Jugar" desde el menú principal, aparece el nivel 1 en menos de 3 segundos **[propuesto]** y el tiempo del nivel empieza a correr.

#### RF-02 — Generar residuos desde los barcos

- **Descripción:** durante el nivel, los barcos cruzan la escena y sueltan residuos en el mar a intervalos definidos por el nivel. Los residuos pueden ser plásticos o hidrocarburo.
- **Prioridad:** Alta
- **Criterio de aceptación:** en el nivel 1 aparece un barco cada 10 segundos **[propuesto]** y cada barco suelta al menos un residuo visible; en el nivel 1 solo aparecen plásticos.

#### RF-03 — Seleccionar herramienta

- **Descripción:** el jugador elige una de las tres herramientas (red, barrera de contención, material absorbente) haciendo clic en su botón de la barra de herramientas. La herramienta elegida queda resaltada.
- **Prioridad:** Alta
- **Criterio de aceptación:** al hacer clic en un botón, ese botón queda resaltado y los demás no; el siguiente clic sobre un residuo usa la herramienta resaltada.

#### RF-04 — Recoger plásticos con la red

- **Descripción:** con la red seleccionada, un clic sobre un residuo plástico lo elimina de la escena y suma puntos.
- **Prioridad:** Alta
- **Criterio de aceptación:** al hacer clic con la red sobre un plástico, este desaparece y el puntaje aumenta en 10 puntos **[propuesto]**.

#### RF-05 — Contener y absorber hidrocarburo

- **Descripción:** una mancha de hidrocarburo crece con el tiempo. Con la barrera de contención, un clic sobre la mancha detiene su crecimiento durante un tiempo limitado. Con el material absorbente, cada clic sobre la mancha reduce su tamaño; al llegar a cero, desaparece y suma puntos.
- **Prioridad:** Alta
- **Criterio de aceptación:** sin barrera, el diámetro de la mancha aumenta con el tiempo; tras usar la barrera, no crece durante 8 segundos **[propuesto]**; cada clic con el absorbente reduce su tamaño en 20 % **[propuesto]**; al llegar a 0 % la mancha desaparece.

#### RF-06 — Penalizar el uso de la herramienta incorrecta

- **Descripción:** si el jugador usa una herramienta que no corresponde al residuo (por ejemplo, la red sobre el hidrocarburo), el sistema le resta tiempo y muestra un mensaje breve que explica por qué esa herramienta no sirve.
- **Prioridad:** Media
- **Criterio de aceptación:** al hacer clic con la red sobre una mancha de hidrocarburo, el residuo no cambia, se descuentan 3 segundos al tiempo del nivel **[propuesto]** y aparece un mensaje de una frase durante 3 segundos.

#### RF-07 — Salud del mar y fin de partida

- **Descripción:** una barra de salud del mar (0 a 100) baja mientras haya residuos sin limpiar. Si llega a 0, el jugador pierde. Si el tiempo del nivel termina con la salud mayor que 0, gana el nivel.
- **Prioridad:** Alta
- **Criterio de aceptación:** con residuos en pantalla la barra disminuye con el tiempo; al llegar a 0 aparece la pantalla de derrota; al terminar el tiempo con la barra mayor que 0 aparece la pantalla de victoria del nivel.

#### RF-08 — Ficha educativa al terminar cada nivel

- **Descripción:** tras ganar un nivel, el sistema muestra una ficha con un dato real sobre contaminación marina y su fuente.
- **Prioridad:** Alta
- **Criterio de aceptación:** al ganar los niveles 1, 2 y 3 se muestra una ficha distinta, cada una con un texto y una fuente identificable, y el jugador debe pulsar "Continuar" para avanzar.

#### RF-09 — Progresión de niveles

- **Descripción:** el juego tiene tres niveles. El nivel 1 solo trae plásticos, el 2 suma manchas de hidrocarburo y el 3 aumenta la cantidad de barcos. Al ganar un nivel y cerrar su ficha, comienza el siguiente; al ganar el nivel 3, se muestra la pantalla final con el puntaje total.
- **Prioridad:** Alta
- **Criterio de aceptación:** el nivel 2 contiene al menos una mancha de hidrocarburo; el nivel 3 tiene el doble de barcos que el nivel 1 **[propuesto]**; tras ganar el nivel 3 aparece el puntaje total.

#### RF-10 — Fauna que refleja la salud del mar

- **Descripción:** peces y tortugas aparecen en la escena. Su cantidad visible disminuye cuando la salud del mar baja y aumenta cuando se recupera.
- **Prioridad:** Baja
- **Criterio de aceptación:** con la salud del mar por debajo de 50 %, hay menos animales visibles que con la salud por encima de 80 % **[propuesto]**.

---

### 3.3 Requerimientos no funcionales

#### RNF-01 — Usabilidad

- **Descripción:** el juego debe poder aprenderse sin ayuda externa. Una pantalla de instrucciones previa al nivel 1 explica las tres herramientas y el objetivo.
- **Prioridad:** Alta
- **Criterio de aceptación:** al menos 4 de 5 personas que no conocen el juego completan el nivel 1 sin ayuda de los desarrolladores después de leer la pantalla de instrucciones **[propuesto]**.

#### RNF-02 — Rendimiento

- **Descripción:** el juego debe verse fluido en las computadoras de los integrantes.
- **Prioridad:** Media
- **Criterio de aceptación:** con la mayor cantidad de residuos y barcos del nivel 3, la tasa de cuadros se mantiene en 30 FPS o más **[propuesto]** en la computadora de cada integrante, medida con un contador de FPS.

#### RNF-03 — Portabilidad

- **Descripción:** el juego debe ejecutarse en los sistemas operativos que usan los integrantes del equipo.
- **Prioridad:** Media
- **Criterio de aceptación:** el juego se ejecuta y se puede completar el nivel 1 en Windows y en Linux **[propuesto, confirmar sistemas del equipo]**.

#### RNF-04 — Mantenibilidad y documentación

- **Descripción:** el código y las instrucciones de ejecución deben estar en el repositorio de GitHub, de forma que otra persona pueda ejecutarlo.
- **Prioridad:** Media
- **Criterio de aceptación:** una persona ajena al equipo, siguiendo solo el README, logra ejecutar el juego en menos de 15 minutos **[propuesto]** sin ayuda.

#### RNF-05 — Veracidad del contenido educativo

- **Descripción:** todo dato mostrado en una ficha educativa debe poder comprobarse en una fuente confiable.
- **Prioridad:** Alta
- **Criterio de aceptación:** cada ficha tiene registrada su fuente en formato APA 7 en `docs/`, y esa fuente contiene el dato mostrado.

---

### 3.4 Revisión con el checklist

Cada requerimiento debe cumplir los seis criterios. **El equipo debe revisar cada fila y marcarla** (☐ → ✅) cuando los dos estén de acuerdo.

| ID | Correcto | No ambiguo | Completo | Consistente | Factible | Verificable |
|---|---|---|---|---|---|---|
| RF-01 | ☐ | ☐ | ☐ | ☐ | ☐ | ☐ |
| RF-02 | ☐ | ☐ | ☐ | ☐ | ☐ | ☐ |
| RF-03 | ☐ | ☐ | ☐ | ☐ | ☐ | ☐ |
| RF-04 | ☐ | ☐ | ☐ | ☐ | ☐ | ☐ |
| RF-05 | ☐ | ☐ | ☐ | ☐ | ☐ | ☐ |
| RF-06 | ☐ | ☐ | ☐ | ☐ | ☐ | ☐ |
| RF-07 | ☐ | ☐ | ☐ | ☐ | ☐ | ☐ |
| RF-08 | ☐ | ☐ | ☐ | ☐ | ☐ | ☐ |
| RF-09 | ☐ | ☐ | ☐ | ☐ | ☐ | ☐ |
| RF-10 | ☐ | ☐ | ☐ | ☐ | ☐ | ☐ |
| RNF-01 | ☐ | ☐ | ☐ | ☐ | ☐ | ☐ |
| RNF-02 | ☐ | ☐ | ☐ | ☐ | ☐ | ☐ |
| RNF-03 | ☐ | ☐ | ☐ | ☐ | ☐ | ☐ |
| RNF-04 | ☐ | ☐ | ☐ | ☐ | ☐ | ☐ |
| RNF-05 | ☐ | ☐ | ☐ | ☐ | ☐ | ☐ |

### 3.5 Trazabilidad con los diagramas UML

| Requerimiento | Caso de uso (`docs/uml/casos-de-uso.md`) | Clases principales (`docs/uml/diagrama-de-clases.md`) |
|---|---|---|
| RF-01 | Iniciar partida | Juego, Nivel |
| RF-02 | (automático, lo hace el sistema) | Barco, Residuo, Plastico, Hidrocarburo |
| RF-03 | Seleccionar herramienta | Jugador, Herramienta |
| RF-04 | Limpiar plástico con la red | Red, Plastico |
| RF-05 | Contener mancha, Absorber hidrocarburo | BarreraContencion, MaterialAbsorbente, Hidrocarburo |
| RF-06 | (reacción a un uso incorrecto) | Herramienta, Residuo |
| RF-07 | Consultar salud del mar | SaludDelMar, Juego |
| RF-08 | Leer ficha educativa | FichaEducativa, Nivel |
| RF-09 | Avanzar de nivel | Juego, Nivel |
| RF-10 | (automático, lo hace el sistema) | Fauna, SaludDelMar |
