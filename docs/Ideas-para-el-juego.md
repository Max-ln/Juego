## Dejo por aquí 5 propuestas de proyectos alternativos con mecánicas sencillas para que las revisemos:

- [ ] **Defensor de la Cosecha (Wave Defense 2D):** Juego de acción *top-down* con estética pixel-art. Consiste en proteger un huerto central de oleadas de plagas. Solo requiere programación básica de colisiones y máquinas de estado para los enemigos.
- [ ] **Recolector Contrarreloj (Gestión de tiempo):** Minijuego con tiempo límite para plantar, regar y cosechar alimentos. Ideal para estructurar la lógica de los *game loops* y el manejo de eventos o temporizadores.
- [ ] **Plataformero de Evasión (Endless Runner):** Avance continuo lateral donde el personaje salta y esquiva obstáculos. Las físicas se limitan a gravedad y vectores de salto, lo que lo hace muy rápido de prototipar.
- [ ] **Simulador de Decisiones en Consola (Basado en texto):** Juego ejecutado directamente en la terminal (ideal para aplicar lógica en C o Python). Se administran los recursos de una comunidad tomando decisiones que modifican variables a través de condicionales.
- [ ] **Rompecabezas de Conciencia Ambiental:** Juego tipo memorama en una cuadrícula. Mecánicamente muy accesible al requerir principalmente el recorrido de matrices bidimensionales y eventos de clic, permitiendo integrar temáticas de consumo responsable.
- [ ] **Marea Limpia: Crisis de Contenedores** (Prototipo 2D)
Estilo Visual y Perspectiva:
Juego en 2D con vista cenital (top-down). Se puede utilizar estética pixel-art (inspirada en la perspectiva de juegos de agricultura o simulación). Esta cámara es ideal porque permite al jugador tener un panorama claro de la extensión del derrame, los obstáculos y la distribución de la basura en el agua.

Premisa del Juego:
Tras una fuerte tormenta, un buque mercante ha perdido varios contenedores peligrosos cerca de la costa. Eres el capitán de una embarcación de respuesta ecológica. Tu misión es evitar un desastre total limpiando el agua y asegurando los contenedores antes de que el nivel de toxicidad del océano llegue al 100%.

Mecánicas Principales:

Navegación y Colisiones 2D: Pilotas el barco usando físicas 2D sencillas (vectores de movimiento y rotación). Debes esquivar rocas, fauna marina y escombros. Si chocas, pierdes tiempo o dañas el casco de la embarcación.

Sistema de Herramientas Dinámicas: No puedes limpiar todo con un solo botón. El jugador debe cambiar de herramienta según el residuo:

Redes de arrastre: Para recoger islas de plásticos sólidos.

Bombas de succión: Para limpiar las densas manchas negras de petróleo.

Dispersantes: Para neutralizar nubes químicas de colores brillantes.

El Peligro de los Contenedores: Los contenedores caídos funcionan como los "jefes" o zonas críticas del nivel. Actúan como emisores (spawners) que liberan contaminación cíclicamente. Para detenerlos, el barco debe acercarse, lanzar un ancla y mantenerse dentro de un radio específico por unos segundos (mecánica de control de zona) para sellarlos de forma segura.

Ciclo de Carga y Mejoras (Loop de Juego): El barco tiene capacidad limitada. Tienes que volver al puerto base para descargar la basura. Al reciclar estos materiales, ganas fondos para mejorar tu nave: motores más rápidos, radares que detectan químicos ocultos o mayor capacidad de almacenamiento.

Beneficios Técnicos (Por qué es un buen proyecto):
Es un juego muy escalable para programar en equipo. Permite dividir tareas fácilmente: alguien puede encargarse del movimiento del jugador y las colisiones (hitboxes), otro del sistema de instanciación (spawning) de la basura y las manchas de petróleo a través de matrices o tilemaps, y alguien más del sistema de puntuación y variables del puerto.
