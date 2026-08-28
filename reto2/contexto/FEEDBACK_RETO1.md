# FEEDBACK del profesor — Reto #1 (sobre el paper final)

Recibido tras la entrega final del Reto #1. **Es la fuente obligatoria de la diapositiva 3** del Reto #2
(*"presentar la espina de pescado, haciendo hincapié en los comentarios anteriores y las modificaciones realizadas"*).

---

## 1. Texto literal

> Trabajo sobresaliente y excelente evolución frente a la socialización que realizaron, se respondió directamente
> al principal feedback recibido: **"usuario en el centro" dejó de ser una declaración y se convirtió en actividades,
> roles, artefactos, métricas y una compuerta de decisión con capacidad real de retorno**, pero sobre todo de una
> propuesta de Diseño centrado en humano.
>
> Destacamos la combinación contextual de HCD, DevOps, EDA y GenIA; las tres cadencias diferenciadas; la doble
> cadena código/contenido; las compuertas G1–G3; la separación entre autoridad de producto y autoridad técnica;
> y la incorporación verificable de privacidad, accesibilidad, seguridad física y derechos sobre contenidos.
> También es especialmente valioso el criterio de formalizar aquello que cruza fronteras o entra al producto.
>
> Un siguiente nivel para esta propuesta, consiste en **demostrar empíricamente que esta estructura reduce
> retrabajo, defectos y tiempo de validación en una magnitud superior al costo de coordinación que introduce.**
>
> Si una experiencia de RA supera G1 —excelente latencia, tracking estable, alta disponibilidad y cero defectos
> críticos— pero G2 demuestra que el usuario se desorienta, aumenta su carga cognitiva o corre riesgo físico,
> ¿tenemos un producto exitoso?
>
> Espero que su respuesta como líderes de TI sea, No. Y precisamente allí aparece el mayor diferencial de su
> metodología: **En Realidad Aumentada, calidad técnica sin experiencia humana validada no es calidad completa.**

---

## 2. Lectura: qué significa para el Reto #2

### 2.1 Lo que el profesor **valida** (defenderlo, no cambiarlo)

Siete elementos citados explícitamente. Todos deben estar **visibles en el diagrama SPEM**, porque son
lo que el evaluador ya reconoció como el valor de la propuesta:

| # | Elemento validado | ¿Visible hoy en el diagrama? |
|---|-------------------|------------------------------|
| 1 | Combinación **contextual** de HCD, DevOps, EDA y GenIA (contextual = condicional) | ⚠️ falta marcar la condicionalidad de EDA (G-10) |
| 2 | **Tres cadencias diferenciadas** | ❌ no representadas (G-02, G-13) |
| 3 | **Doble cadena código/contenido** | ✅ |
| 4 | **Compuertas G1–G3** | ⚠️ sin rol ejecutor ni fase de destino anotados (G-07) |
| 5 | **Separación autoridad de producto / autoridad técnica** (PO vs. Líder técnico) | ⚠️ los roles están, la separación de autoridad no se lee |
| 6 | Incorporación **verificable** de privacidad, accesibilidad, **seguridad física** y derechos | ⚠️ dispersa; se resuelve con la banda transversal T6 (G-05) |
| 7 | Criterio de **formalizar lo que cruza fronteras o entra al producto** | ❌ el criterio no aparece en el diagrama |

> **Consecuencia práctica:** las brechas G-02, G-05, G-07, G-10 y G-13 de `AUDITORIA_DIAGRAMA.md` dejan de ser
> "pulido SPEM" y pasan a ser **obligatorias**: son exactamente los elementos que el profesor destacó.
> Si no se ven en el diagrama, el modelo se ve más pobre que el paper.

### 2.2 Lo que el profesor **pide como siguiente nivel**

> *"Demostrar empíricamente que esta estructura reduce retrabajo, defectos y tiempo de validación en una magnitud
> superior al **costo de coordinación** que introduce."*

Esto es una **crítica de balance neto**, no de las métricas. El paper ya mide el beneficio (retrabajo, defectos
escapados, SUS, latencia) pero **no mide el coste que el propio método introduce**: compuertas, contratos,
entregables de microciclo, nueve roles. Sin ese lado de la ecuación no hay demostración posible.

**Acción para el Reto #2:** añadir la familia de **coste de coordinación** y el **balance neto** a §10 de
`MODELO_PROCESO.md`. Ya está incorporado (marcado `[NUEVO R2 — feedback]`).

### 2.3 El cierre que nos regala

La pregunta G1-pasa / G2-falla y la frase final son **el mejor cierre posible de la socialización**:
el profesor formuló él mismo el diferencial de la metodología. Se usa literalmente en la diapositiva 4.

---

## 3. Trazabilidad: comentario → modificación (tabla de la diapositiva 3)

| Momento | Comentario recibido | Modificación realizada |
|---------|--------------------|------------------------|
| **Socialización Reto #1** | *"Usuario en el centro" era una declaración, no una práctica* | HCD elevado a **fase de primera clase**: rol UX interno + usuario final como rol externo formal; **G2 con capacidad real de retorno** a F1/F2/F4; ≥1 microciclo con usuarios por incremento validado; métricas SUS y NASA-TLX; informe de evaluación como artefacto de lectura obligatoria |
| **Socialización Reto #1** | Faltaba tratar la responsabilidad social como algo verificable | Sacada de los seis ejes y convertida en **obligación transversal verificada en compuerta** (privacidad, accesibilidad, **seguridad física**, derechos), con responsable nominado |
| **Socialización Reto #1** | La propuesta era una lista de enfoques | Combinación **contextual**: HCD y DevOps obligatorios, EDA y GenIA condicionales (ingeniería de métodos situacional) |
| **Feedback del paper final** | *"Demostrar empíricamente que reduce retrabajo, defectos y tiempo de validación **por encima del costo de coordinación**"* | **Pendiente y asumido:** se añade la familia de métricas de **coste de coordinación** y el **balance neto**; se declara como trabajo futuro con diseño de estudio de caso múltiple |
