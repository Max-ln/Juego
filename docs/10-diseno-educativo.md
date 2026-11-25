## Diseño del contenido educativo — *Turno de Guardacostas*

A continuación se define la integración educativa de los tres objetivos seleccionados (**ODS 14: Vida submarina**, **ODS 6: Agua limpia y saneamiento** y **ODS 13: Acción por el clima**) dentro de la jugabilidad, detallando qué información se muestra, el momento exacto de aparición y la retroalimentación visual y textual para el jugador.

---

### 1. Matriz de aparición y contenido por momento del juego

| Momento del juego | Tipo de mensaje | ODS vinculado | Dato / Mensaje que aparece | Retroalimentación al jugador |
| :--- | :--- | :--- | :--- | :--- |
| **Inicio de cada nivel** | Objetivo breve (1 frase) | ODS 14 / ODS 6 / ODS 13 | Instrucción rápida sobre el tipo de residuo o derrame que aparecerá y la herramienta correcta para contenerlo. | Ícono resaltado de la herramienta recomendada en el HUD (Red, Barrera de contención o Material absorbente). |
| **Durante la partida (al limpiar bien)** | Micro-retroalimentación visual | **ODS 14** (Meta 14.1) | Etiqueta flotante corta que no corta el ritmo (ej. *"+Salud marina"*). | Sube la **barra de salud del mar**, el agua recupera su tono claro y reaparecen peces y tortugas. |
| **Durante la partida (error de herramienta)** | Alerta inmediata (Tooltip) | **ODS 6** (Meta 6.3) | Mensaje breve en pantalla: *"La red no detiene hidrocarburos; rodea primero la mancha con la barrera y luego usa el absorbente"*. | Destello rojo suave en la herramienta equivocada y vibración corta en el cursor. |
| **Durante la partida (mancha sin contener)** | Alerta de impacto | **ODS 13** (Meta 13.1) / **ODS 6** | Aviso cuando el derrame crece: *"La contaminación debilita la capacidad del océano para regular el clima y absorber CO₂"*. | Baja la **barra de salud del mar** y la fauna marina se aleja de la zona afectada. |
| **Al completar el Nivel 1** | Ficha educativa (Pantalla de resumen) | **ODS 14: Vida submarina** (Meta 14.1) | *"Cada año llegan al océano entre 11 y 14 millones de toneladas de plástico, afectando a más de 800 especies marinas, incluidas todas las especies de tortugas."* (Fuente: PNUMA / ONU). | Muestra el porcentaje de salud del mar recuperado y desbloquea el Nivel 2. |
| **Al completar el Nivel 2** | Ficha educativa (Pantalla de resumen) | **ODS 6: Agua limpia y saneamiento** (Meta 6.3) | *"1 litro de hidrocarburo puede contaminar hasta 1,000 litros de agua. En la vida real se despliegan barreras flotantes para frenar el avance y material absorbente para retirarlo."* (Fuente: OMI / NOAA). | Muestra la eficiencia de contención del derrame y desbloquea el Nivel 3. |
| **Al completar el Nivel 3 (Victoria)** | Ficha educativa final | **ODS 13: Acción por el clima** (Meta 13.1) | *"El océano absorbe cerca del 30 % del dióxido de carbono (CO₂) producido por la actividad humana y más del 90 % del exceso de calor; mantenerlo limpio es clave frente al cambio climático."* (Fuente: ONU / IPCC). | Pantalla final de océano saludable lleno de peces y tortugas, con el resumen de los 3 niveles. |
| **Derrota (Salud del mar en 0 %)** | Retroalimentación formativa | ODS 14 / ODS 6 / ODS 13 | *"El ecosistema colapsó por acumulación de contaminantes. Recuerda: recoge plásticos con la red y rodea primero los derrames con la barrera."* | Botón de reintento rápido del nivel sin perder el avance anterior. |

---

### 2. Reglas de diseño de la retroalimentación

1. **No interrumpir la acción:** Durante el juego activo solo se usan señales visuales (barra de salud, aparición/huida de fauna, color del agua) y alertas de máximo una línea cuando el jugador usa la herramienta equivocada.
2. **Aprendizaje por consecuencia directa:** El jugador comprueba que cada contaminante exige un protocolo real (red para sólidos; barrera + absorbente para hidrocarburos), reforzando la protección de la calidad del agua (**ODS 6**).
3. **Dato real al cierre de cada nivel:** Las estadísticas verificadas de **ODS 14**, **ODS 6** y **ODS 13** (fuentes: PNUMA, ONU, OMI, NOAA e IPCC) se muestran en las pantallas de transición entre niveles para que el jugador las lea con calma y las conecte con lo que acaba de resolver.
