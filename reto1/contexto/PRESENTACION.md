# PRESENTACION — socialización y PPT corregida

---

## Parte I — Socialización (40%)

**Última actualización:** 2026-08-14  
**Estado:** guion alineado a E3–E6 + investigación en `BORRADOR_MAESTRO.md`  
**Fuente de verdad del contenido:** paper (dominio §II; enfoques §III).  
**Textos de los compañeros:** “Aporta” y “Uso en RA” → **razón de elección (B5)**; el resto se usa donde encaja en el E4.

**Presentación visual (3 slides HTML):** [`presentacion/index.html`](../presentacion/index.html) — abrir en navegador a pantalla completa (`F`). Navegación: `←` `→` / espacio. Expandibles para el detalle.

**Enfoques (D26):** GenIA · DevOps · EDA · HCD.

Tras feedback de clase → **Parte II**.

---

## Diapositiva 0 — Portada

- Título: *Primera aproximación metodológica para desarrollo de software en realidad aumentada basada en taxonomía de procesos* *(o el título vigente del borrador)*  
- Equipo 2 — Realidad aumentada  
- Universidad EAFIT — Procesos Modernos de Desarrollo de Software  
- Autores: Quinnie Nastasja Villarreal Aragon · Jose Manuel Carvajal · Jonathan Sandoval · Lina Ballesteros · Alejandro Ríos *[orden pendiente]*

---

## Diapositiva 1 — Agenda

1. Dominio AR — estado actual (E3)  
2. Enfoques: GenIA, DevOps, EDA, HCD (E4)  
3. Razón de elección  
4. Espina de pescado — 6 ejes (E5)  
5. Valor diferencial  
6. Cierre  

---

## Bloque A — Dominio (Quinnie) — checklist E3

*Contenido tomado de `BORRADOR_MAESTRO.md` §II. Fuentes en cada viñeta.*

### Diapositiva A1 — Qué es RA y estado de desarrollo

**E3:** *Qué es, su estado de desarrollo*

**En lámina**
- **Qué es (Azuma):** sistema que (i) combina objetos reales y virtuales en un entorno real, (ii) interactúa en tiempo real y (iii) registra (alinea) objetos reales y virtuales en 3D [@Azuma1997]. Definición agnóstica al display [@Azuma2001].  
- **Continuo RM:** RA dentro del continuum realidad–virtualidad (Milgram); enriquecimiento del mundo real con contenido digital [@Milgram1994], [@Billinghurst2015].  
- **Estado de desarrollo — madurez parcial:**
  - De laboratorio → móviles y *wearables* [@Azuma1997], [@Azuma2001].  
  - ISMAR: de tracking/interacción/display → más evaluación, rendering, móvil y 3D [@Zhou2008], [@Kim2018].  
  - Hoy: adopción masiva, ética, accesibilidad; retos en display, tracking e interacción [@Goh2023], [@Syed2023], [@Devagiri2024].  
  - Viable en móvil e industria/educación; *see-through* “indistinguible” y adopción general aún abiertos [@Goh2023], [@Devagiri2024].

---

### Diapositiva A2 — Cómo se abordan proyectos + metodologías

**E3:** *Cómo se abordan proyectos · Qué metodologías se utilizan*

**En lámina — Abordaje de proyectos** (sistemas socio-técnicos: HW + SW + contenido) [@Schmalstieg2016], [@Devagiri2024]
1. Caso de uso y contexto [@NIST2022], [@Sereno2022]  
2. Plataforma / display (móvil, HMD, colaborativo) [@Syed2023], [@Devagiri2024]  
3. Anclaje espacial (marcadores, SLAM, VIO…) [@Kim2018], [@Syed2023]  
4. Interfaz espacial e interacción [@Kourouthanassis2015], [@Endsley2017]  
5. Implementación iterativa + evaluación con usuarios [@NIST2022], [@Dunser2011]  
(+ en colaborativa: espacio, tiempo, roles, *awareness* [@Billinghurst2002], [@Sereno2022])

**En lámina — Metodologías (títulos + ancla)**  
*No hay una única metodología estándar para RA.*
- **MDLC adaptado a RA** [@Roedavan2025]  
- **HCD / ISO 9241-210** [@ISO9241210] + usabilidad RA [@NIST2022]  
- **HCI / evaluación específica de RA** [@Dunser2011], [@Dunser2007], [@Endsley2017]

---

### Diapositiva A3 — Principios de diseño/arquitectura + ciclo de vida

**E3:** *Principios de diseño y arquitectura · Ciclo de vida*

**En lámina — Principios de diseño** [@Kourouthanassis2015], [@Endsley2017], [@Dunser2007], [@Sereno2022]
- Registro espacial estable y baja latencia percibida  
- Información aumentada clara sin ocluir lo relevante  
- Interacción alineada a dispositivo y usuario  
- Confort, seguridad, privacidad, continuidad  
- *Awareness* y coordinación en escenarios colaborativos  

**En lámina — Arquitectura** [@Reicher2003], [@MacWilliams2004], [@ETSI-ARF003], [@Schmalstieg2016]
- Capas típicas: captura/sensado → tracking/mapeo → modelo de entorno → lógica → render → interacción  
- Requisitos transversales: tiempo real y baja latencia E2E  
- Ref.: arquitectura funcional ETSI ARF; patrones MacWilliams  

**En lámina — Ciclo de vida (iterativo)** [@Roedavan2025], [@Devagiri2024], [@ISO9241210], [@NIST2022]
1. Ideación y análisis de contexto  
2. Especificación de requisitos (funcionales y NFR: latencia, registro, privacidad…)  
3. Diseño conceptual y arquitectónico  
4. Activos y prototipado  
5. Implementación (núcleo / visual / interacción)  
6. Evaluación iterativa (técnica + usabilidad)  
7. Despliegue, operación y evolución  

---

## Bloque B — Enfoques (E4)

> **Estructura fija por enfoque (lo que pide el profesor):**  
> 1. Qué es · 2. Relación con IS · 3. Cómo se ejecutan proyectos · 4. Técnicas y herramientas · 5. Lenguajes de modelado · 6. Métodos  
> **“Aporta” y “Uso en RA” no van aquí** → van a **B5 Razón de elección**.

---

### Diapositiva B1 — GenIA (Jose Manuel)

**Fuente:** §III.A · *Técnicas/herramientas del mensaje del equipo encajan aquí.*

**En lámina**
1. **Qué es:** GenIA usa modelos que generan contenido nuevo a partir de patrones aprendidos en grandes volúmenes de datos; en SW apoya requisitos, diseño, código, pruebas, documentación y mantenimiento.  
2. **Relación con IS:** apoya etapas del ciclo de vida de software; no sustituye ingeniería — exige datos, evaluación, trazabilidad y supervisión humana [@NISTGenAI].  
3. **Cómo se ejecutan proyectos:** proceso iterativo controlado: problema → preparar/validar datos → diseñar → MVP → evaluar → desplegar/monitorear; para datos actualizados: **RAG** + evaluación de calidad [@GoogleRAG].  
4. **Técnicas y herramientas:** prompt engineering · few-shot · RAG · guardrails · HITL · evaluación auto/humana · versionamiento de prompts; Python/TS/Java, servicios de IA, DBs vectoriales, Git, Docker, observabilidad; marco **NIST AI RMF** (perfil GenAI) [@NISTGenAI].  
5. **Lenguajes de modelado:** UML · BPMN · C4 · ERD · OpenAPI · JSON Schema *(no hay lenguaje exclusivo)*.  
6. **Métodos:** Agile / Scrum-Kanban · DevOps / MLOps / DevSecOps · Design Thinking · Lean Startup · TDD · AI Risk Management.

---

### Diapositiva B2 — DevOps (Jonathan)

**Fuente:** §III.B · *Técnicas/herramientas del mensaje del equipo encajan aquí.*

**En lámina**
1. **Qué es:** enfoque que acorta el tiempo entre un cambio y su operación en producción, manteniendo calidad, vía colaboración dev–ops, automatización y entrega continua [@Bass2015], [@Jabbari2016].  
2. **Relación con IS:** articula prácticas (CI/CD, IaC, monitoreo) que **condicionan arquitectura y operación** [@Bass2015], [@Jabbari2016].  
3. **Cómo se ejecutan proyectos:** pipelines lint → build → test → release → deploy; contenedores + registro; promoción con *release candidates* y staging/producción; QA multi-rol (ops, ingeniería, contenido); dual pipeline **código + contenido/instrucciones** de augmentación. Referente: augmentación gráfica en tiempo real sobre video broadcast *(sin detalle industrial propietario en lámina)*. Transferible a AR por entrega repetible de SW + contenido [@Vaquero2020].  
4. **Técnicas y herramientas:** CI/CD · IaC · contenedores · registros · secretos · observabilidad · pruebas automatizadas; p. ej. GitLab CI / GitHub Actions · Docker/Kubernetes · Terraform · Prometheus/Grafana.  
5. **Lenguajes de modelado / especificación:** YAML de pipelines · diagramas de flujo de aplicación · IaC · esquemas JSON de artefactos de contenido.  
6. **Métodos:** entrega continua con RC · commits convencionales · QA operacional previo a producción.

---

### Diapositiva B3 — Event Driven Architecture (Lina)

**Fuente:** §III.C · *Definición + técnicas/herramientas del mensaje del equipo.*

**En lámina**
1. **Qué es:** estilo arquitectónico donde componentes desacoplados producen, reciben y procesan **eventos** de forma asíncrona (productor–consumidor vía bus/broker) [@Cabane2024].  
2. **Relación con IS:** afecta diseño, calidad, despliegue y observabilidad; combinable con microservicios / DDD-CQRS; **no garantiza** por sí sola mejor latencia o menor consumo vs monolito — hay que evaluar por contexto [@Cabane2024].  
3. **Cómo se ejecutan proyectos:** identificar eventos + productores/consumidores → contratos y reglas → implementar → validar funcionalidad, latencia, throughput y resiliencia → desplegar → monitorear [@RosaBilbao2023].  
4. **Técnicas y herramientas:** Publish/Subscribe · Event Streaming · CEP; Kafka · RabbitMQ · Azure Service Bus · Node-RED · motores CEP *(mensaje equipo: Kafka, RabbitMQ, AsyncAPI)*.  
5. **Lenguajes de modelado:** UML (secuencia/componentes) · modelos de eventos · **AsyncAPI** (JSON/YAML) [@AsyncAPI].  
6. **Métodos:** diseño orientado a contratos de eventos · modelado de patrones CEP · validación iterativa (integración, rendimiento, resiliencia).

*(Opcional visual)* Producer → Event bus → Render AR / Analítica / Estado compartido.

---

### Diapositiva B4 — Human-Centered Design (Alejandro)

**Fuente:** §III.D · *Definición + técnicas/herramientas del mensaje del equipo.*

**En lámina**
1. **Qué es:** diseño de sistemas interactivos centrado en usuarios, necesidades y contexto de uso; **normalizado** en ISO 9241-210 (6 principios + 4 actividades cíclicas) [@ISO9241210].  
2. **Relación con IS:** *Human-Centered Software Engineering* — usabilidad en el ciclo de vida, no cosmética final [@Seffah2005]; usabilidad como NFR medible y evaluación con retorno a etapas anteriores [@Ferre2005].  
3. **Cómo se ejecutan proyectos:** familia de modelos (Star, ISO 13407, Usage-Centered Design, Usability Engineering Lifecycle) [@Ferre2005]; ciclo: entender contexto → especificar requisitos → producir soluciones → evaluar → iterar (retorno si no cumple) [@ISO9241210].  
4. **Técnicas y herramientas:** entrevistas contextuales · observación · personas y escenarios · prototipado · pruebas de usabilidad · heurísticas [@Nielsen1994]; SUS · NASA-TLX.  
5. **Lenguajes de modelado:** ConcurTaskTrees [@Paterno2000] · IFML [@OMG-IFML] *(en industria también artefactos semi-formales: personas, journey, storyboards)*.  
6. **Métodos:** prototipado de fidelidad creciente · evaluación heurística y empírica · retorno explícito desde evaluación.

---

### Diapositiva B5 — Razón de elección (“Aporta” + “Uso en RA”)

**Quién:** cierre del bloque B · **Aquí va lo que mandaron los muchachos.**

| Enfoque | Aporta | Uso en RA / por qué lo elegimos |
|---------|--------|----------------------------------|
| **GenIA** | Ciclo Problema→Datos→MVP→Evaluación→Despliegue; HITL permanente; adopción gradual | Datos confiables y actualizados · RAG · gestión de riesgos [@NISTGenAI]; productividad de ingeniería con control |
| **DevOps** | Ciclos de entrega más cortos y repetibles; menos fricción dev/ops; calidad en el pipeline (CI/CD, IaC, monitoreo) | Iterar con seguridad operativa sobre **software y contenido gráfico** (tiempo real, componentes heterogéneos, despliegues frecuentes) [@Vaquero2020], [@Bass2015] |
| **EDA** | Escalabilidad, modularidad y reacción rápida ante cambios | Experiencias **distribuidas, colaborativas y en tiempo real**; SARA (eventos en AR colaborativa) [@Vaquero2020], [@Cabane2024], [@Oberhauser2023] |
| **HCD** | Usabilidad como requisito medible; evaluación que puede devolver el diseño a etapas anteriores | Requisitos inmaduros y contexto de uso incierto (típico de RA); déficit de métricas/validación de usuario en AR [@Graser2024], [@Picardi2024], [@ISO9241210] |

- Rúbrica: **DevOps + GenIA** obligatorios; EDA + HCD completan el set.  
- Se articulan en la **espina** (siguiente bloque), no como silos.

---

## Bloque C — Espina de pescado (E5 + E6)

### Diapositiva C1 — Visión (6 ejes)

**Base:** [@Ceret2013]  
Ciclo · Colaboración · Artefactos · Uso recomendado · Madurez · Flexibilidad  
→ *Primera aproximación metodológica para SW en RA*

### Diapositiva C2 — Ciclo + Colaboración

- **Ciclo:** incremental; dos compuertas de retorno — (1) usuarios (HCD) · (2) latencia/resiliencia (EDA); GenIA evalúa antes de desplegar; DevOps: RC + promoción por ambientes.  
- **Colaboración:** usuario como rol externo (HCD); QA multi-rol (DevOps); contratos de eventos (EDA); HITL permanente (GenIA).

### Diapositiva C3 — Artefactos + Uso recomendado

- **Artefactos:** formalización mixta (pipelines/esquemas DevOps–EDA; semi-formales HCD; prompts/datasets GenIA).  
- **Uso:** entrega frecuente + componentes heterogéneos y/o incertidumbre de requisitos.  
- **No uso:** AR pequeña/local (EDA de más); requisitos cerrados y contexto conocido (HCD de más).

### Diapositiva C4 — Madurez + Flexibilidad

- **Madurez:** HCD y DevOps altos; EDA media-alta (menos docs AR); GenIA emergente. Propuesta = primera aproximación.  
- **Flexibilidad:** HCD + DevOps **obligatorios**; EDA + GenIA **condicionales**.

---

## Bloque D — Valor diferencial (E6)

### Diapositiva D1

Frente a Spiral / RAD / XP [@Ceret2013]: límites de uso explícitos, **dos compuertas de retorno** (usuario + performance) y variabilidad (fijo vs condicional). Integra DevOps + EDA + GenIA + HCD en un solo andamiaje de 6 ejes.

---

## Diapositiva final — Preguntas / siguientes pasos

- Preguntas  
- Siguiente: paper IEEE + PPT corregida tras feedback  

---

## Bloque R — Referencias (socialización)

> En PPT usar **fuente pequeña** (14–16 pt). Si no caben, partir en R1–R3 como abajo.  
> Formato corto para diapositiva; la lista IEEE completa está en `FUENTES.md` / paper.

### Diapositiva R1 — Referencias · Dominio AR

1. R. T. Azuma, “A survey of augmented reality,” *Presence*, 1997.  
2. R. Azuma et al., “Recent advances in augmented reality,” *IEEE CG&A*, 2001.  
3. P. Milgram and F. Kishino, “A taxonomy of mixed reality visual displays,” *IEICE*, 1994.  
4. M. Billinghurst, A. Clark, and G. Lee, “A survey of augmented reality,” *Found. Trends HCI*, 2015.  
5. F. Zhou et al., “Trends in AR tracking, interaction and display,” *IEEE ISMAR*, 2008.  
6. K. Kim et al., “Revisiting trends in AR research (2008–2017),” *IEEE TVCG*, 2018.  
7. Y. Goh et al., “Wearable augmented reality…,” *IEEE TVCG*, 2023.  
8. T. A. Syed et al., “In-depth review of augmented reality…,” *Sensors*, 2023.  
9. J. S. Devagiri et al., “The essentials… get started in AR,” *IEEE Access*, 2024.  
10. D. Schmalstieg and T. Höllerer, *Augmented Reality: Principles and Practice*, 2016.  
11. M. Billinghurst and H. Kato, “Collaborative augmented reality,” *CACM*, 2002.  
12. M. Sereno et al., “Collaborative work in augmented reality,” *IEEE TVCG*, 2022.  
13. R. Roedavan et al., “A framework… MDLC,” *JIIG*, 2025.  
14. Y.-Y. Cho et al., *AR Usability Evaluation Framework* (NIST IR 8422), 2022.  
15. ISO 9241-210:2019, *Human-centred design for interactive systems*.  
16. A. Dünser and M. Billinghurst, “Evaluating AR systems,” in *Handbook of AR*, 2011.  
17. A. Dünser et al., “Applying HCI principles to AR systems design,” 2007.  
18. T. C. Endsley et al., “AR design heuristics…,” *HFES*, 2017.  
19. P. E. Kourouthanassis et al., “Demystifying the design of mobile AR…,” *MTA*, 2015.  
20. T. Reicher et al., “Software architectures for AR systems,” 2003.  
21. A. MacWilliams et al., “Design patterns for AR systems,” *MIXER*, 2004.  
22. ETSI GS ARF 003, *AR framework architecture*, 2023.

### Diapositiva R2 — Referencias · Enfoques (GenIA, DevOps, EDA, HCD)

**GenIA**  
23. NIST, *AI Risk Management Framework: Generative Artificial Intelligence Profile* [@NISTGenAI].  
24. Google, *Retrieval-Augmented Generation (RAG)* — documentación / guía [@GoogleRAG].  

**DevOps**  
25. L. Bass, I. Weber, and L. Zhu, *DevOps: A Software Architect’s Perspective*, 2015.  
26. R. Jabbari et al., “What is DevOps? A systematic mapping study…,” *XP Workshops*, 2016.  
27. D. Vaquero-Melchor et al., “SARA: … collaborative augmented reality,” *Appl. Sci.*, 2020.

**EDA**  
28. H. Cabane and K. Farias, “On the impact of event-driven architecture…,” *FGCS*, 2024.  
29. J. Rosa-Bilbao et al., “CEPEDALoCo…,” *Internet of Things*, 2023.  
30. R. Oberhauser, “VR-EDStream+EDA…,” *eKNOW*, 2023.  
31. AsyncAPI Initiative, *AsyncAPI Specification* v3.x.

**HCD**  
32. ISO 9241-210:2019 *(también dominio)*.  
33. A. Seffah et al., Eds., *Human-Centered Software Engineering*, 2005.  
34. X. Ferre et al., “Which, when and how usability techniques…,” 2005.  
35. S. Graser et al., “UX evaluation of AR: a systematic literature review,” *CENTRIC*, 2024.  
36. A. Picardi and G. Caruso, “User-centered evaluation framework… AR,” *MTI*, 2024.  
37. J. Nielsen, “Heuristic evaluation,” 1994.  
38. F. Paternò, *Model-Based Design…* (ConcurTaskTrees), 2000.  
39. OMG, *IFML* 1.0, 2015.

### Diapositiva R3 — Referencias · Espina / propuesta

40. E. Céret et al., “A taxonomy of design methods process models,” *Inf. Softw. Technol.*, 2013.  
    https://doi.org/10.1016/j.infsof.2012.11.002  

*Lista completa y DOIs:* `contexto/FUENTES.md`

---

## Checklist

| Ítem | Estado |
|------|--------|
| A1–A3 dominio E3 + fuentes | Lleno desde §II |
| B1–B4 enfoques E4 completo | Lleno desde §III; técnicas/herramientas de los mensajes |
| B5 razón = Aporta + Uso en RA | Lleno con textos del equipo + citas |
| C–D espina y diferencial | Desde §IV |
| R1–R3 referencias | Listo (formato corto PPT) |
| Pasar a PPTX | Pendiente |

---

## Parte II — PPT corregida (anexa al 60%)

**Estado:** pendiente tras feedback de clase.

| # | Observación | Quién | Fecha | Cómo se corrigió |
|---|-------------|-------|-------|------------------|
| | *[aún no hay feedback]* | | | |
