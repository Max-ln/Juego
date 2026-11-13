# Actividad 4 — Lluvia de ideas de proyectos alternativos

**Responsables:** Maximiliano García Espinoza y Jonathan Oswaldo Vázquez Moreno
**Periodo estimado:** 04/11 – 06/11 | **Periodo real:** 10/11/ – 12/11
**Antecedente:** `docs/03-informe-viabilidad.md` descartó el alcance completo del proyecto inicial. Aquí se proponen cinco alternativas, una de ellas la versión reducida de ese proyecto.

## Cómo se desarrolló cada propuesta

Cada propuesta tiene: premisa, cómo se juega, reglas de ganar y perder, parte educativa, ODS, esfuerzo aproximado y lo que se deja fuera. El esfuerzo se mide en puntos de historia (SP), con el mismo criterio de la Actividad 2, y se confirma en la Actividad 12. La evaluación se hace en `docs/05-matriz-evaluacion.md`.

---

## Propuesta 1 — Turno de Guardacostas

**Premisa:** vista fija del mar. Por el horizonte pasan barcos y de vez en cuando uno deja caer basura o hidrocarburo. El jugador es el equipo de respuesta de la costa.

**Cómo se juega:** todo con el mouse, sin movimiento del jugador ni físicas. Cada residuo requiere su herramienta, inspirada en las que se usan en la vida real (se verificaran en las Actividades 6 y 7):
- **Plásticos y basura sólida:** se recogen con una *red*, haciendo clic.
- **Mancha de hidrocarburo:** crece con el tiempo. Una *barrera de contención* frena su expansión unos segundos, y un *material absorbente* la reduce con varios clics.
- **Herramienta equivocada:** se pierde tiempo y aparece un mensaje que explica por qué no funciona.

**Reglas:** una barra de "salud del mar" baja con cada residuo sin limpiar. Si llega a cero, se pierde. Si el jugador aguanta la duración del nivel, gana. Los peces y las tortugas que aparecen en pantalla disminuyen o regresan según la salud del mar.

**Niveles:** el 1 solo trae plástico, el 2 suma manchas de petróleo y el 3 pone más barcos al mismo tiempo.

**Parte educativa:** tras cada nivel, una ficha con un dato real sobre contaminación marina, con fuente (se investigara en la Actividad 6).

**ODS tentativos:** 14 (vida submarina), 12 (producción y consumo responsables) y 6 (agua limpia y saneamiento).
**Esfuerzo aproximado:** 20 SP. Lo más difícil es la mancha que crece y la barrera.
**Se deja fuera:** movimiento del jugador, mejoras con dinero, dispersantes y varios tipos de barcos.

---

## Propuesta 2 — Ruta del Agua

**Premisa:** una comunidad no tiene agua limpia. En una cuadrícula, el jugador coloca y gira piezas de tubería para llevar el agua de la fuente a las casas.

**Cómo se juega:** clic para girar cada pieza. Hay obstáculos: zonas contaminadas por las que no se puede pasar y piezas con filtro que hay que usar bien. Cada nivel tiene un número limitado de movimientos.

**Reglas:** se gana al conectar todas las casas dentro del límite de movimientos; se pierde si se acaban.

**Parte educativa:** cada casa conectada muestra una frase breve sobre qué cambia en la salud y la vida de esa familia.

**ODS tentativos:** 6 (agua limpia y saneamiento), 3 (salud y bienestar) y 11 (ciudades y comunidades sostenibles).
**Esfuerzo aproximado:** 15 SP, con matriz 2D y eventos de clic.
**Se deja fuera:** animaciones complejas, mapa grande y editor de niveles.

---

## Propuesta 3 — Casa Eficiente

**Premisa:** una casa vista en corte, con varias habitaciones. Cada aparato encendido sube un medidor de consumo.

**Cómo se juega:** con presupuesto limitado, el jugador hace clic para apagar lo que no se usa y cambiar aparatos viejos por eficientes. Cada "mes" (cada nivel) se ve el recibo.

**Reglas:** se gana si el recibo queda por debajo de una meta; se pierde si se pasa o si se deja sin servicio a la familia (hay aparatos que no se deben apagar, como el refrigerador).

**Parte educativa:** al terminar cada mes, un resumen compara las decisiones del jugador con las mejores posibles. Los valores de consumo deben verificarse con una fuente real, como la CFE, y no inventarse.

**ODS tentativos:** 7 (energía asequible y no contaminante), 12 (producción y consumo responsables) y 13 (acción por el clima).
**Esfuerzo aproximado:** 15 SP.
**Se deja fuera:** muchas habitaciones, ciclo de día y noche, y tienda.

---

## Propuesta 4 — Tianguis sin Desperdicio

**Premisa:** el jugador atiende un puesto de frutas y verduras en un tianguis. Los alimentos tienen una barra de frescura que baja con el tiempo.

**Cómo se juega:** llegan clientes. Para cada producto, el jugador decide con un clic: vender, donar al banco de alimentos o llevar a composta, antes de que se eche a perder.

**Reglas:** se ganan puntos por vender, donar y compostar bien, y se pierden si algo se desperdicia. La partida dura un número fijo de clientes.

**Parte educativa:** una ficha por nivel sobre desperdicio de alimentos y qué hacer con lo que sobra.

**ODS tentativos:** 2 (hambre cero), 12 (producción y consumo responsables) y 13 (acción por el clima).
**Esfuerzo aproximado:** 17 SP.
**Se deja fuera:** mapa, varios puestos y economía de precios.

---

## Propuesta 5 — Aldea Despierta (versión reducida de "Reconstrucción de la civilización")

**Premisa:** el proyecto inicial, reducido a lo esencial. Una aldea pequeña, vista en una sola pantalla, donde el jugador cultiva alimento, despierta a los habitantes y los organiza para que la comunidad recupere el ánimo.

**Mecánicas que se conservan del inventario (`docs/02-inventario-proyecto-inicial.md`):**
- **1.1 Siembra, riego y cosecha (5 SP):** un huerto con ciclos de crecimiento simples.
- **2.3 Asignación de vocaciones (3 SP):** los habitantes "despertados" se asignan a un rol (agricultor, médico u otro). Se despiertan por eventos fijos al alcanzar cierta cantidad de alimento, sin explorar un mapa.
- **3.2 Medidor de moral y salud comunitaria (5 SP):** una barra global que sube o baja según los alimentos y los roles asignados.

**Reglas:** se gana al llevar la moral a la meta en un número fijo de días de juego; se pierde si la moral llega a cero.

**Parte educativa:** una ficha por nivel sobre seguridad alimentaria y salud comunitaria.

**ODS tentativos:** 2 (hambre cero), 3 (salud y bienestar) y 11 (ciudades y comunidades sostenibles).
**Esfuerzo aproximado:** 13 SP según el inventario. Pero las tres mecánicas dependen entre sí (la moral depende de la comida y de los roles), así que ajustar el balance puede costar más de lo que sugiere esa cifra.
**Se deja fuera:** ganado, suministros sustentables, crafteo, exploración y rescate, diagnóstico de salud, restauración de edificios y economía de trueque.

---

## Comparación rápida

| Propuesta | Mecánica central | Esfuerzo aprox. | Riesgo principal |
|---|---|---|---|
| 1. Turno de Guardacostas | Elegir la herramienta correcta y hacer clic | 20 SP | La mancha que crece y la barrera |
| 2. Ruta del Agua | Girar piezas en una cuadrícula | 15 SP | Diseñar niveles que se puedan resolver |
| 3. Casa Eficiente | Apagar y mejorar aparatos | 15 SP | Conseguir datos reales de consumo |
| 4. Tianguis sin Desperdicio | Decidir qué hacer con cada producto | 17 SP | Que se vuelva repetitivo |
| 5. Aldea Despierta | Cultivar, asignar roles y mantener la moral | 13 SP | Balance entre sistemas dependientes |

## Ideas previas (sin desarrollar)

Se conservan como referencia: Defensor de la Cosecha, Recolector Contrarreloj, Plataformero de Evasión, Simulador de Decisiones en Consola, Rompecabezas de Conciencia Ambiental y Marea Limpia: Crisis de Contenedores.

## Siguiente paso

Actividad 5: evaluar estas cinco propuestas con una matriz de criterios y elegir una (`docs/05-matriz-evaluacion.md`).
