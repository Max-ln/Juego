## Alcance mínimo (MVP) y análisis de riesgos — *Turno de Guardacostas*

Con base en la evaluación de la Actividad 5 (esfuerzo estimado de **20 puntos de historia**), se establece el Producto Mínimo Viable (MVP) del proyecto, las funcionalidades recortables ante imprevistos y la matriz de riesgos con sus planes de contingencia.

---

### 1. Definición del alcance (MVP vs. Recortes)

| Categoría | Elementos incluidos / excluidos | Justificación |
| :--- | :--- | :--- |
| **Entra en el MVP (Obligatorio)** | • Vista fija del mar con embarcaciones pasando y soltando residuos.<br>• Tres herramientas funcionales: **red**, **barrera de contención** y **material absorbente**.<br>• Dos tipos de contaminantes: residuos plásticos y mancha de hidrocarburo que crece con el tiempo.<br>• Barra de salud del mar con condiciones claras de victoria y derrota.<br>• Fauna reactiva (peces y tortugas que aparecen o se alejan según la salud del mar).<br>• Tres niveles jugables con una ficha de datos reales de los ODS (14, 12 y 6) al finalizar cada nivel. | Garantiza que el ciclo principal del juego sea funcional, entretenido y cumpla su objetivo educativo sin exceder el tiempo de desarrollo. |
| **Fuera del alcance inicial** | • Movimiento libre de una lancha del jugador.<br>• Sistema de tienda o mejoras con dinero.<br>• Dispersantes y nubes químicas.<br>• Múltiples clases de barcos con comportamientos distintos. | Evita que el proyecto vuelva a crecer (como el concepto descartado de 55 SP) y mantiene el enfoque en la mecánica central. |
| **Plan de recorte (Si hay retrasos)** | 1. **Primer recorte:** Reducir la fauna reactiva a animaciones simples en la interfaz o mantener solo un tipo de pez en pantalla.<br>2. **Segundo recorte:** Sustituir las animaciones complejas de expansión de la mancha de hidrocarburo por un cambio de tamaño escalonado (chico, mediano, grande) con temporizador fijo.<br>3. **Tercer recorte (Emergencia):** Consolidar el juego en **2 niveles jugables** (Nivel 1: Plásticos; Nivel 2: Plásticos + Hidrocarburo) mostrando las fichas educativas en la pantalla de cierre. | Permite entregar un juego jugable, sin errores críticos y con el contenido educativo completo aunque se reduzca el tiempo disponible. |

---

### 2. Matriz de análisis de riesgos y plan de respuesta

| ID | Riesgo identificado | Probabilidad | Impacto | Plan de prevención (Mitigación) | Plan de respuesta (Contingencia) |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **R1** | **Complejidad técnica de la mancha de hidrocarburo y la barrera de contención:** Que la detección de colisión entre la barrera dibujada/colocada y la mancha que crece genere errores o consuma demasiado tiempo. | Alta | Alto | Diseñar la barrera mediante puntos o segmentos predeterminados alrededor del derrame en lugar de física de fluidos libre. | Reemplazar el crecimiento dinámico por tres estados de tamaño fijos (pequeño, mediano, grande) que avancen cada *X* segundos si no se coloca la barrera. |
| **R2** | **Desbalanceo de dificultad entre niveles:** Que los residuos caigan demasiado rápido o la mancha crezca tan veloz que el jugador pierda sin poder reaccionar. | Media | Medio | Configurar velocidades, tasas de aparición y puntos de salud en variables externas fáciles de ajustar durante las pruebas. | Realizar una sesión rápida de pruebas internas entre los dos integrantes antes del cierre para ajustar los tiempos de aparición. |
| **R3** | **Retrasos por carga académica de otras materias:** Que el tiempo disponible se reduzca en semanas de entregas finales y exámenes. | Media | Alto | Dividir las tareas en bloques pequeños de 1 a 2 horas y priorizar primero la lógica funcional antes que los detalles visuales. | Activar el **Plan de recorte** (simplificar fauna y reducir a 2 niveles jugables) para asegurar la entrega puntual del MVP. |
| **R4** | **Falta de recursos gráficos o sonoros a tiempo:** Que crear sprites personalizados desde cero retrase la programación de las mecánicas. | Baja | Medio | Programar primero usando figuras geométricas simples (*placeholders*) para validar toda la lógica del juego. | Utilizar paquetes de assets 2D libres de derechos (con atribución adecuada) o gráficos minimalistas consistentes. |
| **R5** | **Conflictos de versión o pérdida de avances en el código:** Que ambos modifiquen los mismos archivos al mismo tiempo en GitHub. | Baja | Alto | Trabajar en ramas separadas (`feature/...`) o dividir archivos por responsabilidad (lógica de niveles, interfaz, fichas educativas) y hacer *commits* frecuentes. | Usar el historial de versiones de Git para revertir al último *commit* estable funcional. |
