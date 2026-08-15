# BORRADOR MAESTRO — Entregable en construcción

**Estado:** Título, Abstract, Índice e Introducción (Quinnie); §II Dominio AR (versión completa, Quinnie); §III.B DevOps, §III.C EDA, §III.D HCD y §IV en borrador.  
**Dominio:** Realidad aumentada (Equipo 2).  
**Outline:** `PLANTILLA_PAPER.md` · **Fuentes:** `FUENTES.md` · **Gestión:** `GESTION_PROYECTO.md`  
**Citas:** `[@Clave]` hasta el ensamblado.

---

## Título

Primera aproximación a una metodología de desarrollo de software para realidad aumentada basada en taxonomía de procesos

## Autores

*[pendiente — orden por confirmar]*  
Universidad EAFIT — Procesos Modernos de Desarrollo de Software  
Quinnie Nastasja Villarreal Aragon; Jose Manuel Carvajal; Jonathan Sandoval; Lina Ballesteros; Alejandro Ríos

## Abstract (English)

*Responsable: Quinnie Nastasja Villarreal Aragon. Sin citas (IEEE).*

Augmented reality (AR) systems combine real and virtual objects in real time with spatial registration, yet software projects in this domain still lack a consolidated development methodology that jointly addresses technical delivery, event-driven collaboration, and explicit user validation. This paper reviews the current state of AR—definition and maturity, how projects are approached, prevailing methods, design and architecture principles, and a typical life cycle—and examines four complementary software-engineering approaches: generative artificial intelligence (GenAI), DevOps, event-driven architecture (EDA), and human-centered design (HCD). Building on the process-model taxonomy of Céret et al., the team proposes a first methodological approximation for AR software work. The proposal defines decisions along six axes—cycle, collaboration, artifacts, recommended use, maturity, and flexibility—including two independent return gates (user evaluation and performance), mixed artifact formalization with an explicit boundary criterion, declared limits of applicability, and configurable variability (HCD and DevOps mandatory; EDA and GenAI conditional). The contribution is positioned as an unvalidated first approximation relative to consolidated process models such as Spiral, RAD, and XP, and is intended as a structured baseline for subsequent empirical validation and refinement.

## Índice de Términos

*Responsable: Quinnie Nastasja Villarreal Aragon. Orden alfabético (inglés, alineado al Abstract).*

Augmented reality, DevOps, event-driven architecture, generative AI, human-centered design, process models, process taxonomy, software methodology

---

## I. Introducción

*Responsable: Quinnie Nastasja Villarreal Aragon.*

La realidad aumentada (AR) se caracteriza por combinar objetos reales y virtuales de forma interactiva, en tiempo real y con registro espacial tridimensional [@Azuma1997]. El dominio ha pasado de prototipos de laboratorio a despliegues móviles e industriales con madurez parcial: es viable en nichos concretos, pero persisten retos de tracking, interacción, evaluación con usuarios y coordinación de sistemas socio-técnicos [@Azuma2001], [@Goh2023], [@Graser2024]. En la práctica, los equipos deben co-diseñar hardware, pipelines de tracking y renderizado, contenido gráfico y reglas de interacción [@Schmalstieg2016], [@Devagiri2024].

El problema que motiva este trabajo no es solo técnico. Aunque existen guías de arquitectura, ciclos multimedia adaptados y marcos de evaluación de usabilidad para AR, sigue siendo limitada una **metodología de desarrollo de software** que integre de forma explícita la entrega continua de software y contenido, la reacción a eventos en experiencias distribuidas o colaborativas, y la validación reiterada con usuarios —dimensión que la evidencia identifica como déficit del dominio [@Vaquero2020], [@Graser2024]. Sin esa integración, las decisiones sobre ciclo, roles, artefactos, límites de uso y madurez del proceso quedan fragmentadas entre enfoques parciales.

Este artículo propone una **primera aproximación metodológica** para el desarrollo de software en realidad aumentada. Como marco para estructurar esas decisiones se adopta la taxonomía de modelos de proceso de Céret et al., que organiza el diseño de metodologías en seis ejes: ciclo, colaboración, artefactos, uso recomendado, madurez y flexibilidad [@Ceret2013]. Sobre ese andamiaje se combinan cuatro enfoques de ingeniería de software: inteligencia artificial generativa (GenIA), para apoyar productividad y generación controlada cuando hay datos confiables; DevOps, para entrega repetible de software y contenido; arquitectura orientada a eventos (EDA), para experiencias AR distribuidas y en tiempo real; y diseño centrado en el humano (HCD), para elevar la evaluación con usuarios a fase de primera clase.

La propuesta resultante define: un ciclo incremental con dos compuertas de retorno independientes (evaluación con usuarios y pruebas de latencia/resiliencia); más de cinco roles internos más dos roles externos formales; formalización mixta de artefactos con criterio declarado; límites explícitos de uso y de no-uso; madurez declarada como primera aproximación no validada; y variabilidad configurable (HCD y DevOps obligatorios; EDA y GenIA condicionales). El valor diferencial se discute frente a Spiral, RAD y XP según las clasificaciones ya publicadas en [@Ceret2013].

El resto del artículo se organiza así: la Sección II presenta el estado del dominio AR; la Sección III desarrolla los cuatro enfoques y la razón de su elección; la Sección IV define la propuesta metodológica sobre los seis ejes y su valor diferencial; y la Sección V cierra con síntesis, limitaciones y trabajo futuro.

---

## II. Dominio: realidad aumentada — estado actual

*Responsable: Quinnie.*  
*Versión completa alineada al estado del arte en [`estado-arte-realidad-aumentada/`](../estado-arte-realidad-aumentada/). Sustituye la condensación previa (~570 palabras) tras validación de la autora.*

### A. Qué es la Realidad Aumentada y cuál es su estado de desarrollo

#### Definición y delimitación conceptual

La Realidad Aumentada (RA) se define clásicamente como un sistema que *(i)* combina objetos reales y virtuales en un entorno real, *(ii)* opera de forma interactiva y en tiempo real, y *(iii)* registra (alinea) objetos reales y virtuales en tres dimensiones [@Azuma1997]. Esta definición es tecnológicamente agnóstica: no se restringe a un tipo particular de visualizador (p. ej., HMD) ni al sentido de la vista [@Azuma2001].

Milgram y Kishino situaron la RA dentro del *continuum* realidad–virtualidad de la Realidad Mixta (RM), donde el entorno predominante es el mundo real y este se enriquece con contenido generado por computador; el extremo opuesto es la Realidad Virtual (RV) y, entre ambos, aparece la Virtualidad Aumentada [@Milgram1994]. Billinghurst, Clark y Lee consolidaron esta base conceptual en un estudio amplio de HCI, reafirmando el papel de la RA como interfaz espacial que superpone información digital al entorno físico [@Billinghurst2015].

#### Estado de desarrollo

El campo evolucionó desde prototipos de laboratorio hacia plataformas móviles y *wearables* de uso más amplio. Azuma [@Azuma1997] identificó tempranamente el registro, la latencia y la sensorización como problemas centrales. La actualización de 2001 documentó avances en *tracking*, despliegues móviles y displays, sin resolver por completo la alineación estable en entornos no controlados [@Azuma2001].

Los meta-análisis de ISMAR muestran el desplazamiento temático del área: Zhou et al. sintetizaron la primera década con foco en *tracking*, interacción y display [@Zhou2008]; Kim et al. reportaron, para 2008–2017, un aumento marcado de evaluación y *rendering*, junto con el auge de RA móvil y reconstrucción 3D [@Kim2018]. En años recientes, Goh et al. observan que la investigación en RA *wearable* se orienta a adopción masiva, ética, accesibilidad, avatares/*embodiment* y agentes virtuales inteligentes, además de retos persistentes en display, tracking e interacción [@Goh2023].

En paralelo, revisiones técnicas recientes sistematizan tecnologías de tracking, herramientas de desarrollo, displays, RA colaborativa y preocupaciones de seguridad [@Syed2023]. Devagiri et al. ofrecen un panorama consolidado de 2024: tecnologías habilitadoras y potenciadoras, matriz de hardware comercial, capacidades de software y un conjunto de guías de desarrollo desde la ideación hasta el despliegue [@Devagiri2024]. En conjunto, el estado actual puede caracterizarse como *madurez parcial*: la RA es viable comercialmente en móviles y en niches industriales/educativos, mientras que la RA óptica *see-through* “indistinguible” y la adopción generalizada siguen siendo desafíos abiertos [@Goh2023], [@Devagiri2024].

### B. Cómo se abordan los proyectos en el contexto de RA

Los proyectos de RA suelen abordarse como sistemas socio-técnicos en los que hardware (cámara, IMU, HMD, dispositivo móvil), software (*tracking*, renderizado, gestión de escena) y contenido (modelos 3D, anotaciones, reglas de interacción) deben co-diseñarse [@Schmalstieg2016], [@Devagiri2024].

En la práctica, el abordaje típico incluye:

1. **Delimitación del caso de uso y contexto de uso:** dominio (mantenimiento, educación, medicina, colaboración, etc.), usuarios, entorno físico y restricciones de seguridad [@NIST2022], [@Sereno2022].
2. **Selección de plataforma y modalidad de display:** RA móvil (*handheld*), HMD óptico o por video, o configuraciones colaborativas heterogéneas [@Syed2023], [@Devagiri2024].
3. **Elección de la estrategia de anclaje espacial:** marcadores fiduciales, SLAM/*markerless*, localización visual-inercial o mapas previos del entorno [@Kim2018], [@Syed2023].
4. **Diseño de la interfaz espacial e interacción:** gestos, voz, mirada, tangibles o híbridos, cuidando carga cognitiva y coherencia real–virtual [@Kourouthanassis2015], [@Endsley2017].
5. **Implementación iterativa y evaluación con usuarios:** prototipado temprano, pruebas de usabilidad y métricas de efectividad, eficiencia y satisfacción en contexto [@NIST2022], [@Dunser2011].

En RA colaborativa, el abordaje se amplía a dimensiones de espacio, tiempo, simetría de roles y de tecnología, y modalidades de entrada/salida, lo que exige decisiones explícitas de arquitectura multi-usuario y *awareness* compartido [@Billinghurst2002], [@Sereno2022].

### C. Metodologías utilizadas

No existe una única metodología estándar universal para RA; la literatura converge en la combinación de marcos de desarrollo multimedia/software con diseño centrado en el humano (HCD) y evaluación específica de usabilidad en RA.

#### Ciclos de desarrollo multimedia adaptados

Roedavan et al. proponen un marco basado en el *Multimedia Development Life Cycle* (MDLC) adaptado a RA, estructurado en capas de fase, etapa de desarrollo y componentes. En producción distinguen núcleo (*tracking* y anclaje), visual (contenido y renderizado) e interacción; en postproducción enfatizan evaluación de compatibilidad, desempeño y usabilidad [@Roedavan2025].

#### Diseño centrado en el usuario

ISO 9241-210 provee el marco general de HCD para sistemas interactivos —comprensión del contexto, especificación de requisitos, producción de soluciones y evaluación— aplicable a RA como sistema interactivo espacial [@ISO9241210]. NIST IR 8422 operacionaliza este enfoque para RA mediante un marco de evaluación de usabilidad en cinco componentes: alcance, usuarios y contexto, escenarios/tareas, métricas y medidas [@NIST2022].

#### Evaluación HCI específica de RA

Dünser y Billinghurst argumentan que los métodos HCI tradicionales deben adaptarse porque la RA introduce factores de registro espacial, confort, carga cognitiva y acoplamiento con el entorno físico [@Dunser2011]. Trabajos previos del mismo grupo plantean la aplicación explícita de principios HCI al diseño de sistemas RA [@Dunser2007]. Endsley et al. aportan heurísticas de diseño orientadas a interacciones dinámicas en entornos aumentados [@Endsley2017].

En síntesis, las metodologías predominantes son: **(a)** ciclos iterativos tipo MDLC/ágil adaptados a componentes RA; **(b)** HCD/ISO 9241-210; y **(c)** evaluación heurística y empírica específica de RA.

### D. Principios de diseño y arquitectura

#### Principios de diseño

Kourouthanassis et al. desmitifican el diseño de aplicaciones de RA móvil y enfatizan criterios de utilidad contextual, interacción natural, gestión de la atención y coherencia entre capas real y virtual [@Kourouthanassis2015]. Endsley et al. formalizan heurísticas para interacciones dinámicas, advirtiendo que omitir usabilidad en el diseño incrementa errores y erosiona la confianza del usuario [@Endsley2017]. Dünser et al. recomiendan trasladar principios HCI (visibilidad del estado del sistema, correspondencia con el mundo real, control del usuario, prevención de errores, etc.) al dominio espacial de la RA [@Dunser2007].

Principios recurrentes en la literatura:

- Registro espacial estable y baja latencia percibida.
- Claridad de la información aumentada sin ocluir indebidamente el entorno relevante.
- Interacción alineada con capacidades del dispositivo y del usuario.
- Consideración de confort, seguridad, privacidad y continuidad ante interrupciones.
- Soporte a *awareness* y coordinación en escenarios colaborativos [@Sereno2022].

#### Arquitectura de sistemas

Reicher et al. formularon una arquitectura de referencia para sistemas RA a partir del estudio de implementaciones existentes, destacando atributos de calidad como latencia de tracking/renderizado, operación inalámbrica, múltiples dispositivos de tracking, reutilización e integración de componentes [@Reicher2003]. MacWilliams et al. complementaron este trabajo con un catálogo de patrones de diseño para RA (específicos del dominio y adaptaciones de patrones generales), orientado a un vocabulario compartido de decisiones arquitectónicas [@MacWilliams2004].

A nivel industrial/estándar, ETSI GS ARF 003 especifica una arquitectura funcional de referencia para componentes, sistemas y servicios de RA, con bloques lógicos interconectados por puntos de referencia y despliegue posible en dispositivo, nube o de forma híbrida [@ETSI-ARF003]. Schmalstieg y Höllerer sistematizan la arquitectura típica como acoplamiento de visión por computador, gráficos, tracking, visualización e interacción 3D [@Schmalstieg2016].

De manera esquemática, las arquitecturas de RA suelen descomponerse en: *captura/sensado*, *tracking y mapeo del mundo*, *modelo del entorno/contexto*, *lógica de aplicación*, *renderizado/presentación* e *interacción*, con requisitos transversales de tiempo real y baja latencia extremo a extremo [@Reicher2003], [@ETSI-ARF003].

### E. Ciclo de vida para llegar a soluciones en RA

A partir de la convergencia entre MDLC adaptado [@Roedavan2025], guías de desarrollo contemporáneas [@Devagiri2024] y HCD/evaluación de usabilidad [@ISO9241210], [@NIST2022], el ciclo de vida típico de una solución RA puede formularse así:

1. **Ideación y análisis de contexto.** Definir problema, usuarios, entorno físico, riesgos y valor de la aumentación frente a alternativas no-RA [@Devagiri2024], [@NIST2022].
2. **Especificación de requisitos.** Requisitos funcionales (qué se aumenta, cómo se interactúa) y no funcionales (latencia, precisión de registro, autonomía, privacidad, colaboración) [@Reicher2003], [@Sereno2022].
3. **Diseño conceptual y arquitectónico.** Selección de display/plataforma, estrategia de tracking, patrones arquitectónicos y principios/heurísticas de UI espacial [@MacWilliams2004], [@ETSI-ARF003], [@Endsley2017].
4. **Preparación de activos y prototipado.** Modelos 3D, marcadores/mapas, interacciones; prototipos de fidelidad creciente [@Roedavan2025], [@Schmalstieg2016].
5. **Implementación (núcleo, visual, interacción).** Integración del *pipeline* de tracking–render–input sobre el *framework* elegido [@Roedavan2025], [@Syed2023].
6. **Evaluación iterativa.** Pruebas técnicas (precisión, FPS, compatibilidad) y de usabilidad con usuarios reales en contexto, con métricas explícitas [@NIST2022], [@Dunser2011].
7. **Despliegue, operación y evolución.** Publicación en dispositivos objetivo, monitoreo de desempeño en campo, actualización de mapas/contenido y mejora continua [@Devagiri2024].

Este ciclo es inherentemente **iterativo**: los hallazgos de evaluación realimentan requisitos y diseño, en coherencia con ISO 9241-210 [@ISO9241210] y con la evidencia de que la madurez de RA depende tanto de avances técnicos como de calidad de experiencia de usuario [@Kim2018], [@Goh2023].

> **Nota de alcance:** este apartado se limita al estado del arte orientado a las cinco preguntas del checklist del dominio. No desarrolla contribuciones experimentales propias ni una revisión sistemática exhaustiva de todos los subdominios de aplicación.

---

## III. Enfoques seleccionados y razón de elección

### A. GenIA
*Responsable: Jose Manuel Carvajal.*  

La Inteligencia Artificial Generativa (GenIA) utiliza modelos capaces de generar contenido nuevo a partir de patrones aprendidos de grandes volúmenes de datos. En el contexto de este proyecto, GenIA resulta pertinente porque permite apoyar diferentes actividades del desarrollo de software aplicado a realidad aumentada (RA), como la generación de requisitos, diseño de componentes, programación, pruebas, documentación y mantenimiento. Su incorporación busca complementar el trabajo del equipo mediante generación asistida, manteniendo la validación humana de los resultados [IBM-GenAI].

Para el caso de Genius Sports, esta capacidad puede aprovechar información deportiva estructurada y contextual para generar o transformar contenidos relacionados con la experiencia de RA. GeniusIQ constituye un ejemplo del uso de IA y datos deportivos dentro del ecosistema de Genius Sports, mientras que sus APIs proporcionan información sobre partidos, jugadores, estadísticas y eventos que puede servir como fuente de información para las funcionalidades propuestas [GeniusSportsIQ] [GeniusSportsAPI].

Para la ejecución del proyecto se propone un proceso iterativo: identificar la necesidad, preparar y validar las fuentes de información, diseñar la solución, generar una primera versión, evaluar sus resultados y posteriormente integrarla. Cuando se requiera utilizar información específica o actualizada, puede emplearse RAG (Retrieval-Augmented Generation), recuperando información desde fuentes autorizadas antes de generar la respuesta y evaluando posteriormente su calidad [GoogleRAG].

Las principales técnicas propuestas son prompt engineering, few-shot prompting, RAG, human-in-the-loop, generación estructurada, guardrails, evaluación automática y humana y versionamiento de prompts. Como herramientas pueden utilizarse Python, Java o TypeScript, servicios de IA, frameworks de integración, bases de datos vectoriales, Git, Docker y herramientas de observabilidad. Estas corresponden a alternativas de la propuesta y no implican que sean tecnologías confirmadas públicamente como infraestructura interna de Genius Sports.

En cuanto al modelado, GenIA no requiere un lenguaje exclusivo. Se propone utilizar UML, BPMN, C4 Model, ERD, OpenAPI y JSON Schema para representar procesos, arquitectura, datos, APIs y estructuras de información. Los métodos complementarios incluyen Agile, Scrum/Kanban, DevOps, MLOps, DevSecOps, Design Thinking, Lean Startup y TDD.


> ⚠️ *Tabla **derivada por el equipo** a partir de la prosa de esta sección, para poder consolidar §IV. **Pendiente de validación por su autor.***

| Eje | Aporte de GenIA |
|-----|-----------------|
| Ciclo | Ciclo iterativo y controlado: identificar el problema, preparar y validar datos, diseñar la solución, construir un MVP, evaluar resultados, desplegar y monitorear. La evaluación precede al despliegue y puede devolver el proceso a la preparación de datos. |
| Colaboración | Exige **supervisión humana** (*human-in-the-loop*) como control permanente, no como revisión final. La adopción es gradual y acompañada de trazabilidad. |
| Artefactos | Prompts versionados, conjuntos de datos validados, evaluaciones automáticas y humanas, MVP, y salidas con generación estructurada bajo *guardrails*. Modelado con UML, BPMN, C4 Model, ERD, OpenAPI y JSON Schema. |
| Uso recomendado | Indicado cuando existen datos confiables y actualizados sobre los que apoyar la generación (p. ej. mediante RAG). Requiere gestión explícita de riesgos de seguridad, privacidad, sesgos y propiedad intelectual. |
| Madurez | **Emergente.** Los marcos de gestión de riesgo son recientes; se toma como referencia el AI Risk Management Framework de NIST en su perfil para GenIA. |
| Flexibilidad | **Alta.** No requiere un lenguaje de modelado exclusivo y se combina con Agile, Scrum/Kanban, DevOps, MLOps, DevSecOps, Design Thinking, Lean Startup y TDD. |


### B. DevOps
*Responsable: Jonathan Sandoval.*  
*Nota: el detalle del caso industrial (empleador) vive solo en `contexto/privado/III_B_DEVOPS_GENIUS.md` (gitignored). Aquí, versión sanitizada para el repo compartido.*

DevOps es un enfoque de ingeniería de software que busca acortar el tiempo entre un cambio en el sistema y su operación en producción, manteniendo calidad, mediante colaboración entre desarrollo y operaciones, automatización y entrega continua [@Bass2015], [@Jabbari2016]. En la ingeniería de software, articula prácticas (CI/CD, infraestructura como código, monitoreo) que condicionan arquitectura y operación [@Bass2015], [@Jabbari2016].

Como referente de ejecución, se toma experiencia industrial en **augmentación gráfica en tiempo real sobre video deportivo broadcast** (superposición de gráficos a partir de tracking y estado del juego): pipelines CI/CD con lint, build, test, release y deploy; contenedores e imágenes en registro cloud; promoción mediante *release candidates* y ambientes de staging/producción; QA con roles de operaciones, ingeniería y contenido; y un **pipeline de contenido** que genera instrucciones de augmentación (artefactos tipados + manifiesto de plugins) además del pipeline de código. [SIN FUENTE PÚBLICA — respaldo en notas privadas del autor; no citar paths internos en la entrega pública sin autorización]

Para el dominio AR del curso se declara el matiz: el referente es *realtime augmentation* sobre video broadcast, no necesariamente AR móvil con *headset*; aun así, comparte con AR la necesidad de entregar software y contenido gráfico de forma repetible. La literatura en AR colaborativa basada en microservicios refuerza la orquestación de componentes heterogéneos [@Vaquero2020]. Se propone transferir CI/CD, contenedores, promoción por ambientes, QA multi-rol y el dual pipeline **código + instrucciones/contenido** a la metodología AR.

Técnicas/herramientas típicas del enfoque: CI/CD, contenedores, registros de imágenes, IaC, secretos, observabilidad y pruebas automatizadas (incl. escenarios costosos de simulación). Lenguajes de modelado/especificación: YAML de pipelines, diagramas de flujo de aplicación, IaC y esquemas JSON de artefactos de contenido. Métodos: entrega continua con RC, commits convencionales, QA operacional previo a producción.

Se elige DevOps porque el dominio AR exige iterar con seguridad operativa sobre software y contenido; el referente industrial de augmentación en tiempo real aporta un modelo concreto transferible al ciclo de vida AR del equipo.

> ⚠️ *Tabla **derivada por el equipo** a partir de la prosa de esta sección, para poder consolidar §IV. **Pendiente de validación por su autor.***

| Eje | Aporte de DevOps / DevSecOps |
|-----|------------------------------|
| Ciclo | Entrega continua: cada cambio dispara un pipeline (lint, build, test, release, deploy). Promoción por **candidatos de versión** y ambientes escalonados (desarrollo → *staging* → producción), con caminos de excepción documentados. |
| Colaboración | **QA multi-rol** antes de producción: operaciones, ingeniería y contenido firman por separado. Responsabilidad compartida entre quien desarrolla y quien opera. |
| Artefactos | Especificaciones de pipeline en YAML, imágenes de contenedor en registro, infraestructura como código, esquemas JSON de artefactos de contenido y diagramas de flujo de aplicación. Formalización **alta**: son ejecutables, no documentación. |
| Uso recomendado | Indicado cuando hay que entregar **software y contenido** de forma repetible y operable, y cuando el sistema debe permanecer disponible mientras se actualiza. |
| Madurez | **Alta.** Amplia adopción industrial y literatura consolidada sobre definiciones y prácticas [@Jabbari2016], además de tratamiento desde la arquitectura [@Bass2015]. |
| Flexibilidad | **Alta.** Plantillas de plataforma reutilizables evitan reinventar el despliegue en cada iniciativa, y los caminos excepcionales (*hotfix*, *one-off*, solo-configuración) están previstos y registrados. |

### C. Event Driven Architecture
*Responsable: Lina Ballesteros.*  
La Arquitectura Orientada a Eventos (Event-Driven Architecture, EDA) es un estilo arquitectónico en el que componentes desacoplados producen, reciben y procesan eventos de forma asíncrona. Un evento representa un cambio de estado o un hecho relevante, y la comunicación suele seguir un modelo productor–consumidor mediante canales o buses de eventos. Este desacoplamiento permite que los componentes evolucionen de forma más independiente y favorece la modularidad, la escalabilidad y la integración de sistemas distribuidos [@Cabane2024].

En ingeniería de software, EDA afecta decisiones de diseño, calidad, despliegue y observabilidad. Puede combinarse con microservicios y patrones como DDD/CQRS, pero su adopción debe evaluarse por contexto: la evidencia empírica muestra que no garantiza mejores tiempos de respuesta ni menor consumo de recursos frente a una arquitectura monolítica [@Cabane2024]. Por ello, se propone un proceso iterativo: identificar eventos del dominio y sus productores/consumidores; definir contratos y reglas de procesamiento; implementar el flujo; validar funcionalidad, latencia, throughput y resiliencia; desplegar; y monitorear. CEPEDALoCo muestra un ciclo similar apoyado en procesamiento de eventos complejos, brokers, APIs y pruebas sobre flujos reales [@RosaBilbao2023].

Como técnicas se proponen publicación/suscripción, Event Streaming y Complex Event Processing (CEP). Entre las herramientas posibles están Apache Kafka, RabbitMQ, Azure Service Bus, Node-RED y motores CEP. Para modelado, EDA no posee un único lenguaje estándar; se proponen diagramas UML de secuencia y componentes, modelos de eventos y contratos AsyncAPI en JSON/YAML. AsyncAPI permite describir APIs orientadas a mensajes de forma legible por máquina y agnóstica al protocolo [@AsyncAPI]. Como métodos se proponen el diseño orientado a contratos de eventos, el modelado de patrones CEP y la validación iterativa mediante pruebas de integración, rendimiento y resiliencia.

EDA se selecciona para realidad aumentada porque las experiencias distribuidas y colaborativas requieren reaccionar a cambios de interacción, sesión y estado compartido. SARA demuestra una arquitectura AR colaborativa donde servicios y clientes intercambian y procesan eventos para actualizar sesiones y elementos aumentados [@Vaquero2020]. Además, Oberhauser muestra que flujos EDA pueden visualizarse y analizarse en entornos inmersivos con Kafka y RabbitMQ, reforzando su aplicabilidad al ecosistema XR [@Oberhauser2023].

*Insumo para §IV — aporte de EDA a los seis ejes [@Ceret2013]* (sincronizado desde el Google Doc):

| Eje | Aporte de Event-Driven Architecture |
|-----|-------------------------------------|
| Ciclo | EDA no impone por sí misma un ciclo de desarrollo. Para la metodología se propone un ciclo incremental e iterativo, con iteraciones locales o regionales sobre flujos de eventos y retorno (*backwards*) cuando las pruebas de integración, latencia o resiliencia no cumplan los objetivos. Una vez estabilizados los contratos, productores y consumidores pueden desarrollarse parcialmente en paralelo. |
| Colaboración | Se proponen como roles internos: arquitecto de software/eventos, desarrollador AR, desarrollador backend/eventos, QA orientado a integración y rendimiento y DevOps. La coordinación entre equipos se basa en contratos compartidos de eventos, reduciendo las dependencias directas entre productores y consumidores. |
| Artefactos | Catálogo de eventos, esquema de cada evento, matriz productor–consumidor, diagramas UML de secuencia/componentes, especificación AsyncAPI y resultados de pruebas de latencia, throughput y errores. La formalización es **media-alta**, porque los contratos deben poder ser interpretados de manera consistente por equipos distintos. |
| Uso recomendado | Recomendado para experiencias AR distribuidas, colaborativas o en tiempo real, especialmente cuando existen múltiples productores y consumidores de información. **No** se recomienda introducir EDA por defecto en aplicaciones AR pequeñas, locales y con pocas interacciones entre componentes, debido a la complejidad adicional que genera. |
| Madurez | **Media-alta** en ingeniería de software general, debido a su adopción industrial, brokers consolidados y literatura existente; sin embargo, su aplicación específicamente documentada en AR es menor. Por ello, la metodología exige evaluar el enfoque mediante métricas antes de adoptarlo como decisión definitiva. |
| Flexibilidad | **Alta.** Permite agregar o modificar consumidores sin alterar necesariamente al productor y admite diferentes brokers, protocolos y mecanismos de procesamiento. Esta flexibilidad exige versionamiento y gobernanza de contratos para evitar incompatibilidades. |



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

*Base: [@Ceret2013]. Cada eje consolida el aporte de los cuatro enfoques y fija la decisión de la metodología propuesta, usando las gradaciones del autor.*

### A. Ciclo

Los cuatro enfoques coinciden en la iteración pero difieren en qué la dispara: HCD retorna desde la evaluación con usuarios; EDA desde las pruebas de latencia y resiliencia; GenIA desde la evaluación previa al despliegue; DevOps aporta entrega continua con candidatos de versión y promoción por ambientes.

Se propone un ciclo **incremental con gran número de entregas** (1–3 meses en la escala de [@Ceret2013]), con **iteración local y regional** —local sobre el flujo de eventos y el prototipo de interacción, regional sobre el conjunto experiencia–datos— y **retorno explícito obligatorio**. La decisión clave es que existen **dos compuertas de retorno independientes**: la evaluación con usuarios y las pruebas de latencia y resiliencia. Cualquiera de las dos devuelve el proceso a fases anteriores. Esto responde a una carencia concreta: RAD menciona procedimientos de validación pero no especifica qué debe hacerse cuando una etapa no se valida [@Ceret2013].

### B. Colaboración

HCD incorpora al usuario como rol externo formal; DevOps aporta QA multi-rol con firmas separadas; EDA coordina mediante contratos de eventos compartidos; GenIA exige supervisión humana permanente.

Se proponen roles internos —arquitecto de eventos, desarrollador AR, desarrollador backend, ingeniero DevOps y especialista en experiencia de usuario— y **dos roles externos formales**: el usuario final y el responsable de los datos. Son más de cinco roles, el mismo grado que RAD [@Ceret2013], pero con una diferencia sustantiva: RAD centra la coordinación en identificar equipos paralelos y verificar su no-redundancia, sin detallar cómo trabajan juntos [@Ceret2013]. Aquí la coordinación se ancla en **dos artefactos de lectura obligatoria** para todos los roles: el contrato de eventos y el informe de evaluación con usuarios.

### C. Artefactos

Es el eje donde los enfoques tensionan: EDA y DevOps empujan hacia formalización alta —contratos, esquemas, pipelines ejecutables—; HCD aporta artefactos deliberadamente semi-formales; GenIA añade prompts versionados y salidas estructuradas.

Se propone **formalización mixta y declarada por artefacto**. Obligatoriamente formales: el contrato de eventos (AsyncAPI o JSON Schema), la especificación de pipeline y el informe de evaluación con métricas. Deliberadamente semi-formales: los artefactos de exploración de la experiencia. La posición es intermedia entre XP, que no recomienda artefactos no ejecutables por considerarlos inútiles [@Ceret2013], y RAD, que propone alrededor de treinta clases de artefactos no ejecutables solo en su fase de inicialización [@Ceret2013]. El criterio de decisión es explícito: se formaliza lo que cruza una frontera entre equipos; se deja semi-formal lo que sirve para explorar.

### D. Uso recomendado

Recomendada para proyectos de realidad aumentada **distribuidos o en tiempo real**, con múltiples productores y consumidores de datos, equipo multidisciplinario de entre cinco y quince personas, y **madurez de requisitos baja** —condición característica del dominio.

**No recomendada** para aplicaciones AR pequeñas, locales y con pocas interacciones entre componentes, donde EDA añade complejidad sin retorno, ni para proyectos con requisitos cerrados y contexto de uso conocido, donde el peso de HCD no se justifica. Declarar los límites es en sí un aporte: RAD está clasificado como *sin información específica sobre el tamaño de proyecto esperado* y con *mención vaga del tipo de aplicación* [@Ceret2013].

### E. Madurez

La madurez es desigual: HCD y DevOps son altos —normalización internacional y adopción industrial—; EDA es medio-alto en general pero con escasa documentación específica en AR; GenIA es emergente.

En consecuencia, la metodología se declara **primera aproximación no validada**: sin difusión y sin validación empírica. Se propone medirla mediante indicadores por eje —frecuencia de entrega, número de retornos disparados por cada compuerta, cobertura de contratos versionados y resultados de evaluación con usuarios—. Reconocer la ausencia y acompañarla de un mecanismo de medición la separa del modelo Spiral, que no sugiere ninguna forma de validación [@Ceret2013].

### F. Flexibilidad

Los cuatro aportan variabilidad: HCD admite al menos cuatro modelos de proceso; EDA admite distintos brokers y protocolos; DevOps prevé caminos de excepción; GenIA no exige un lenguaje exclusivo.

Se propone **variabilidad explícita por enfoque**: HCD y DevOps son **obligatorios** en toda instancia de la metodología; EDA es **condicional**, se activa solo si el proyecto es distribuido o de tiempo real; GenIA es **condicional**, se activa solo si existen datos confiables sobre los que apoyar la generación. Esta configurabilidad la aleja de los modelos de procedimiento fijo: [@Ceret2013] recoge que modelos como el Waterfall, el Spiral o el modelo en V pueden considerarse procedimientos fijos, y que esa fijeza dificulta adaptarlos a condiciones locales; el Spiral, en particular, no sugiere ninguna variante.

### G. Valor diferencial frente a metodologías actuales

La comparación usa los mismos ejes y gradaciones con que [@Ceret2013] clasifica tres modelos de proceso consolidados. No se compara contra Scrum porque el paper no lo clasifica; hacerlo exigiría una clasificación propia que excede esta primera aproximación.

| Eje / sub-eje | Spiral | RAD | XP | **Propuesta** |
|---|---|---|---|---|
| Incremento | Desarrollo incremental, una entrega final | Número medio (3–6 meses) | Número muy grande | **Grande (1–3 meses)** |
| Iteración | Global | Global y regional | Regional y local | **Local y regional** |
| Retorno (*backwards*) | — | Menciona validación, no define qué hacer si falla | — | **Dos compuertas explícitas de retorno** |
| Roles | — | Más de cinco | Cliente diario; usuarios definen historias | **Más de cinco + dos roles externos formales** |
| Artefactos | Solo artefactos formalizados | ~30 clases no ejecutables en inicialización | No recomienda no ejecutables | **Mixta, con criterio declarado** |
| Tamaño de proyecto | Grandes, sin procedimiento de evaluación | Sin información específica | — | **Declarado: 5–15 personas, con límites de no-uso** |
| Validación | No sugiere ninguna | — | — | **Ausencia declarada + indicadores por eje** |
| Difusión | — | — | Muy bien difundido | **Nula (primera aproximación)** |
| Variabilidad | No sugiere variantes | — | — | **Explícita: dos enfoques obligatorios, dos condicionales** |

Tres diferencias concentran el valor de la propuesta. **Primero**, el retorno explícito con dos compuertas independientes —usuario y rendimiento— frente a modelos que validan sin definir la consecuencia de no validar. **Segundo**, la declaración de límites de uso, incluyendo cuándo *no* aplicarla, frente a modelos que no informan sobre tamaño o tipo de aplicación. **Tercero**, la variabilidad configurable por enfoque, frente a procedimientos fijos difíciles de adaptar a condiciones locales.

La debilidad, declarada sin atenuantes, es la madurez: frente a XP —muy bien difundido [@Ceret2013]— esta propuesta no tiene difusión ni validación empírica. Es precisamente lo que el mecanismo de medición del eje Madurez busca empezar a corregir.

## V. Conclusión

*[pendiente]*

1. Proponemos una respuesta a un vacío metodológico real: El estado del arte confirma que la RA carece de una metodología que integre entrega técnica, reacción a eventos y validación con usuarios como ejes de igual jerarquía, no como anexos opcionales. Con nuestra propuesta argumentamos que es posible tejer estos tres frentes bajo un mismo marco de decisión.
 
2. Las dos compuertas de retorno son el corazón de la propuesta, no un detalle de diseño:  Al declarar evaluación de usuario y pruebas de latencia/resiliencia como gatillos independientes de retroceso, evidenciamos algo que ni Spiral ni RAD resuelven: qué hacer cuando una etapa no se valida. Esta es la diferencia entre iterar porque sí e iterar con una causa raíz identificable. 
 
3. La formalización mixta con criterio declarado supera la falsa dicotomía formal/informal: Frente a XP, que descarta artefactos no ejecutables, y RAD, que los multiplica sin criterio, proponemos una regla simple y defendible: se formaliza lo que cruza frontera entre equipos, se deja semi-formal lo que sirve para explorar. Esto convierte una decisión típicamente arbitraria en una decisión trazable. 

4. La variabilidad configurable —HCD y DevOps obligatorios, EDA y GenIA condicionales— responde directamente a la heterogeneidad del dominio: Un proyecto de RA educativa local no tiene las mismas exigencias que una experiencia colaborativa en tiempo real. De las tres metodologías con las que se comparó (Spiral, RAD, XP), la propuesta es la única que ajusta explícitamente su propio peso según ese contexto, en lugar de imponer un procedimiento fijo, una diferencia de diseño que, como el resto de la propuesta, aún no se ha probado en un caso real.

5. Asumimos la inmadurez de la propuesta como punto de partida, no como debilidad oculta: A diferencia de Spiral, que no sugiere ninguna forma de validación, acompañamos esta primera aproximación con indicadores concretos por eje, retornos disparados, cobertura de contratos, resultados de evaluación, que dejan trazado el camino hacia la validación empírica que hoy nos falta.

6. El trabajo futuro no es abrir más frentes, sino cerrar el que abrimos:  La prioridad inmediata es instrumentar la metodología en un caso real de RA distribuida, medir con los indicadores propuestos y contrastar los resultados contra Spiral, RAD y XP bajo condiciones controladas, el único camino para que esta propuesta deje de ser una aproximación y se convierta en evidencia. 

7. La propuesta traduce cuatro cuerpos de conocimiento dispersos en una sola gramática de decisión:  GenIA, DevOps, EDA y HCD existen hoy como silos con literatura propia, comunidades propias y vocabularios propios; nuestro aporte no es inventar ninguno de los cuatro, sino demostrar que pueden convivir bajo los mismos seis ejes de Céret et al. sin perder su identidad técnica. Esa capacidad de traducción más que cualquier técnica individual es lo que hace escalable la metodología a nuevos enfoques que el dominio RA siga incorporando. 

---

## Referencias

- [@Ceret2013]
- *(añadir fuentes AR y de cada enfoque tras verificación)*
