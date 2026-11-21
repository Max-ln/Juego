# Actividad 8 — Definición del concepto del juego

**Responsables:** Maximiliano García Espinoza y Jonathan Oswaldo Vázquez Moreno
**Periodo estimado:** 18/11 – 19/11 | **Periodo real:** 19/11 – 20/11
**Insumos:** `docs/05-matriz-evaluacion.md`, `docs/06-seleccion-de-ods.md`, `docs/07-referentes-y-herramientas.md` y `docs/SRS.md`

---

## 1. Resumen del concepto

*Turno de Guardacostas* es un juego 2D de clic en el que el jugador es el equipo de respuesta de una bahía. Desde una vista fija del mar, ve pasar barcos que sueltan plásticos y manchas de hidrocarburo, y debe limpiarlos con la herramienta correcta antes de que la salud del mar llegue a cero. Al terminar cada turno (nivel), una ficha le muestra un dato real sobre la contaminación marina.

## 2. Nombre

Nombre provisional: **Turno de Guardacostas**. Cada nivel es un "turno" de trabajo, lo que conecta el nombre con la mecánica.

## 3. De qué trata

**Premisa:** una bahía con tráfico marítimo. Los barcos pasan por el horizonte y, de vez en cuando, uno deja caer residuos al agua. El jugador es el equipo de guardacostas de turno y no puede dejar que el mar se degrade.

**Qué hace el jugador:** elegir una de tres herramientas (red, barrera de contención y material absorbente) y hacer clic en el residuo que corresponde. Si se equivoca de herramienta, pierde tiempo y el juego le explica por qué esa no funciona.

**Qué siente:** urgencia controlada. Siempre hay algo que limpiar, pero cada decisión es sencilla: qué residuo atiendo primero y con qué herramienta.

## 4. Público objetivo

| | |
|---|---|
| **Público principal** | Estudiantes de secundaria, preparatoria y universidad (12 a 25 años) |
| **Público secundario** | Público general interesado en un juego corto con tema ambiental |
| **Conocimientos previos** | Ninguno sobre contaminación marina; sabe usar un mouse |
| **Contexto de uso** | Una computadora de escritorio o portátil, en una sesión corta |
| **Duración de una partida completa** | 10 a 15 minutos |
| **Idioma** | Español |

Dato de apoyo: uno de los referentes revisados (Ocean Odyssey, de NOAA) está pensado para estudiantes de 5.º a 8.º grado; el estudio de Cambridge evaluó un juego con estudiantes de preparatoria. Las pruebas del equipo serán con compañeros universitarios, así que el contenido debe entenderse sin conocimientos técnicos.

## 5. Objetivos

**Del jugador:** mantener la salud del mar por encima de cero hasta que termine el tiempo del turno, limpiando cada residuo con la herramienta adecuada.

**De aprendizaje:** al terminar el juego, el jugador puede:
1. Decir qué herramienta se usa para un plástico y cuáles para una mancha de hidrocarburo.
2. Explicar con una frase por qué el hidrocarburo se contiene antes de absorberse.
3. Mencionar al menos un dato real de las fichas sobre contaminación marina, con su origen.

**Del proyecto:** concientizar sobre tres ODS (14, 12 y 6) con un juego que el equipo pueda terminar.

## 6. Pilares de diseño

1. **Herramienta correcta, no solo rapidez.** La mecánica central enseña: cada residuo exige su herramienta, como en la vida real.
2. **Consecuencias visibles.** La barra de salud del mar y la fauna (peces y tortugas) muestran el efecto de lo que se limpia o se deja.
3. **Dato real al final de cada turno.** El aprendizaje sucede justo después de la acción, cuando el jugador acaba de vivirla.

## 7. Bucle de juego

1. Aparece un barco y suelta un residuo.
2. El jugador decide cuál es el residuo más urgente.
3. Elige la herramienta correspondiente.
4. Hace clic en el residuo: si acierta, desaparece o se reduce; si falla, pierde tiempo y recibe un mensaje.
5. La salud del mar y la fauna reflejan el resultado.
6. Al terminar el turno aparece la ficha y empieza el siguiente.

## 8. Tono y estilo

| Aspecto | Definición |
|---|---|
| **Tono** | Serio pero accesible. Urgente sin ser dramático |
| **Mensaje** | Positivo: el jugador es parte de la solución, no el culpable |
| **Lenguaje** | Frases cortas, sin tecnicismos; el término técnico se explica la primera vez |
| **Contenido** | Imágenes crudas: la fauna que se ve afectada se muestra herida |
| **Visual** | 2D, colores del mar y alto contraste en los residuos para distinguirlos |
| **Sonido** | Opcional. Si se incluye, de licencia libre |

## 9. Conexión con los ODS

Las metas se citan de forma resumida. **Confirmar la redacción exacta en la página oficial de los ODS** antes de entregar.

| ODS | Meta | Cómo aparece en el juego | Qué aprende el jugador |
|---|---|---|---|
| **14 — Vida submarina** | 14.1 (reducir la contaminación marina) y 14.2 (proteger los ecosistemas marinos) | La limpieza es la mecánica central; la fauna y la salud del mar muestran el estado del océano | Que la basura y los derrames dañan la vida marina |
| **12 — Producción y consumo responsables** | 12.4 (gestión racional de desechos) y 12.5 (reducir la generación de residuos) | Cada residuo tiene su tratamiento; las fichas explican el origen de los plásticos | Que el problema empieza en cómo se producen y gestionan los residuos |
| **6 — Agua limpia y saneamiento** | 6.3 (mejorar la calidad del agua reduciendo la contaminación) | El hidrocarburo deteriora el agua y debe contenerse antes de que se expanda | Que la contaminación afecta la calidad del agua |

**Sobre el ODS 6:** es el vínculo más débil de los tres, porque sus metas están pensadas sobre todo para el agua dulce y el saneamiento. Se mantiene porque el derrame de hidrocarburos es un caso claro de deterioro de la calidad del agua. Si en la presentación lo cuestionan, la respuesta es esa, y la alternativa es reemplazarlo por otro ODS cuyas metas encajen mejor. [DECIDIR]

## 10. Qué enseña cada nivel

| Turno | Qué aparece | Herramientas que usa | Tema de la ficha |
|---|---|---|---|
| 1 | Plásticos | Red | Plástico en el océano y fauna afectada |
| 2 | Plásticos y manchas de hidrocarburo | Red, barrera y absorbente | Cómo se responde a un derrame |
| 3 | Más barcos al mismo tiempo | Las tres | Origen de la contaminación y prevención |

## 11. Qué lo diferencia

De los referentes revisados (`docs/07-referentes-y-herramientas.md`), los de clic limpian un solo tipo de residuo con una sola herramienta. Turno de Guardacostas pide elegir **entre varias herramientas según el tipo de residuo**, y esa decisión es la que enseña. Esta afirmación se apoya en cinco referentes y no en una búsqueda exhaustiva.

## 12. Cómo sabremos que funciona

Se medirá con las pruebas del RNF-01 del SRS: 5 personas que no conocen el juego lo juegan, y después responden tres preguntas sin ayuda:
1. ¿Qué herramienta usas para un plástico?
2. ¿Qué herramientas usas para una mancha de petróleo?
3. Menciona un dato que viste en una ficha.

**Criterio:** al menos 4 de 5 personas responden bien las preguntas 1 y 2 **[propuesto]**. Es una medida modesta de comprensión, no de cambio de actitud, y así debe presentarse.

## 13. Fuera del concepto

Movimiento del jugador, mejoras con dinero, dispersantes y varios tipos de barcos (ver `docs/SRS.md`, sección 1.2).

## 14. Riesgos del concepto

- **Que se vuelva repetitivo.** Con un solo tipo de acción, el nivel 1 puede aburrir. Mitigación: los niveles 2 y 3 agregan herramientas y más barcos.
- **Fichas con datos sin verificar.** Si una cifra es incorrecta, el juego enseña algo falso. Mitigación: verificar cada dato antes de incluirlo.
- **Mancha de hidrocarburo.** Es la mecánica más difícil de programar (crece con el tiempo y reacciona a dos herramientas). Si falta tiempo, se simplifica: la mancha no crece y solo se limpia con el absorbente.

## 15. Decisiones pendientes

| Decisión | Quién | Estado |
|---|---|---|
| Nombre final del juego | Ambos | Pendiente |
| Rango de edad (sección 4) | Ambos | Propuesto: 12 a 25 años |
| Herramienta de desarrollo | Ambos | Pendiente |
| Estilo visual | Jonathan | Actividad 11 |
| Datos de las fichas verificados | Maximiliano | Pendiente |
