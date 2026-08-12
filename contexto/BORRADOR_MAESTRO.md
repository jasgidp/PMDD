# BORRADOR MAESTRO — Entregable en construcción

**Estado:** estructura alineada al Reto #1; §III.B DevOps y §III.D HCD en borrador.  
**Dominio:** Realidad aumentada (Equipo 2).  
**Outline:** `PLANTILLA_PAPER.md` · **Fuentes:** `FUENTES.md` · **Gestión:** `GESTION_PROYECTO.md`  
**Citas:** `[@Clave]` hasta el ensamblado.

---

## Título

*[pendiente — AR + metodología / espina de pescado]*

## Autores

*[pendiente — orden por confirmar]*  
Universidad EAFIT — Procesos Modernos de Desarrollo de Software  
Quinnie; Jose Manuel Carvajal; Jonathan Sandoval; Lina Ballesteros; Alejandro Ríos

## Abstract (English)

*[pending — no references]*

## Índice de Términos

*[pendiente]*

---

## I. Introducción

*[pendiente]*

---

## II. Dominio: realidad aumentada — estado actual

*Responsable: Quinnie. Checklist: qué es; estado; cómo se abordan proyectos; metodologías; principios diseño/arquitectura; ciclo de vida.*

> **Borrador externo (2026-08-11):** estado del arte en [`estado-arte-realidad-aumentada/`](../estado-arte-realidad-aumentada/) (`estado_arte_RA.pdf`, `estado_arte_RA.tex`, `preview_IEEE.html`). Pendiente integrar prosa aquí y fuentes en `FUENTES.md`.

*[pendiente de integración a Markdown]*

---

## III. Enfoques seleccionados y razón de elección

### A. GenIA
*Responsable: Jose Manuel Carvajal.*  

La Inteligencia Artificial Generativa (GenIA) utiliza modelos capaces de generar contenido nuevo a partir de patrones aprendidos de grandes volúmenes de datos. En Genius Sports, este enfoque se relaciona directamente con GeniusIQ, plataforma de datos e inteligencia artificial que combina grandes volúmenes de datos deportivos con IA y aprendizaje automático para análisis del juego, experiencias personalizadas, generación automatizada de contenido y augmentación de transmisiones. [@GeniusSportsIQ]

En ingeniería de software, GenIA puede apoyar diferentes etapas del ciclo de vida: generación de requisitos e historias de usuario, diseño de componentes y arquitecturas, programación, creación de pruebas, documentación y mantenimiento. En el caso de Genius Sports, esto puede aprovechar sus APIs de datos deportivos, que proporcionan información sobre partidos, jugadores, estadísticas y eventos en tiempo real. [@GeniusSportsAPI]

Para la ejecución de proyectos se propone un proceso iterativo y controlado: identificar el problema, preparar y validar los datos, diseñar la solución, construir un MVP, evaluar sus resultados y posteriormente desplegar y monitorear. Para información deportiva actualizada se propone RAG (Retrieval-Augmented Generation), recuperando información de fuentes autorizadas antes de generar la respuesta y evaluando posteriormente la calidad del sistema. [@GoogleRAG]

Las principales técnicas propuestas son prompt engineering, few-shot prompting, RAG, human-in-the-loop, generación estructurada, guardrails, evaluación automática/humana y versionamiento de prompts. Como herramientas pueden utilizarse Python, Java o TypeScript, servicios de IA, frameworks de integración, bases de datos vectoriales, Git, Docker y herramientas de observabilidad; estas corresponden a alternativas de la propuesta y no a tecnologías confirmadas públicamente como infraestructura interna de Genius Sports.

En cuanto al modelado, GenIA no requiere un lenguaje exclusivo. Se propone utilizar UML, BPMN, C4 Model, ERD, OpenAPI y JSON Schema para representar procesos, arquitectura, datos, APIs y estructura de las respuestas generadas. Los métodos complementarios incluyen Agile, Scrum/Kanban, DevOps, MLOps, DevSecOps, Design Thinking, Lean Startup, TDD y AI Risk Management.

Se toma como referencia el AI Risk Management Framework de NIST, particularmente su perfil para GenIA, para gestionar riesgos relacionados con seguridad, privacidad, sesgos, propiedad intelectual, información incorrecta y otros riesgos propios de estos sistemas. [@NISTGenAI]

Se elige GenIA porque permite aprovechar los datos deportivos de Genius Sports para generar contenido, análisis y experiencias personalizadas, al mismo tiempo que puede apoyar la productividad de los equipos de ingeniería. Su adopción debe ser gradual y acompañada de datos confiables, evaluación, trazabilidad, seguridad y supervisión humana.


### B. DevOps
*Responsable: Jonathan Sandoval.*  
*Nota: el detalle del caso industrial (empleador) vive solo en `contexto/privado/III_B_DEVOPS_GENIUS.md` (gitignored). Aquí, versión sanitizada para el repo compartido.*

DevOps es un enfoque de ingeniería de software que busca acortar el tiempo entre un cambio en el sistema y su operación en producción, manteniendo calidad, mediante colaboración entre desarrollo y operaciones, automatización y entrega continua [@Bass2015], [@Jabbari2016]. En la ingeniería de software, articula prácticas (CI/CD, infraestructura como código, monitoreo) que condicionan arquitectura y operación [@Bass2015], [@Jabbari2016].

Como referente de ejecución, se toma experiencia industrial en **augmentación gráfica en tiempo real sobre video deportivo broadcast** (superposición de gráficos a partir de tracking y estado del juego): pipelines CI/CD con lint, build, test, release y deploy; contenedores e imágenes en registro cloud; promoción mediante *release candidates* y ambientes de staging/producción; QA con roles de operaciones, ingeniería y contenido; y un **pipeline de contenido** que genera instrucciones de augmentación (artefactos tipados + manifiesto de plugins) además del pipeline de código. [SIN FUENTE PÚBLICA — respaldo en notas privadas del autor; no citar paths internos en la entrega pública sin autorización]

Para el dominio AR del curso se declara el matiz: el referente es *realtime augmentation* sobre video broadcast, no necesariamente AR móvil con *headset*; aun así, comparte con AR la necesidad de entregar software y contenido gráfico de forma repetible. La literatura en AR colaborativa basada en microservicios refuerza la orquestación de componentes heterogéneos [@Vaquero2020]. Se propone transferir CI/CD, contenedores, promoción por ambientes, QA multi-rol y el dual pipeline **código + instrucciones/contenido** a la metodología AR.

Técnicas/herramientas típicas del enfoque: CI/CD, contenedores, registros de imágenes, IaC, secretos, observabilidad y pruebas automatizadas (incl. escenarios costosos de simulación). Lenguajes de modelado/especificación: YAML de pipelines, diagramas de flujo de aplicación, IaC y esquemas JSON de artefactos de contenido. Métodos: entrega continua con RC, commits convencionales, QA operacional previo a producción.

Se elige DevOps porque el dominio AR exige iterar con seguridad operativa sobre software y contenido; el referente industrial de augmentación en tiempo real aporta un modelo concreto transferible al ciclo de vida AR del equipo.

### C. Event Driven Architecture
*Responsable: Lina Ballesteros.*  
*[pendiente]*

### D. Human-Centered Design (HCD)
*Responsable: Alejandro Ríos.*

El Diseño Centrado en el Humano (HCD) es un enfoque de desarrollo de sistemas interactivos que busca hacerlos usables y útiles centrándose en los usuarios, sus necesidades y el contexto de uso. A diferencia de los demás enfoques del equipo, está **normalizado**: ISO 9241-210 fija seis principios —entre ellos la participación del usuario durante todo el desarrollo, la iteración y el equipo multidisciplinario— y cuatro actividades cíclicas: entender el contexto de uso, especificar requisitos, producir soluciones de diseño y evaluar contra los requisitos [@ISO9241210].

Su relación con la ingeniería de software se articula en la *Human-Centered Software Engineering*, que integra la usabilidad en el ciclo de vida en lugar de tratarla como fase cosmética final [@Seffah2005]. Su aporte es convertir la usabilidad en requisitos no funcionales medibles y elevar la evaluación a fase de primera clase, con capacidad de retornar el diseño a etapas anteriores [@Ferre2005].

No responde a un único proceso sino a una familia de modelos —Star Life Cycle, ISO 13407, Usage-Centered Design y Usability Engineering Lifecycle— comparados por Ferre et al. [@Ferre2005]. Sus técnicas se distribuyen por fase: entrevistas contextuales y observación, personas y escenarios, prototipado de fidelidad creciente, y evaluación mediante pruebas de usabilidad, evaluación heurística [@Nielsen1994] e instrumentos como SUS o NASA-TLX.

En lenguajes de modelado dispone de notaciones formales —ConcurTaskTrees para tareas [@Paterno2000] e IFML, estándar OMG para flujos de interacción [@OMG-IFML]— aunque la práctica industrial se apoya en artefactos semi-formales (personas, mapas de recorrido, storyboards). Esa asimetría entre notación disponible y notación usada es en sí un hallazgo para el eje **Artefactos**.

Se elige HCD porque hay evidencia de una brecha entre lo que ofrece y lo que el dominio aplica: una revisión sistemática de 30 artículos filtrados de 498 concluye que **no existen métricas de experiencia específicas de AR** [@Graser2024], y la investigación en AR ha desatendido la dimensión de usuario [@Picardi2024]. En AR el contexto de uso es variable y los requisitos inmaduros, condiciones donde HCD resulta más indicado. No se incorpora por completitud metodológica, sino por un déficit medido de validación con usuarios.

*Insumo para §IV — aporte de HCD a los seis ejes [@Ceret2013]:*

| Eje | Aporte de HCD |
|-----|---------------|
| Ciclo | Iteración obligatoria con **retorno explícito** (*backwards*): si la evaluación no satisface los requisitos, el proceso vuelve a contexto, requisitos o diseño [@ISO9241210]. Granularidad **local y regional**. |
| Colaboración | **Usuario como rol externo formal** presente en todo el ciclo; equipo **multidisciplinario** (principio 6) [@ISO9241210]. |
| Artefactos | Contexto de uso, personas, escenarios, prototipos e **informes de evaluación con métricas**. Formalización **mixta**: existen notaciones formales pero domina el artefacto semi-formal [@Paterno2000], [@OMG-IFML]. |
| Uso recomendado | Indicado cuando la **madurez de requisitos es baja** y el contexto de uso es incierto — condición característica de AR [@Graser2024]. |
| Madurez | **Alta.** Normalizado internacionalmente, con más de dos décadas de literatura [@ISO9241210], [@Seffah2005]. |
| Flexibilidad | **Alta variabilidad:** al menos cuatro modelos de proceso conviven bajo el mismo marco [@Ferre2005]. |

---

## IV. Espina de pescado y propuesta metodológica

*Base: [@Ceret2013]. Definir roles, formatos, ciclos y justificación; valor diferencial.*

### A. Ciclo
*[pendiente]*

### B. Colaboración
*[pendiente]*

### C. Artefactos
*[pendiente]*

### D. Uso recomendado
*[pendiente]*

### E. Madurez
*[pendiente]*

### F. Flexibilidad
*[pendiente]*

### G. Valor diferencial frente a metodologías actuales
*[pendiente]*

---

## V. Conclusión

*[pendiente]*

---

## Referencias

- [@Ceret2013]
- *(añadir fuentes AR y de cada enfoque tras verificación)*
