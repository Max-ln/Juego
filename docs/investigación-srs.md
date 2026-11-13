# Especificación de Requerimientos de Software (SRS / ERS)

El SRS documenta qué debe hacer el software, estableciendo un acuerdo formal entre los involucrados, mientras que la norma internacional vigente que reemplazó a la tradicional IEEE 830 es la **ISO/IEC/IEEE 29148**.

---

## 1. ¿Qué es un SRS/ERS y qué problemas evita?

Un **SRS** (*Software Requirements Specification*) o **ERS** (*Especificación de Requerimientos de Software*) es un documento formal que establece lo que los desarrolladores deben implementar: las funciones, restricciones, interfaces, datos y atributos de calidad del sistema. Describe **qué** debe hacer el producto, no **cómo** debe programarse (Sommerville, 2011, cap. 4).

Su propósito es servir como acuerdo comprensible entre clientes, usuarios, analistas, desarrolladores y *testers*. Un SRS bien elaborado reduce el riesgo de que el equipo construya una solución distinta de la esperada, porque hace explícitos los requerimientos funcionales y no funcionales antes o durante el desarrollo (Sommerville, 2011, cap. 4).

### Problemas que ayuda a evitar
* **Malentendidos entre interesados:** Al definir alcance, propósito, términos y requerimientos, disminuye la ambigüedad sobre qué se entregará (IEEE 830-1998, sec. 5.1).
* **Alcance indefinido o creciente (*scope creep*):** La sección de alcance y las restricciones delimitan qué está incluido y qué queda fuera del producto (IEEE 830-1998, sec. 5.1.2).
* **Requerimientos contradictorios o incompletos:** El documento obliga a organizar, revisar y detallar los requerimientos antes de diseñar o programar (IEEE 830-1998, sec. 5.3).
* **Pruebas difíciles de planear:** Si los requerimientos son verificables, el equipo puede derivar criterios de aceptación y casos de prueba. ISO/IEC/IEEE 29148 señala que un requerimiento verificable puede demostrarse mediante métodos como inspección, demostración, análisis o prueba.
* **Decisiones técnicas prematuras:** Al separar necesidades y restricciones de la solución, el SRS evita confundir un requerimiento con una implementación específica (Sommerville, 2011, cap. 4).
* **Falta de trazabilidad y control de cambios:** Un SRS versionado permite saber qué cambió, cuándo y por qué, facilitando la comunicación con el cliente y la gestión del proyecto (Sommerville, 2011, cap. 4).

En resumen, el SRS no garantiza por sí solo el éxito del proyecto, pero reduce errores costosos de comunicación, alcance, diseño y validación al convertir expectativas informales en un documento estructurado y revisable (IEEE 830-1998, sec. 5).

---

## 2. Secciones de IEEE 830

El estándar **IEEE Std 830-1998** (*IEEE Recommended Practice for Software Requirements Specifications*) propone una estructura de SRS con cuatro partes principales:

| Sección | Contenido principal |
| :--- | :--- |
| **1. Introducción** | Propósito del documento, alcance del producto, definiciones y siglas, referencias y visión general del resto del SRS (IEEE 830-1998, sec. 5.1). |
| **2. Descripción general** | Contexto del producto, funciones principales, características de los usuarios, restricciones, suposiciones y dependencias. No contiene los requerimientos detallados; prepara su comprensión (IEEE 830-1998, sec. 5.2). |
| **3. Requerimientos específicos** | Requerimientos funcionales, de interfaces externas, de desempeño, restricciones de diseño, atributos de calidad y requerimientos lógicos de base de datos. Es la parte más detallada del documento (IEEE 830-1998, sec. 5.3). |
| **4. Información de apoyo** | Apéndices, índice y material complementario que facilita la lectura o el uso del SRS (IEEE 830-1998, sec. 5.4). |

### Detalle de la introducción
Debe incluir cinco subsecciones: propósito, alcance, definiciones (acrónimos y abreviaturas), referencias y visión general. El propósito explica para quién es el documento y por qué existe; el alcance identifica el producto, sus objetivos y lo que no hará (IEEE 830-1998, sec. 5.1).

### Detalle de los requerimientos específicos
Los requerimientos funcionales describen qué debe hacer el sistema: entradas, procesamiento y salidas. IEEE 830 permite expresarlos en lenguaje natural, pseudocódigo, un lenguaje de definición de sistemas o mediante subsecciones de introducción, entradas, procesamiento y salidas (IEEE 830-1998, sec. 5.3). También deben considerarse interfaces externas (usuario, hardware, software y comunicaciones), requerimientos de desempeño, restricciones de diseño, atributos como seguridad o mantenibilidad, y requerimientos lógicos de datos.

### Estado actual de IEEE 830
IEEE 830-1998 fue reemplazado (*superseded*) por **ISO/IEC/IEEE 29148**, publicado inicialmente en 2011 y actualizado en su edición **ISO/IEC/IEEE 29148:2018**. Actualmente, IEEE 830 se utiliza como referencia histórica y estructural, mientras que ISO/IEC/IEEE 29148 es la norma vigente para la ingeniería de requerimientos.

---

## 3. Características de un buen requerimiento

De acuerdo con **ISO/IEC/IEEE 29148:2018**, un buen requerimiento debe cumplir con las siguientes características:

* **Necesario:** Representa una necesidad real de un interesado; si se elimina, se pierde una capacidad requerida.
* **Apropiado:** Corresponde al propósito y contexto del sistema.
* **No ambiguo:** Puede interpretarse de una sola manera.
* **Completo:** Contiene toda la información necesaria para entenderlo y satisfacerlo.
* **Singular:** Expresa una sola idea o requerimiento, en lugar de mezclar varios.
* **Factible:** Puede implementarse dentro de las restricciones tecnológicas, económicas y de tiempo del proyecto.
* **Verificable:** Existe una forma objetiva de comprobar si se cumplió (prueba, inspección, demostración o análisis).
* **Correcto:** Representa fielmente la necesidad del interesado.
* **Conforme:** Sigue las reglas, convenciones y estándares aplicables.

Adicionalmente, todo requerimiento debe ser **consistente** con el resto del documento y contar con un **identificador único** para garantizar su trazabilidad y control de cambios.

### Ejemplos prácticos

* **Ejemplo correcto:**
  > **RF-001:** El sistema permitirá al usuario restablecer su contraseña mediante un enlace enviado a su correo electrónico registrado. El enlace será válido durante 30 minutos y solo podrá utilizarse una vez.
  * **Justificación:** Es específico, singular, medible y verificable; un evaluador puede comprobar el envío del correo, la vigencia de 30 minutos y el uso único del enlace. Cumple con los criterios de no ambigüedad y verificabilidad de ISO/IEC/IEEE 29148.

* **Ejemplo incorrecto:**
  > **RF-002:** El sistema deberá ser rápido y seguro, y permitir recuperar la contraseña fácilmente.
  * **Justificación:** Los términos “rápido”, “seguro” y “fácilmente” son subjetivos y vagos; no establecen métricas, tiempos ni criterios de aceptación, lo que impide su verificación objetiva y genera múltiples interpretaciones.

---

## 4. Plantillas y herramientas para un SRS

### Plantillas estándar
* **Plantilla basada en IEEE 830:** Organiza el documento en introducción, descripción general, requerimientos específicos e información de apoyo. Muy utilizada en entornos académicos.
* **Plantilla del Florida Department of Transportation (FDOT):** Plantilla institucional en formato Word que destaca por incluir una tabla estructurada de control de versiones (versión, fecha, autor y descripción del cambio).
* **Estructura de Sommerville:** Propone prefacio (con lectores esperados, historial de versiones y resumen de cambios), introducción, glosario, definición de requerimientos de usuario, arquitectura del sistema y especificación de requerimientos del sistema (Sommerville, 2011, cap. 4).

### Herramientas para redactar y gestionar
| Herramienta | Uso principal |
| :--- | :--- |
| **Microsoft Word / Google Docs** | Redacción tradicional con plantillas, comentarios, control de cambios y revisión colaborativa. |
| **Markdown + Git** | Redacción como texto plano, fácil de revisar y versionar directamente junto con el código fuente. |
| **Confluence / Notion** | Documentación colaborativa en la nube y vinculación de requerimientos con decisiones y entregables. |
| **Jira / Azure DevOps** | Administración de requerimientos como elementos de trabajo (*tickets*), asignación de responsables y seguimiento de estados. |
| **IBM DOORS / Polarion** | Plataformas especializadas para gestión de requerimientos, trazabilidad avanzada y verificación en proyectos complejos. |

### Herramientas para versionar
**Git** es un sistema de control de versiones distribuido que registra cambios en los archivos a lo largo del tiempo, permitiendo auditar modificaciones y recuperar versiones previas. Para gestionar un SRS eficazmente mediante control de versiones se recomienda:

1. Almacenar el documento (preferiblemente en formato Markdown) dentro de un repositorio Git.
2. Utilizar mensajes de *commit* descriptivos (ej. `Actualiza RF-003: define tiempo máximo de respuesta`).
3. Crear ramas independientes para modificaciones mayores (ej. `feature/requisitos-seguridad`).
4. Emplear *Pull Requests* o *Merge Requests* para revisión por pares antes de aprobar cambios.
5. Mantener una tabla de historial de versiones dentro del propio documento para lectores no técnicos.

---

## Referencias

* Atlassian. (2025). *What is version control?* https://www.atlassian.com/git/tutorials/what-is-version-control/
* Atlassian. (2026). *What is Git?* https://www.atlassian.com/git/tutorials/what-is-git/
* Florida Department of Transportation. (2013). *Software requirement specification template* [Plantilla de documento]. https://www.fdot.gov/docs/default-source/it/pdm/3_requirements/Software_Requirement_Specification_Template.docx
* IEEE. (1998). *IEEE recommended practice for software requirements specifications* (IEEE Std 830-1998). IEEE Standards Association. https://standards.ieee.org/ieee/830/1222/
* International Organization for Standardization, International Electrotechnical Commission, & Institute of Electrical and Electronics Engineers. (2018). *Systems and software engineering — Life cycle processes — Requirements engineering* (ISO/IEC/IEEE 29148:2018). ISO. https://www.iso.org/standard/72089.html

## Declaración de uso de IA

Se utilizó `Perplexity / Claude` para localizar fuentes y para `explicar conceptos / revisar la redacción`.
Las fuentes fueron abiertas y leídas, y los resúmenes fueron verificados contra ellas.
