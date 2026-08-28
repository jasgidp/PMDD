# PRESENTACIÓN — Entregables 1 y 2

**Entregable 1:** 4 diapositivas (las 3 del Reto #1 + 1 del modelo de proceso) — sábado 29-ago-2026.
**Entregable 2:** socialización de **máximo 5 minutos** siguiendo la Guía de Presentación.

**Archivo:** [`index.html`](../../index.html) — en la raíz del repo. Deck de 4 diapositivas, derivado de
`reto1/presentacion/v2-corregida.html` (el original del Reto #1 queda intacto como respaldo).

Para verlo: abrir el archivo en el navegador, o `python3 -m http.server` desde la raíz.
Teclas: **← →** o espacio para navegar · **F** pantalla completa · **Esc** cierra paneles y el zoom.

### Qué se actualizó de las 3 primeras (2026-08-27)

| Diapositiva | Cambio |
|---|---|
| 1 · Realidad aumentada | Subtítulo ahora nombra **ARCA — Augmented Reality Continuous Assurance** |
| 2 · Cuatro enfoques | Orden del paper v2 (**HCD · DevOps · EDA · GenIA**) y nota de obligatorios vs. condicionales |
| 3 · Espina de pescado | **Flujo de fases corregido** a F1–F7 de ARCA con los destinos de retorno de cada compuerta · eje *Ciclo* → tres cadencias anidadas · eje *Colaboración* → **11 roles** (se retiró el "arquitecto de eventos", que el paper descarta explícitamente) · eje *Artefactos* → doble pipeline en F5 y tipado Artifact/Deliverable/Outcome · eje *Madurez* → cuatro familias de indicadores y criterio de valor neto · *Valor diferencial* reescrito |

### Diapositiva 4 · ARCA, modelo de proceso

Mapa interactivo a la izquierda + panel de detalle a la derecha, con el mismo lenguaje visual de la 3:

- **7 fases clicables** en serpentina, con hitos M1–M4 marcados y la banda S1–S7 al pie
- **Compuertas clicables**: G1, G2, G3.1 y G3.2
- **8 momentos clave**: cadencias · doble pipeline · compuertas y retornos · 11 roles · hitos · apoyo S1–S7 · patrones CP1–CP4 · medición y valor neto
- Cada selección muestra actividades (A1.1–A7.3) con su **rol primario**, productos de trabajo, métodos y técnicas, herramientas, compuerta y nota clave
- **Mini-diagrama de entradas / interior / salidas** encabezando cada selección: qué entra y de qué fase viene, qué actividades ocurren dentro, qué sale y hacia dónde, más la compuerta que aplica y el retorno que entra
- **Las actividades se revelan al tocarlas** dentro del diagrama (A1.1, A5.3…): la descripción aparece justo debajo, no todas a la vez. Volver a tocarla la cierra
- **Segundo diagrama por fase — `herramienta ⇢ rol → tarea`**, con el mismo encadenamiento del SPEM: qué herramienta usa cada rol y qué tareas ejecuta
- **Cada compuerta tiene su propio diagrama de destinos**: G1 (→ F2 · F3 · F5), G2 (→ F1 · F2 · F3 · F4) y G3 (→ siempre F4), con su rol ejecutor y quién decide
- Los momentos clave tienen su propio esquema: cadencias como cajas anidadas, doble pipeline como dos carriles que convergen en A5.3, hitos como línea de tiempo
- Botón **Ampliar** → overlay a pantalla completa: el mini-diagrama a todo el ancho y el detalle a dos columnas
- Botón **Ver en el diagrama** / **◱ Ver el diagrama SPEM completo** → visor a pantalla completa del `.drawio` real, con rueda para acercar, arrastre para mover y botones F1–F7 · G1 · G2 · G3 que **encuadran esa fase o compuerta** en el lienzo. Es lo que resuelve “ver visualmente la conexión” sin romper el límite de 4 diapositivas
- Se retiró la lista de **Herramientas** del panel: ya están en el diagrama `herramienta ⇢ rol → tarea`, no hacía falta repetirlas

### El visor usa el SVG exportado

Archivo: **`reto2/diagrama/arca-general4.svg`** (3340 × 4111), exportado de la página `General 4` con el layout
ya reorganizado. Se eligió SVG sobre PNG, HTML o PDF: es vectorial, así que **no pixela por mucho que se acerque**
—clave al proyectar— y se carga como imagen normal, lo que permite controlar el encuadre desde el deck.
El HTML de draw.io traería su propio visor anidado y no se le puede pedir que enfoque una fase concreta.

Los encuadres de F1–F7 y G1–G3 están **leídos del propio SVG** (posición real de cada caja y de cada rótulo),
no supuestos. Si el diagrama se reorganiza y se vuelve a exportar, **hay que recalcularlos**: las cajas se mueven
y los botones apuntarían a la zona equivocada.

### Por qué no hay diapositiva 5

El enunciado pide **exactamente 4 diapositivas** ("las tres anteriores + 1 del modelo de proceso"). Añadir una
quinta contradice un requisito literal y evaluable. Por eso el diagrama completo va como **visor dentro de la
diapositiva 4**, no como diapositiva aparte: se ve a pantalla completa igual, pero el conteo sigue siendo 4.

---

## 1. Reparto del tiempo (lo pide el enunciado)

| Bloque | Slides | Tiempo | % |
|--------|--------|--------|---|
| Contexto/dominio + enfoque + espina (con modificaciones) | 1–3 | **≈1:30** | 30 % |
| **Modelo de proceso** | 4 | **≈3:30** | **70 %** |

> El enunciado es explícito: *"utilizar el 70 % restante del tiempo para explicar el modelo de proceso"*.
> Ensayar con cronómetro: el riesgo real es gastar 3 minutos en repetir el Reto #1.

---

## 2. Slide 1 — Contexto / dominio (≈30 s)

- RA = objetos reales y virtuales, interactivo, en tiempo real, con registro 3D (Azuma).
- Madurez **parcial**: viable en móviles y nichos industriales/educativos; adopción masiva aún abierta.
- El problema **no es solo técnico**: falta una metodología que integre entrega de software **y contenido**,
  coordinación distribuida, validación con usuarios y obligaciones legales por captura continua del entorno.

**Frase de cierre:** *"El vacío que atacamos no es de tecnología, es de proceso."*

## 3. Slide 2 — Enfoque (≈30 s)

Cuatro enfoques, cada uno cubriendo una debilidad documentada del dominio:

| Enfoque | Debilidad que cubre |
|---------|---------------------|
| **GenIA** | Coste de autoría de contenido |
| **DevOps** | Entrega repetible de software **y** contenido |
| **EDA** | Coordinación de experiencias distribuidas y en tiempo real |
| **HCD** | Escasez de validación con usuarios (eleva la evaluación a fase de primera clase) |

Marco: **taxonomía de procesos de Céret et al.** (6 ejes) + **ingeniería de métodos situacional**.

## 4. Slide 3 — Espina de pescado **con las modificaciones** (≈30 s)

El enunciado pide *"enfatizando los comentarios previos y las modificaciones realizadas"*.
Fuente literal: [`FEEDBACK_RETO1.md`](FEEDBACK_RETO1.md).

| Comentario recibido | Modificación realizada |
|---------------------|------------------------|
| **"Usuario en el centro" era una declaración, no una práctica** (feedback de la socialización) | HCD elevado a **fase de primera clase**: rol UX + usuario final como rol externo formal · **G2 con capacidad real de retorno** a F1/F2/F4 · ≥1 microciclo con usuarios por incremento · SUS y NASA-TLX · informe de evaluación como artefacto obligatorio |
| Responsabilidad social sin mecanismo de verificación | Sacada de los seis ejes → **obligación transversal verificada en compuerta**: privacidad, accesibilidad, **seguridad física** y derechos, con responsable nominado |
| La propuesta parecía una lista de enfoques yuxtapuestos | Combinación **contextual**: HCD y DevOps obligatorios, EDA y GenIA **condicionales** (ingeniería de métodos situacional) |
| Crítica de madurez (propuesta no validada) | Se **operacionalizó el instrumento**: métricas de instrumentación, de resultado y de coste de coordinación + diseño de estudio de caso múltiple |

**Cómo decirlo (≈30 s), literal:**

> *"El feedback de la socialización fue directo: 'usuario en el centro' era una declaración. Lo convertimos en
> estructura — actividades, roles, artefactos, métricas y **una compuerta con capacidad real de retorno**.
> Esa es la modificación que ordena todo lo demás."*

Es la frase con la que el profesor reconoció la evolución: **usarla es hablar su idioma**.

## 5. Slide 4 — Modelo de proceso SPEM 2.0 (≈3:30) — **la diapositiva que decide la nota**

**Contenido:** el diagrama SPEM exportado en alta resolución + leyenda de símbolos.

### Guion en 5 movimientos (≈40 s cada uno)

1. **La secuencia** (≈40 s) — "Siete fases, F1 a F7. Pero **no es una cascada**: el microciclo de dos semanas
   selecciona trabajo de las fases activas, no las recorre todas."
2. **Las cadencias anidadas** (≈40 s) — "Tres relojes distintos: CI/CD **continua**, microciclo de **2 semanas**,
   incremento validado de **1 a 3 meses**. Separamos la frecuencia con que se publica de la frecuencia con que
   se valida."
3. **Las compuertas** (≈50 s) — "**G1** rendimiento, **G2** experiencia y responsabilidad social, **G3** generación
   (solo si GenIA). Lo distintivo: la compuerta no solo bloquea — **prescribe la fase de destino y tiene un rol
   nominado**. Spiral y RAD mencionan la validación pero no dicen qué hacer cuando falla."
4. **La doble cadena** (≈50 s) — "En F5 conviven la cadena de código y la de contenido. En RA no se despliega solo
   software: se despliegan activos, instrucciones de augmentación y reglas de interacción, con su propio versionado
   y sus propias pruebas. **Y una cadena puede bloquear el incremento aunque la otra esté lista** — ese es el
   cuello de botella más caro del dominio."
5. **Roles y soporte** (≈30 s) — "Nueve roles internos y dos externos, con autoridad separada: el PO decide el
   *qué*, el líder técnico el *cómo*. Y un rol que **ningún modelo clásico contempla**: el responsable de derechos
   y licencias, sin cuyo registro **ningún activo entra a la cadena de contenido**. Debajo, las actividades
   transversales de soporte que cruzan las siete fases."

### Cierre (≈20 s) — **la pregunta que decide la defensa**

El propio profesor formuló el diferencial del método. Se usa tal cual:

> *"Si una experiencia de RA supera G1 —latencia excelente, tracking estable, alta disponibilidad, cero defectos
> críticos— pero G2 demuestra que el usuario se desorienta, aumenta su carga cognitiva o corre riesgo físico:
> **¿tenemos un producto exitoso?** Nuestra respuesta es **no**. Y por eso G1 y G2 no son sustituibles entre sí:
> **en realidad aumentada, calidad técnica sin experiencia humana validada no es calidad completa.**"*

Y el trabajo que viene, en una frase:

> *"El siguiente nivel es demostrar empíricamente que esta estructura reduce retrabajo, defectos y tiempo de
> validación **por encima del coste de coordinación** que introduce. Por eso el modelo mide las dos cosas."*

---

## 6. Checklist antes de presentar

- [ ] Exactamente **4 diapositivas**
- [ ] Cronometrado **≤ 5:00** (ensayo real, no estimación)
- [x] Slide 3 dice **qué comentarios se recibieron y qué se cambió** (ver `FEEDBACK_RETO1.md`)
- [ ] Slide 4 ocupa ≈70 % del tiempo
- [ ] El diagrama se lee proyectado (exportar a alta resolución; probarlo en pantalla)
- [ ] La **leyenda SPEM** es visible en la slide 4
- [ ] Quien presenta puede recitar: 7 fases · 3 compuertas · 3 cadencias · 9+2 roles · doble cadena
- [ ] El cierre G1-pasa/G2-falla está memorizado — es el remate de la presentación
