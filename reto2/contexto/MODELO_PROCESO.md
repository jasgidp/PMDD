# MODELO_PROCESO — especificación canónica

Definición única del modelo de proceso del Equipo 2 para RA. Todo lo que se dibuje en SPEM 2.0, se diga en la
presentación o se escriba en el paper debe coincidir con este archivo.

**Fuente normativa:** paper final del Reto #1 (`reto1/entrega-final/Equipo2_2026_Metodologia_AR_EAFIT.pdf`),
§IV-A a §IV-I. Lo añadido en el Reto #2 se marca **[NUEVO R2]**.

---

> ## ⚠️ FUENTE NORMATIVA — el paper manda sobre este archivo
>
> Versión vigente: **`reto2/paper/pdms_reto2-2.pdf`** (17 pp., secciones I–X, 9 figuras, 8 cuadros,
> 42 referencias). En todo lo que se contradiga, **gana el paper**. Deltas frente a lo escrito más abajo,
> que sigue reflejando el Reto #1:
>
> | Cambio en v2 | Antes (Reto #1) |
> |--------------|-----------------|
> | **11 roles**, cada uno con *decisión exclusiva* + actividades donde es primario + productos de los que responde (Cuadro I) | 9 internos + 2 externos, sin decisión exclusiva declarada |
> | Fases descompuestas en **actividades A1.1 … A7.3** con rol primario nombrado | solo tareas sueltas |
> | **Hitos M1–M4**. M3 marca el fin de la precedencia estricta: a partir de ahí las fases son reservorios de trabajo | no existían |
> | **S1–S7** actividades de apoyo, alineadas con **ISO/IEC/IEEE 12207:2017** (Cuadro IV) | T1–T7 sin anclaje normativo |
> | **CP1–CP4 patrones de proceso reutilizables** (Capability Patterns): microciclo, compuerta de retorno, doble pipeline, ciclo HCD anidado | no existían |
> | Productos de trabajo tipados **Artifact / Deliverable / Outcome** (Cuadro II) | todos genéricos |
> | **Cuatro** familias de indicadores; cadena causal falsable; validación con *stepped-wedge* | dos familias |
> | Cada elemento justificado por **riesgo que reduce / evidencia que produce / qué pasa si se elimina** (Cuadro V) + elementos descartados y por qué | no existía |
> | Tabla de destinos de retorno por causa: G1→F2/F3/F5 · G2→F1/F2/F3/F4 · **G3→siempre F4** | destinos más gruesos |
> | Vocabulario: **pipeline de código / pipeline de contenido** | "cadena" |
>
> Los §1–§11 de abajo siguen siendo válidos como resumen operativo, pero **verificar contra el paper v2**
> antes de usarlos en un entregable.

## 0. Nombre de la metodología

**ARCA — Augmented Reality Continuous Assurance**
*Aseguramiento Continuo para Realidad Aumentada*

Cierra la decisión **D15** del Reto #1, que había quedado aplazada: en el paper final la propuesta se
llamaba solo "la propuesta". A partir de ahora el nombre se usa en el diagrama, la presentación y el paper.

El nombre carga el argumento del método: *continuous* por las tres cadencias anidadas y la entrega continua;
*assurance* por el esquema de compuertas de retorno, que es lo que distingue a ARCA de un proceso ágil normal.

---

## 1. Idea del modelo en una frase

Modelo **incremental con compuertas de retorno prescriptivas**, construido por ingeniería de métodos situacional
sobre siete fases, con **doble cadena de construcción** (código y contenido de augmentación) y **variabilidad
configurable por enfoque** (HCD y DevOps obligatorios; EDA y GenIA condicionales).

### Las cinco decisiones distintivas (son el guion de la defensa)

1. **Cadencias anidadas** — separa la frecuencia con que se *publica* de la frecuencia con que se *valida*.
2. **Compuertas de retorno** — no solo bloquean: **prescriben la fase de destino** y están **asignadas a un rol**.
3. **Roles con autoridad separada** — el *qué* (Product Owner) frente al *cómo* (Líder técnico).
4. **Doble cadena de pipelines** — el contenido de augmentación es componente de primera clase, no un anexo.
5. **Responsabilidad social verificable en compuerta** — con responsable nominado, no como declaración de intenciones.

---

## 2. Cadencias anidadas (el "ciclo")

| Nivel | Duración | Qué lo dispara | Quién decide | Elemento SPEM |
|-------|----------|----------------|--------------|---------------|
| **Integración y entrega continua** | por cambio | cada commit dispara el pipeline (código o contenido) | DevOps (automático) | flujo continuo / herramienta |
| **Microciclo** | **2 semanas fijas** | sesión de apertura PO + Líder técnico sobre el backlog | PO selecciona el trabajo | **Iteración** |
| **Incremento validado** | **1–3 meses (2–6 microciclos)** | solo se declara completo si G1 ∧ G2 (∧ G3 si GenIA) pasan sobre el acumulado | **PO acepta** | **Proceso de liberación / hito** |

Reglas que hay que poder recitar:

- Un despliegue a un ambiente de validación **no** es un microciclo.
- Un microciclo **no** es por sí solo un incremento validado.
- El microciclo **no recorre las siete fases**: selecciona trabajo de las fases activas → **no es una cascada en miniatura**.
- **Al menos un microciclo por incremento validado incluye sesiones de evaluación con usuarios y entrega su informe.**

### Seis elementos de control al cierre de cada microciclo

1. Compilación desplegable del incremento de código.
2. Manifiesto de contenido de augmentación versionado + registro de derechos.
3. Contrato de frontera actualizado y versionado (si cambió).
4. Evidencias de las compuertas ejecutadas, **con la causa registrada de cada retorno**.
5. Registro de decisiones arquitectónicas (ADR).
6. Backlog repriorizado y aceptado por el PO.

> Si un elemento no aplica en ese microciclo, **se registra explícitamente** que no aplica; no se fabrica un
> artefacto artificial. El principio de "entregables fijos" fija **categorías de cierre**, no la obligación de
> poblarlas todas.

---

## 3. Roles

### 3.1 Internos (9)

| Rol | Responsabilidad | Compuerta |
|-----|-----------------|-----------|
| **Product Owner (PO)** | Prioriza el backlog, selecciona el trabajo del microciclo, **único que acepta un incremento como validado** | acepta tras G1∧G2 |
| **Líder técnico** | Decisiones arquitectónicas; arbitra latencia vs. calidad visual vs. coste; responde por el contrato de frontera; **absorbe la arquitectura de eventos cuando EDA está activo**; **decide la fase de destino cuando G1 falla** | decide destino de G1 |
| **Desarrollador RA** | Interacción, tracking, renderizado, integración de activos en la experiencia | — |
| **Desarrollador de servicios** | Lógica de negocio, integraciones y (si EDA) productores/consumidores de eventos | — |
| **Ingeniero DevOps** | Pipelines, ambientes, automatización, observabilidad, promoción a producción | — |
| **Especialista en experiencia de usuario (UX)** | Dirige las actividades de HCD y las evaluaciones con usuarios | coejecuta G2 |
| **Responsable de calidad de integración y rendimiento** | Pruebas de integración, latencia, throughput y resiliencia; **registra la causa del retorno** | **ejecuta G1** |
| **Responsable de derechos y licencias** *(Legal Rights Management)* | Procedencia, licencias y derechos de activos y de contenido generado; **ningún activo entra a la cadena de contenido sin su registro** | coejecuta G2 y G3 |
| **Responsable de contenido** | Prepara, mantiene y versiona los activos de augmentación | coejecuta G3 |

### 3.2 Externos (2)

| Rol | Cuándo interviene |
|-----|-------------------|
| **Usuario final** | Definición del contexto (F1) y **G2** |
| **Responsable de los datos** | **Solo si GenIA está activo** — participa en G3 |

> ⚠️ **GenIA, DevOps, EDA y HCD son enfoques, no roles.** En el diagrama no deben llevar icono de Rol (ver G-06).

### 3.3 Por qué estos roles (argumento para la defensa)

- Nueve roles internos supera a RAD (>5), pero la diferencia sustantiva no es el número: RAD identifica equipos
  paralelos sin decir cómo trabajan juntos. Aquí la coordinación **se ancla en dos artefactos de lectura obligatoria**:
  el **informe de evaluación con usuarios** y el **contrato de frontera**.
- El **responsable de derechos y licencias no existe en Spiral, RAD ni XP**: es la respuesta a que en RA el producto
  incorpora activos de terceros, captura entornos donde aparecen personas y, con GenIA, contenido cuya procedencia
  debe acreditarse.

---

## 4. Fases (F1–F7)

Formato uniforme: **Entrada → Actividades → Roles → Técnicas/Herramientas → Artefactos de salida → Compuerta/retorno → Cuello de botella → Métrica.**

### F1 — Encuadre y contexto de uso · *responsable de modelado: Quinnie*

| Campo | Contenido |
|-------|-----------|
| **Entrada** | Idea, usuarios, entorno físico, restricciones |
| **Actividades/tareas** | Delimitar contexto de uso · Entrevistas y observación contextual · Declarar accesibilidad e inclusión · Acordar alcance del proyecto |
| **Roles** | UX (dirige) · Usuario final · PO (alcance) |
| **Técnicas** | Entrevistas contextuales · Observación · Personas y escenarios · Mapeo colaborativo |
| **Herramientas** | Figma · Repositorio de hallazgos · Herramienta de mapeo colaborativo |
| **Artefactos** | Especificación del contexto de uso · Personas y escenarios · **Declaración de accesibilidad** · Alcance acordado |
| **Enfoques activos** | HCD |
| **Compuerta** | Sin compuerta propia |
| **Retorno entrante** | Desde **G2** si la causa es contexto, privacidad o accesibilidad mal declarada → retoma **UX** (con Usuario final); el **PO** reabre alcance |
| **Cuello de botella** | Mal encuadre: todo lo demás se construye sobre supuestos falsos (el error más caro de corregir tarde) |
| **Métrica** | Coste de cambio de alcance temprano vs. tardío · horas de redescubrimiento de contexto |

### F2 — Requisitos y contratos · *Quinnie*

| Campo | Contenido |
|-------|-----------|
| **Entrada** | Especificación de contexto + alcance (F1) |
| **Actividades/tareas** | Especificar requisitos F/NF · Definir RNF medibles (latencia, precisión de registro, autonomía, privacidad) · Definir contrato de frontera · Catalogar eventos *(solo si EDA)* |
| **Roles** | UX · Líder técnico · Desarrollador de servicios *(si EDA)* |
| **Técnicas** | Especificación de RNF medibles · Diseño orientado a contratos de eventos *(EDA)* |
| **Herramientas** | AsyncAPI · JSON Schema · OpenAPI · UML · C4 · BPMN |
| **Artefactos** | Requisitos F/NF · **Contrato de frontera versionado** (contrato de eventos si EDA; si no, especificación de interfaces entre captura, lógica y presentación — ETSI ARF) · Catálogo de eventos* |
| **Enfoques activos** | HCD · EDA* |
| **Compuerta** | Sin compuerta propia |
| **Retorno entrante** | Desde **G2** o desde fallo de integración por requisitos incompletos/contrato ambiguo → **Líder técnico + UX**; Dev servicios actualiza el contrato |
| **Cuello de botella** | Contrato de frontera mal versionado: los equipos en paralelo se bloquean |
| **Métrica** | % de contratos versionados · horas de espera entre equipos por interfaz no clara |

### F3 — Diseño y arquitectura · *José Manuel*

| Campo | Contenido |
|-------|-----------|
| **Entrada** | Requisitos F/NF + contrato de frontera |
| **Actividades/tareas** | Decidir arquitectura funcional (**ETSI GS ARF 003**) · Definir anclaje espacial (marcadores fiduciales / SLAM / VIO) · Diseñar interfaz espacial · Diseñar pipeline CI/CD |
| **Roles** | Líder técnico (decide) · DevOps · Dev RA · Dev servicios |
| **Técnicas** | Arquitectura de referencia ETSI ARF · Registro de decisiones (ADR) · Infraestructura como código · Heurísticas de diseño espacial |
| **Herramientas** | Jenkins / GitLab CI · Terraform · Ansible · Docker · Unity · C4 |
| **Artefactos** | **ADR** (registro de decisiones arquitectónicas) · **Especificación de pipeline (IaC)** |
| **Enfoques activos** | HCD · EDA* · DevOps |
| **Compuerta** | Sin compuerta propia |
| **Retorno entrante** | Desde **G1** cuando la causa es arquitectónica (latencia de diseño) → **Líder técnico** |
| **Cuello de botella** | Trade-off latencia ↔ calidad visual ↔ coste (asignado explícitamente al Líder técnico) |
| **Métrica** | Coste de infraestructura/pipeline · retrabajo por decisión arquitectónica revertida tras ADR |

### F4 — Activos y prototipado · *Lina*

| Campo | Contenido |
|-------|-----------|
| **Entrada** | Requisitos de experiencia + arquitectura |
| **Actividades/tareas** | Prototipar (fidelidad creciente) · Producir y versionar activos 3D · Generar contenido con GenIA* · Verificar procedencia y licencias |
| **Roles** | UX · Responsable de contenido · Responsable de derechos y licencias · Responsable de los datos* |
| **Técnicas** | Prototipado de fidelidad creciente · Wizard of Oz · Storyboards · **Prompt engineering · RAG · human-in-the-loop · guardrails · generación estructurada · versionamiento de prompts*** |
| **Herramientas** | Figma / Adobe XD · Unity · Git · Servicios de IA · Bases de datos vectoriales |
| **Artefactos** | Prototipos de fidelidad creciente · Storyboards de baja fidelidad · **Activos con derechos aclarados** · **Registro de derechos** · Prompts versionados* |
| **Enfoques activos** | HCD · GenIA* |
| **Compuerta** | **G3*** (solo si GenIA produjo contenido destinado al producto) |
| **Retorno entrante** | **G3** falla → Responsable de contenido + Derechos (+ Datos) · **G2** falla por UX del prototipo → UX · activo sin licencia → Derechos **bloquea la entrada a la cadena** |
| **Cuello de botella** | **El más fuerte del dominio: autoría de contenido** (3D, anotaciones, reglas de interacción). GenIA existe para bajar ese coste, **no para saltarse G3** |
| **Métrica** | Coste por asset · coste de regeneración/rechazo en G3 · tiempo hasta "asset listo para cadena" |

### F5 — Construcción (doble cadena) · *Jhonnatan*

| Campo | Contenido |
|-------|-----------|
| **Entrada** | Arquitectura + activos aprobados |
| **Cadena de CÓDIGO** | Tracking, render e interacción · Implementar eventos* · Aplicar TDD y pruebas de integración · CI: empaquetar candidato de versión — **Dev RA · Dev servicios · DevOps** |
| **Cadena de CONTENIDO** | Preparar, versionar y probar el contenido de augmentación — **Responsable de contenido · Responsable de derechos** |
| **Técnicas** | TDD · Integración continua · Publicación/suscripción · Event streaming · CEP* · Versionado de manifiesto |
| **Herramientas** | Git · Docker · Unity · Kubernetes + Helm · Kafka / RabbitMQ · motores CEP |
| **Artefactos** | **Compilación desplegable** · **Manifiesto de contenido** (+ registro de derechos) · Servicios de eventos desplegados* · **Candidato de versión** |
| **Enfoques activos** | DevOps · EDA* · GenIA* |
| **Compuerta** | **G3*** para todo contenido generado antes de entrar a la cadena de despliegue |
| **Retorno entrante** | Bug técnico o G1→implementación → Dev RA / Dev servicios / DevOps · contenido o derechos → Contenido + Derechos |
| **Cuello de botella** | **Las dos cadenas deben llegar juntas**: si el código está listo y el contenido no (o al revés), el incremento se frena |
| **Métrica** | *Idle time* entre cadenas · coste de build fallido · coste de contenido bloqueado en G3 |

### F6 — Verificación y compuertas · *Alejo*

| Campo | Contenido |
|-------|-----------|
| **Entrada** | Build integrado + manifiesto + evidencias |
| **Actividades/tareas** | Pruebas de rendimiento y resiliencia · Evaluación con usuarios (SUS, NASA-TLX) · Verificar privacidad y accesibilidad · Obtener consentimiento informado |
| **Roles** | Calidad (técnico) · UX · Derechos · Usuario final |
| **Técnicas** | Pruebas de latencia/throughput/resiliencia · Pruebas de usabilidad · Evaluación heurística (Nielsen) · SUS · NASA-TLX · Consentimiento informado |
| **Herramientas** | Plataformas de prueba de usabilidad remota · herramientas de carga y observabilidad |
| **Artefactos** | **Informe de evaluación con usuarios (con métricas)** · Evidencias técnicas · Evidencias de responsabilidad social · Registro de causa de retorno |
| **Enfoques activos** | DevOps · EDA* · HCD |
| **Compuerta** | **G1 (rendimiento)** y **G2 (experiencia + responsabilidad social)** |
| **Salida** | A **F7 solo si G1 ∧ G2 pasan** (∧ G3 si hubo GenIA) |
| **Cuello de botella** | Diferir la evaluación con usuarios — el modelo lo prohíbe: **≥1 microciclo con usuarios por incremento** |
| **Métrica** | Coste de retorno = horas rehechas × tarifa · nº de retornos por compuerta y por incremento |

### F7 — Despliegue, operación y evolución · *Alejo*

| Campo | Contenido |
|-------|-----------|
| **Entrada** | Incremento que ya superó las compuertas |
| **Actividades/tareas** | Promover a producción por ambientes · Monitorear telemetría de campo · Aceptar incremento y repriorizar backlog |
| **Roles** | DevOps (despliega) · PO (acepta) |
| **Técnicas** | Promoción escalonada por candidatos de versión · convenciones de registro de cambios · aseguramiento de calidad operacional |
| **Herramientas** | Kubernetes · Prometheus / Grafana · HashiCorp Vault |
| **Artefactos** | **Release desplegado** · **Telemetría de campo** · **Backlog repriorizado** |
| **Enfoques activos** | DevOps |
| **Compuerta** | Sin compuerta propia (las compuertas ya se superaron en F6) |
| **Retorno entrante** | Incidente en campo → DevOps + Líder técnico · si es de producto/UX → PO + UX reabren backlog (puede volver a F1–F6) |
| **Cuello de botella** | Promover a producción sin compuertas (el modelo lo impide por construcción) |
| **Métrica** | Defectos escapados a producción · coste de rollback · frecuencia de promociones exitosas |

`*` = elemento condicional según el enfoque activado (§6).

---

## 5. Compuertas de retorno

> Se usa **compuerta de retorno** y no *puerta de calidad* porque el elemento **no solo autoriza o bloquea el
> avance: prescribe la fase de destino del retroceso según la causa registrada**. Esa es la diferencia sustantiva
> frente a Spiral y RAD, que mencionan validación pero no dicen qué hacer cuando una etapa no se valida.

| Compuerta | Verifica | Ejecuta | Fase | Destino del retorno |
|-----------|----------|---------|------|---------------------|
| **G1 — Rendimiento** | Latencia, throughput y resiliencia del flujo de datos y del renderizado. **Obligatoria aunque EDA no esté activo**: la latencia de registro y renderizado es restricción inherente a la RA | Responsable de calidad de integración y rendimiento (registra la causa); **el Líder técnico elige el destino** | F6 | **F3** (diseño) o **F5** (implementación) |
| **G2 — Experiencia y responsabilidad social** | Requisitos de uso mediante evaluación con usuarios + obligaciones de responsabilidad social (§8) | UX + Responsable de derechos, **con participación del usuario final** | F6 | **F1**, **F2** o **F4** según la causa |
| **G3 — Generación** *(condicional)* | Calidad, trazabilidad y **procedencia** del contenido generado | Responsable de contenido + Responsable de derechos, **con participación del responsable de los datos** | **F4 y F5** (toda fase en que GenIA produzca contenido para el producto) | **F4** o **F5** |

**Regla dura:** ningún contenido generado entra a la cadena de despliegue sin superar G3.
**Regla dura:** el incremento no se declara validado sin G1 ∧ G2.

> **G1 y G2 no son sustituibles entre sí.** Un incremento que supera G1 (latencia excelente, tracking estable,
> alta disponibilidad, cero defectos críticos) pero falla G2 (el usuario se desorienta, aumenta su carga
> cognitiva o corre riesgo físico) **no es un producto exitoso**: es un retorno a F1, F2 o F4.
> En RA, **calidad técnica sin experiencia humana validada no es calidad completa** — ese es el diferencial
> del método, y el profesor lo señaló como tal en el feedback al Reto #1.

### Mapa rápido: qué falla → quién retoma → a dónde vuelve

| Qué falla | Quién retoma | Vuelve a |
|-----------|--------------|----------|
| Contexto / accesibilidad / privacidad | UX (+ Usuario final, Derechos) | F1 / F2 |
| Contrato / requisitos | Líder técnico + UX | F2 |
| Arquitectura / latencia de diseño | Líder técnico | F3 |
| Asset / derechos / GenIA | Contenido + Derechos (+ Datos) | F4 / F5 |
| Código / integración | Dev RA / Dev servicios / DevOps | F5 |
| **G1** rendimiento | Calidad registra la causa; **Líder técnico decide** | F3 o F5 |
| **G2** UX + responsabilidad social | UX + Derechos | F1, F2 o F4 |
| Producción / incidente en campo | DevOps + PO | F7 → backlog |

---

## 6. Variabilidad: qué enfoque se activa y cuándo

| Enfoque | Condición | Qué añade al activarse |
|---------|-----------|------------------------|
| **HCD** | **Obligatorio** en toda instancia | G2, evaluación con usuarios, rol de usuario final, artefactos de contexto |
| **DevOps** | **Obligatorio** en toda instancia | CI/CD, IaC, observabilidad, promoción por ambientes |
| **EDA** | **Condicional**: el sistema distribuye estado entre componentes/clientes, o hay restricciones de tiempo real | Contrato de eventos versionado, catálogo de eventos, tareas de eventos en F2/F3/F5. En su ausencia la coordinación recae en el contrato de frontera genérico |
| **GenIA** | **Condicional**: existen datos confiables sobre los que apoyar la generación | **Compuerta G3** + rol externo *Responsable de los datos* + prompts versionados |

El enfoque general del método es **ingeniería de métodos situacional** (Henderson-Sellers & Ralyté): el método se
construye a partir de componentes configurables según el contexto. Eso es lo que aleja la propuesta de los modelos
de procedimiento fijo (Waterfall, Spiral, modelo en V).

---

## 7. Artefactos y criterio de formalización

**Criterio explícito:** *se formaliza lo que cruza una frontera entre equipos o entra al producto; se deja
semi-formal lo que sirve para explorar.*

| Formalización | Artefactos |
|---------------|------------|
| **Formales (obligatorio)** | Contrato de frontera (AsyncAPI / JSON Schema) · Especificación de pipeline · Manifiesto de contenido de augmentación · Registro de derechos · Informe de evaluación con métricas · **Prompts versionados** (gobiernan una salida que entra al producto → deben ser reproducibles y auditables) |
| **Semi-formales** | Personas y escenarios · Storyboards · Mapas de recorrido · Prototipos de exploración |

Posición intermedia entre **XP** (no recomienda artefactos no ejecutables) y **RAD** (≈30 clases de artefacto solo
en su fase de inicialización). Lo distintivo no es la cantidad, **es el criterio de frontera**.

---

## 8. Actividades transversales / de soporte **[NUEVO R2]**

El enunciado las pide explícitamente y el paper las tiene dispersas. Se consolidan aquí como **procesos de apoyo
que atraviesan F1–F7** (en SPEM: banda transversal bajo el flujo de fases).

| # | Proceso de apoyo | Responsable | Atraviesa | Artefacto que produce |
|---|------------------|-------------|-----------|-----------------------|
| T1 | **Gestión de derechos y licencias** | Responsable de derechos | F4–F7 | Registro de derechos (condición de entrada a la cadena de contenido) |
| T2 | **Gestión de configuración y versionado** (código, contenido, contratos, prompts) | DevOps + Resp. contenido | F2–F7 | Manifiesto versionado · contratos versionados |
| T3 | **Planificación y coordinación del microciclo** | PO + Líder técnico | todas | Backlog priorizado · seis elementos de control de cierre |
| T4 | **Gestión de riesgos de IA*** (sesgo, información incorrecta, propiedad intelectual) — perfil de IA generativa del marco NIST AI 600-1 | Resp. de los datos + Derechos | F4–F5 | Evidencia de trazabilidad y procedencia (entrada a G3) |
| T5 | **Observabilidad y operación** | DevOps | F5–F7 | Telemetría de campo · tablero de indicadores |
| T6 | **Responsabilidad social** (§9) | UX + Derechos | F1–F7, **verificada en G2/G3** | Declaración de accesibilidad · consentimiento informado · registro de derechos |
| T7 | **Medición del proceso** (§10) | Líder técnico + Calidad | todas | Tablero de instrumentación y resultado |

---

## 9. Responsabilidad social (obligación transversal, no un eje de la taxonomía)

Principio: **tratar las preocupaciones éticas como requisitos del sistema, no como una revisión posterior**
(IEEE Std 7000-2021).

| Grupo | Obligación | Responde | Se verifica en |
|-------|-----------|----------|----------------|
| **Protección de personas y entorno** | La RA captura el entorno de forma continua → la privacidad de terceros no participantes es **requisito**, no consideración. La oclusión indebida del entorno y la sobrecarga de atención son **riesgos de seguridad física**, no solo defectos de usabilidad. Consentimiento informado en toda sesión de evaluación | UX | **G2** |
| **Accesibilidad e inclusión** | Declarar **en F1** qué capacidades sensoriales y motoras supone la experiencia y qué alternativas ofrece a quien no las tiene | UX | **G2** |
| **Integridad del contenido y derechos** | Procedencia y licencia de activos de terceros; derechos de imagen de personas capturadas o representadas; con GenIA, trazabilidad del contenido generado y riesgos de sesgo/IP | Responsable de derechos | **G3** (generado) y **G2** (conjunto desplegado) |

---

## 10. Métricas

### 10.1 Del paper — dos familias

| Familia | Indicadores |
|---------|-------------|
| **Instrumentación** (¿se ejecuta el proceso como se definió?) | Frecuencia de integración y entrega a ambientes de validación · frecuencia de promociones a producción · entregables completos por microciclo · **retornos disparados por cada compuerta** · cobertura de contratos de frontera versionados |
| **Resultado** (¿produce mejores productos?) | Defectos escapados a producción por incremento · retrabajo (trabajo rehecho tras un retorno) · puntuación de usabilidad (**SUS**) · latencia percibida en la augmentación |

**Diseño mínimo de validación:** estudio de caso múltiple en proyectos comparables, contrastando estas variables
frente a un proceso ágil sin compuertas diferenciadas.

### 10.2 Lectura económica **[NUEVO R2]**

| Métrica | Fórmula práctica |
|---------|------------------|
| Coste de retorno | horas rehechas × coste/hora |
| Coste de autoría de contenido | horas (o $ GenIA + revisión humana) por asset aceptado |
| Coste de bloqueo entre cadenas | horas *idle* código ∩ contenido |
| Coste evitado por G2/G3 | incidentes legales/UX que no llegaron a producción |
| Coste por incremento validado | suma de microciclos hasta G1 ∧ G2 OK |

### 10.3 Coste de coordinación y balance neto **[NUEVO R2 — feedback del profesor]**

> *"Demostrar empíricamente que esta estructura reduce retrabajo, defectos y tiempo de validación en una
> magnitud superior al **costo de coordinación** que introduce."* — feedback al paper final del Reto #1.

El paper medía el **beneficio** del método pero no el **coste que el propio método introduce**. Sin los dos
lados no hay demostración posible. Se añade la tercera familia de indicadores:

| Coste que introduce el método | Cómo se mide |
|-------------------------------|--------------|
| Ejecución de compuertas | horas-persona en G1 + G2 + G3 por incremento |
| Mantenimiento de contratos de frontera | horas de versionado y negociación de contratos |
| Entregables fijos del microciclo | horas dedicadas a los seis elementos de control |
| Coordinación entre nueve roles | horas de sesiones de apertura, revisión y firma multi-rol |
| Registro de derechos y trazabilidad | horas por asset acreditado |

**Balance neto por incremento validado:**

```
Beneficio  =  (retrabajo evitado) + (defectos escapados evitados × coste de falla en campo)
              + (tiempo de validación ahorrado) + (incidentes legales/UX evitados)
Coste      =  horas de compuertas + contratos + entregables de microciclo + coordinación multi-rol
Balance    =  Beneficio − Coste          → la hipótesis del método es Balance > 0
```

**Hipótesis falsable que queda declarada:** frente a un proceso ágil sin compuertas diferenciadas, el método
reduce retrabajo, defectos escapados y tiempo hasta validación en una magnitud **superior** al coste de
coordinación que añade. El diseño mínimo para contrastarla es el estudio de caso múltiple de §10.1.

---

### 10.4 Los cuatro cuellos de botella que más cuestan

1. **Autoría de contenido (F4/F5)** — el más caro del dominio.
2. **Desalineación código ↔ contenido (F5)** — una cadena espera a la otra.
3. **G1 latencia** — los retornos técnicos son caros si el diseño ya venía mal.
4. **G2 diferida** — validar con usuarios tarde multiplica el retrabajo.

---

## 11. Trazabilidad con los seis ejes de la espina (Céret et al.)

| Eje | Decisión del modelo | Dónde se ve en el diagrama |
|-----|---------------------|----------------------------|
| **Ciclo** | Microciclo de 2 semanas (grado más fino de la escala) + incremento validado; retorno **nominado a un rol y con fase de destino** | Iteración + compuertas + flechas `[falla: …]` |
| **Colaboración** | 9 roles internos + 2 externos; autoridad separada PO/Líder técnico; rol de derechos | Carriles/roles por fase |
| **Artefactos** | Formalización mixta con criterio de frontera | Productos de trabajo, marcados formal/semi-formal |
| **Uso recomendado** | Ámbito declarado **y casos de no-uso** | Nota en la lámina |
| **Madurez** | Primera aproximación no validada; se operacionaliza el instrumento de medición | Tablero de indicadores (T7) |
| **Flexibilidad** | Variabilidad por enfoque: HCD/DevOps obligatorios, EDA/GenIA condicionales | Marcas `*` de condicionalidad |
