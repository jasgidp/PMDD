# REQUISITOS — Reto #2: Diseñar un modelo de procesos

**Única fuente de requisitos del Reto #2.** Actualizar aquí cuando llegue información nueva del profesor.
**Última actualización:** 2026-08-27 (ingesta del enunciado + apoyos del profesor).

---

## 1. Fechas

| Hito | Fecha | Nota |
|------|-------|------|
| Cierre de la tarea | **domingo 30 de agosto de 2026, 23:59** | Se permiten varios envíos |
| Entregable 1 (presentación 4 slides) | **sábado 29 de agosto de 2026** | "sábado" en el enunciado |
| Entregable 2 (socialización ≤5 min) | **sábado 29 de agosto de 2026** | En clase |
| Entregable 3 (modelo incorporado al paper) | **domingo 30 de agosto de 2026** | Cierre |

---

## 2. Enunciado literal

> **Contexto:** A su equipo se le ha asignado un tema específico relacionado con dominios problemáticos como
> sistemas integrados, realidad aumentada, análisis, aprendizaje automático, etcétera. Se requiere que se
> concentre en esta área de trabajo y haga las suposiciones necesarias para desarrollar el modelo propuesto.
>
> **Desafío 2:** Su tarea consiste en diseñar un modelo de proceso que describa una secuencia de actividades,
> roles, métodos, técnicas, artefactos y herramientas, junto con cualquier actividad de soporte adicional
> necesaria para desarrollar soluciones intensivas de software en el dominio asignado.
>
> **Consideraciones:**
> - Incorpore prácticas de las áreas de conocimiento de Ingeniería de Software, metodologías convencionales
>   y/o prácticas ágiles según sea necesario para su modelo. Asegúrese de que los métodos, técnicas, artefactos,
>   roles y herramientas que desea resaltar en el modelo estén claramente visibles.
> - Mejore su ensayo elaborando los conceptos principales del enfoque seleccionado por su equipo.
> - Afine la propuesta a partir de las prácticas de clase y un análisis detallado de la literatura.
> - Describa claramente cómo interactúan estos elementos en su trabajo.
> - Prepare una presentación en la que se expongan los principales conceptos derivados de las lecturas del grupo
>   y se presente el modelo final de proceso evolucionado y consolidado propuesto durante el curso.
> - **Utilice el modelo SPEM 2.0** para desarrollar el modelo de proceso.
> - Revise los documentos de referencia.
>
> **Entregas:**
> - **Entregable 1 (sábado):** Presentación de **4 diapositivas** (las tres anteriores + 1 del modelo de proceso).
> - **Entregable 2 (sábado):** Presentación de **máximo 5 minutos**, siguiendo la Guía de Presentación:
>   introducir contexto/dominio; resaltar el enfoque; presentar el diagrama de espina de pescado enfatizando
>   los comentarios previos y las modificaciones realizadas; usar el **70 % restante del tiempo** para explicar
>   el modelo de proceso.
> - **Entregable 3 (domingo):** Incorporar el modelo al paper, explicando **las interacciones, los ciclos y los
>   artefactos** propuestos.
>
> **Ejemplos:** https://edup.lecciones-aprendidas.info/ ·
> https://www.lecciones-aprendidas.info/search/label/Procesos%20modernos%20de%20desarrollo%20de%20software
>
> **Objetivos de aprendizaje:** diseñar un modelo de proceso para un dominio específico; incorporar prácticas de
> IS, metodologías convencionales y/o ágiles; refinar y evolucionar el modelo con base en las prácticas de clase
> y el análisis de literatura; preparar y entregar una presentación concisa y efectiva.

---

## 3. Elementos obligatorios del modelo (checklist normativo)

El enunciado nombra **siete categorías**. Todas deben estar *"claramente visibles"* en el diagrama.

| # | Elemento exigido | ¿Dónde vive? | Estado |
|---|------------------|--------------|--------|
| R1 | **Secuencia de actividades** | 7 fases con hitos M1–M4 y retornos por compuerta · paper §V-B y §V-C | ✅ |
| R2 | **Roles** | 11 roles con decisión exclusiva · Cuadro I · diagrama | ✅ |
| R3 | **Métodos** | Ingeniería de métodos situacional; HCD/DevOps obligatorios, EDA/GenIA condicionales · §IV-F | ✅ |
| R4 | **Técnicas** | Paneles "Métodos y técnicas" por fase en el diagrama · Cuadro III | ✅ |
| R5 | **Artefactos** | Tipados Artifact/Deliverable/Outcome · Cuadro II · 24 artefactos en el diagrama | ✅ |
| R6 | **Herramientas** | Encadenadas `herramienta ⇢ rol → tarea` · Cuadro III | ✅ |
| R7 | **Actividades transversales / de soporte** | Banda **S1–S7** alineada con ISO/IEC/IEEE 12207:2017 · Cuadro IV | ✅ |
| R8 | **Uso de SPEM 2.0** | 13 de los 14 símbolos de la paleta + patrones **CP1–CP4** (Capability Patterns) · §V-A | ✅ |
| R9 | **Interacciones descritas** | §V-I: tres planos + tabla de destinos de retorno · Figs. 2–9 | ✅ |

Leyenda: ✅ cumple · ⚠️ parcial · ❌ falta. Las nueve quedaron cubiertas. El histórico de cómo se cerraron está en `AUDITORIA_DIAGRAMA.md`.

---

## 4. Requisitos de la presentación (Entregables 1 y 2)

| Requisito | Valor |
|-----------|-------|
| Número de diapositivas | **4** exactas: las 3 del Reto #1 + 1 nueva del modelo de proceso |
| Duración | **≤ 5 minutos** |
| Estructura obligatoria | (1) contexto/dominio → (2) enfoque → (3) espina de pescado *con los comentarios recibidos y las modificaciones hechas* → (4) modelo de proceso |
| Reparto del tiempo | **~30 % slides 1–3, ~70 % (≈3:30) slide 4** |
| Punto crítico | Hay que **mostrar explícitamente qué se cambió** tras el feedback del Reto #1 → resuelto en `FEEDBACK_RETO1.md` §3 |

Desarrollo en `PRESENTACION.md`.

---

## 5. Supuestos declarados (el enunciado los autoriza)

| ID | Supuesto | Razón |
|----|----------|-------|
| S1 | Proyecto de RA con equipo multidisciplinario y madurez de requisitos baja | Ámbito declarado en §IV-E del paper |
| S2 | Microciclo de **2 semanas**; incremento validado de **1 a 3 meses** (2–6 microciclos) | §IV-A del paper |
| S3 | EDA y GenIA **condicionales**; HCD y DevOps **obligatorios** | §IV-G del paper |
| S4 | El contrato de frontera existe siempre; su forma (AsyncAPI vs. spec de interfaces) depende de EDA | §IV-C del paper |
| S5 | No aplica a prototipos exploratorios de un solo desarrollador ni a requisitos cerrados | §IV-E (casos de no-uso) |

---

## 5-bis. Exigencia adicional derivada del feedback

El profesor, al evaluar el paper final del Reto #1, añadió un requisito de fondo que el Reto #2 debe atender:

> *"Demostrar empíricamente que esta estructura reduce retrabajo, defectos y tiempo de validación en una
> magnitud superior al **costo de coordinación** que introduce."*

| Implicación | Dónde se resuelve |
|-------------|-------------------|
| Medir también el **coste** que el método introduce, no solo su beneficio | `MODELO_PROCESO.md` §10.3 (nueva familia de indicadores + balance neto) |
| Declararlo como **hipótesis falsable**, no como afirmación | §IV-F y §V del paper (`PAPER_SECCION_MODELO.md`) |
| Que el diagrama muestre los 7 elementos que el profesor destacó | `AUDITORIA_DIAGRAMA.md` G-02, G-05, G-07, G-10, G-13, G-17, G-18 |

---

## 6. Rúbrica

No se publicó rúbrica numérica para el Reto #2. Se asume que se evalúa contra las **siete categorías del
enunciado (R1–R7)**, el **uso correcto de SPEM 2.0 (R8)** y la **calidad de la explicación de interacciones (R9)**.
Si llega rúbrica formal, se registra aquí. **[FALTA]**
