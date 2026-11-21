# Actividad 7 — Investigación de referentes y herramientas

**Responsable:** Maximiliano García Espinoza
**Periodo estimado:** 11/11 – 17/11 | **Periodo real:** 18/11/2026 – 20/11/2026
**Proyecto:** Turno de Guardacostas (`docs/05-matriz-evaluacion.md`)

---

## Parte 1 — Referentes

Se buscaron juegos y recursos educativos sobre contaminación marina, con mecánicas parecidas a las de Turno de Guardacostas (clic para limpiar, residuos en el mar, mensaje educativo).

### 1. Dumb Ways to Kill the Ocean

- **Qué es:** juego web que muestra tres problemas del océano: plástico, calentamiento y degradación del coral.
- **Mecánica:** en el primer minijuego el jugador tiene 20 segundos para "agarrar" la mayor cantidad de plástico haciendo clic en los desechos. Los siguientes minijuegos son un acertijo de palabras y colorear coral.
- **Parte educativa:** se completa en menos de un minuto y busca educar más que dar la posibilidad de ganar o perder.
- **Qué tomamos:** el clic como única interacción y el tiempo limitado.
- **Qué evitamos:** que no haya consecuencias ni progresión; nuestro juego sí tiene salud del mar, derrota y niveles.
- **Fuente:** artículo de National Geographic sobre el juego. Sarah Gibbens | 19 Jun 2018

### 2. Nurdle Minigame (Wilson Center, Serious Games Initiative)

- **Qué es:** minijuego del Wilson Center sobre microplásticos.
- **Mecánica:** un barco de carga pierde cajas en el camino a una fábrica de productos plásticos y se sueltan pellets de plástico (*nurdles*). El jugador debe salvar a la vida marina de la contaminación con acciones rápidas, atrapando los pellets con una red.
- **Parte educativa:** el texto del juego señala que la única forma efectiva de combatir los microplásticos es detenerlos en la fuente, no limpiar después.
- **Qué tomamos:** es el referente más cercano a nuestra premisa (barco, carga perdida, red, vida marina) y su mensaje conecta con el ODS 12.
- **Qué evitamos:** limitarnos a una sola herramienta.
- **Fuente:** página "About the Nurdle Minigame", Wilson Center.

### 3. Plastic Dive (n0mad-d3v)

- **Qué es:** juego de código abierto en el que el jugador es un buzo que recoge plástico del océano.
- **Mecánica:** recolectar desechos en entornos submarinos, con mejoras para el buzo y tabla de puntuaciones.
- **Parte educativa:** tutorial en el primer inicio, una pantalla de información ("Infocean") sobre la contaminación por plástico y los animales, y consejos reales que se desbloquean al avanzar.
- **Tecnología:** Flutter con Flame, según el repositorio.
- **Qué tomamos:** el tutorial inicial y la pantalla de información como parte del juego.
- **Qué evitamos:** las mejoras y la tabla de puntuaciones (fuera de nuestro alcance).
- **Fuente:** repositorio del juego en GitHub.

### 4. Ocean Odyssey: Tracking Marine Debris (NOAA)

- **Qué es:** juego educativo de la agencia oceánica de Estados Unidos, para estudiantes de 5.º a 8.º grado, de unos 20 minutos.
- **Mecánica:** el jugador elige entre 15 ubicaciones del mundo y sigue hacia dónde llega la basura en el océano, usando datos reales.
- **Parte educativa:** explica qué son las corrientes superficiales y por qué existen los "parches de basura" en los giros oceánicos.
- **Qué tomamos:** apoyarse en datos reales de una fuente oficial, como haremos con las fichas.
- **Qué evitamos:** una exploración tan abierta; es más de lo que podemos construir.
- **Fuente:** página del juego en NOAA (NESDIS).

### 5. Estudio sobre un juego serio para la alfabetización oceánica (Cambridge)

- **Qué es:** artículo académico que presenta un juego sobre el océano y evalúa su uso en tres sesiones con estudiantes de preparatoria en Noruega.
- **Por qué importa:** argumenta que los juegos serios pueden ayudar a que el público conozca el océano y que ofrecen una experiencia inmersiva e interactiva que la enseñanza tradicional puede no dar. Respalda la decisión de enseñar mediante un juego.
- **Qué tomamos:** su justificación del enfoque educativo.
- **Fuente:** artículo en Cambridge Core. Rachel Tiller, Ina Helene Ahlquist, Håvard Almås, Emily Cowan, Dorothy Dankel and Magnus Hakvåg. 22 November 2024. *Ocean literacy and how serious games can play a part: the case of the jellyfish and the microplastics governance game MoreGoJelly!*.

### Resumen de lo aprendido

| Referente | Mecánica | Parte educativa | Relevancia para nuestro juego |
|---|---|---|---|
| Dumb Ways to Kill the Ocean | Clic en plástico con tiempo límite | Muy breve | Media: confirma que el clic basta |
| Nurdle Minigame | Atrapar pellets con una red | Mensaje sobre detener en la fuente | Alta: premisa casi idéntica |
| Plastic Dive | Recolectar bajo el agua, con mejoras | Tutorial y pantalla de información | Alta: estructura educativa |
| Ocean Odyssey | Seguir la basura con datos reales | Corrientes y parches de basura | Media: uso de datos oficiales |
| Estudio de Cambridge | (artículo) | Evalúa un juego serio | Media: respaldo académico |

**Conclusiones:**
- Los juegos de este tipo se pueden construir con una sola interacción, el clic.
- Los mejores combinan la acción con un mensaje educativo corto (ficha, pantalla de información o mensaje final).
- Ninguno de los referentes encontrados combina varias herramientas según el tipo de residuo, y esa es la parte que distingue a Turno de Guardacostas.

---

## Parte 2 — Herramientas

Se comparan dos opciones para construir un juego 2D de clic.

### Comparación

| Aspecto | Pygame-ce (Python) | Godot (GDScript) |
|---|---|---|
| Qué es | Biblioteca de Python: el programa es el juego y se escribe el bucle, el dibujo y las colisiones | Motor con editor: se arman escenas con nodos y el motor se encarga del bucle y el dibujo |
| Lenguaje | Python | GDScript, parecido a Python (también admite C#) |
| Interfaz (botones, barras, mensajes) | Se programa a mano | Se arma en el editor |
| Curva de aprendizaje | Baja si ya se sabe Python; enseña los fundamentos | Hay que aprender el editor y GDScript; quienes saben Python suelen aprenderlo en unos días |
| Instalación | `pip install pygame-ce` | Un solo programa de unos 100 MB |
| Publicación | Escritorio (con una herramienta de empaquetado) | Windows, macOS, Linux, Android, iOS y web desde el editor |
| Licencia | Gratuita (LGPL) | Gratuita (MIT) |

### Encaje con los requerimientos del SRS

| Requerimiento | Pygame-ce | Godot |
|---|---|---|
| RNF-03: ejecutar en Windows y Linux | Sí, es Python | Sí, se exporta a ambos |
| RNF-04: otra persona ejecuta el juego con el README en 15 minutos | Instalar Python y `pip install` | Abrir el proyecto o usar un ejecutable exportado |
| RNF-02: 30 FPS o más | Un juego 2D con pocos objetos debería lograrlo | Igual |
| Diagrama de clases (`docs/uml/`) | Las clases del diagrama se escriben casi tal cual en Python | Se pueden representar con scripts y nodos |

### Experiencia del equipo

| Integrante | Python | Godot / GDScript | Otras herramientas |
|---|---|---|---|
| Maximiliano García Espinoza | Fundamentos y librerias basicas | Sin experiencia | Cosas básicas en C |
| Jonathan Oswaldo Vázquez Moreno | Fundamentos | Sin experiencia | Cosas básicas en C |

---

## Referencias

Completar con todos los datos de cada fuente al abrirla. Se agregan las fuentes oficiales de las herramientas.

- National Geographic. (19 jun 2018. *Nuevo juego llama a limpiar el plástico de los océanos*. https://www.nationalgeographicla.com/planeta-o-plastico/2018/06/nuevo-juego-llama-a-limpiar-el-plastico-de-los-oceanos
- Wilson Center. (s. f.). *About the nurdle minigame*. https://www.wilsoncenter.org/article/about-nurdle-minigame
- n0mad-d3v. (s. f.). *Plastic Dive*. GitHub. https://www.github.com/n0mad-d3v/plastic-dive
- National Oceanic and Atmospheric Administration. (s. f.). *Ocean Odyssey: Tracking marine debris*. https://www.nesdis.noaa.gov/node/18531
- [Rachel Tiller, Ina Helene Ahlquist, Håvard Almås, Emily Cowan, Dorothy Dankel and Magnus Hakvåg]. (22 November 2024). *Ocean literacy and how serious games can play a part: the case of the jellyfish and the microplastics governance game MoreGoJelly!*. Cambridge University Press. https://www.cambridge.org/core/product/791665766D298B255F9D3FA832851A9A
- https://pyga.me/docs/
- https://docs.godotengine.org/en/stable/about/introduction.html
