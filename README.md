# Documentación del proyecto — Turno de Guardacostas

Videojuego 2D de concientización sobre la contaminación marina (ODS 14, 12 y 6, tentativos), desarrollado por Maximiliano García Espinoza y Jonathan Oswaldo Vázquez Moreno.

## Contenido de esta carpeta

| Archivo | Qué contiene |
|---|---|
| `SRS.md` | Especificación de requerimientos: qué debe hacer el juego (introducción, descripción general y requerimientos) |
| `investigacion-srs.md` | Investigación sobre qué es un SRS y la plantilla elegida |
| `uml/casos-de-uso.md` | Diagrama de casos de uso general |
| `uml/diagrama-de-clases.md` | Diagrama de clases del juego |
| `01-…` a `05-…` | Entregables de las actividades de planeación del cronograma |

## Los diagramas UML

Los diagramas están hechos con **Mermaid**, un lenguaje de texto que GitHub dibuja directamente en el navegador, sin programas adicionales. Se eligió porque vive en el repositorio como texto, queda en el historial de Git y los dos integrantes pueden editarlo.

### Diagrama de casos de uso (`uml/casos-de-uso.md`)

Muestra **qué puede hacer el jugador** con el sistema: iniciar partida, seleccionar una herramienta, limpiar plásticos, contener y absorber el hidrocarburo, consultar la salud del mar, leer la ficha educativa y avanzar de nivel. Solo hay un actor, el jugador. Cada caso de uso corresponde a un requerimiento funcional del SRS.

### Diagrama de clases (`uml/diagrama-de-clases.md`)

Muestra **de qué piezas se construye el juego**: `Juego`, `Nivel`, `Barco`, `Residuo` (con `Plastico` e `Hidrocarburo`), `Herramienta` (con `Red`, `BarreraContencion` y `MaterialAbsorbente`), `Jugador`, `SaludDelMar`, `Fauna` y `FichaEducativa`. Cada clase indica sus datos y acciones, y las líneas muestran cómo se relacionan. Como el juego completo es el módulo del equipo, el diagrama cubre todo el juego.

## Cómo se relacionan los documentos

1. Los **requerimientos** (`SRS.md`) dicen qué debe hacer el juego.
2. Los **casos de uso** agrupan los requerimientos funcionales por lo que hace el jugador.
3. El **diagrama de clases** muestra cómo se organizará el código para cumplirlos.

La tabla de trazabilidad de la sección 3.5 del SRS enlaza cada requerimiento con su caso de uso y sus clases.

## Gestión del trabajo

Cada requerimiento funcional (RF-01 a RF-10) es un Issue en este repositorio, con su ID en el título, un responsable y un lugar en el tablero de GitHub Projects "Juego".
