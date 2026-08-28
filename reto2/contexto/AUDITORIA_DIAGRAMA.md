# AUDITORÍA DEL DIAGRAMA — ¿estamos cumpliendo lo que piden?

**Archivo auditado:** `reto2/diagrama/Diagrama-SPEM2.0-PMDS.drawio`
**Fecha:** 2026-08-27 · **Contra:** enunciado del Reto #2 (`REQUISITOS.md` §3) + paper final del Reto #1.

---

> ## ✅ CERRADO — página `General 4`, reorganizada por el equipo
>
> Las **18 brechas G-01…G-18 están cerradas** y el equipo reorganizó además el layout (el lienzo pasó de
> 4250 a 3340 px de ancho y varios rótulos se movieron bajo su caja). El resultado se exportó a
> `arca-general4.svg`, que es lo que muestra el visor de la diapositiva 4 y lo que alimenta las Figs. 2–9 del paper.
>
> **Único pendiente material:** el `.drawio` con ese layout reorganizado **no está en el repo** — la copia de
> `reto2/diagrama/Diagrama-SPEM2.0-ARCA.drawio` tiene el layout anterior. Hay que guardarlo antes del sábado.
>
> <details><summary>Estado intermedio (antes de la reorganización)</summary>
>
> ## ESTADO 2026-08-27 — página `General 4` de `Diagrama-SPEM2.0-ARCA.drawio`
>
> **Cerradas las 18 brechas G-01…G-18.** El diagrama usa hoy **13 de los 14 símbolos SPEM 2.0** y cubre las
> siete categorías del enunciado. Añadido además, desde el paper ARCA v2: actividades **A1.1–A7.3** con rol
> primario, hitos **M1–M4**, apoyos **S1–S7** con ISO/IEC/IEEE 12207:2017 y patrones **CP1–CP4**.
>
> Pendientes de criterio humano: revisar el **trazado de las flechas** (estética) y decidir si se eliminan las
> páginas de historial (`General`, `General 2`, `General 3`) y las cuatro páginas personales vacías antes de entregar.
>
> </details>
>
> <details><summary>Estado anterior (página General 3)</summary>
>
> ## Estado 2026-08-27 — página `General 3`
>
> Se creó la página **`General 3`** en `Diagrama-SPEM2.0-PMDS.drawio` a partir de General 2 (que se conserva
> intacta como respaldo). Cerradas por completo o en lo esencial: **G-01, G-02, G-04, G-05, G-06, G-07,
> G-08, G-10, G-12, G-13, G-14, G-15, G-17, G-18**.
>
> **Sigue abierto y necesita mano humana:**
>
> | Pendiente | Por qué no se automatizó |
> |-----------|--------------------------|
> | **Cablear los artefactos nuevos** (informe de evaluación, evidencias de compuerta, release, telemetría, backlog, responsable de los datos) con flechas a sus tareas | Decidir el origen exacto de cada flecha es criterio de diseño, y trazarlas mal cruza el lienzo |
> | **G-03** — reasignar las tareas de F5 bajo las dos `Actividad` | Los nodos `Actividad` ya están creados y conectados a INTEGRACIÓN; falta colgar las tareas existentes |
> | **G-09** — 3 `Declaración de accesibilidad` duplicadas | Hay que decidir si se borran o se reemplazan por el artefacto correcto de esa fase |
> | **G-11** — storyboards ubicados en F3 | Decisión del equipo: moverlos a F4 o justificarlos |
> | **G-16** — el archivo tiene **13 páginas**, con `Alejandro Rios`, `Lina Ballesteros`, `Jose Manuel`, `Jonathan` y `Quinnie` **duplicadas** | Borrar páginas es destructivo; que lo confirme el equipo |
> | Estética y separación de flechas | Requiere ojo humano en el lienzo |
>
> </details>

## 0. Veredicto en una línea

El diagrama **tiene el contenido correcto y bien alineado con el paper** (fases, tareas, roles, artefactos y
herramientas coinciden), pero **está tipado con solo 4 de los 14 símbolos SPEM 2.0** y **le faltan dos de las
categorías que el enunciado nombra de forma explícita: métodos/técnicas y actividades de soporte**.
Es un trabajo de **corrección y completado, no de rehacer**.

### Inventario actual (extraído del archivo)

| Elemento SPEM | Nodos | Estado |
|---------------|-------|--------|
| Tarea | 28 | ✅ |
| Herramienta | 31 | ✅ |
| Rol | 25 instancias (9 roles distintos + `GenIA` mal tipado) | ⚠️ |
| Producto de Trabajo | 20 | ⚠️ (4 duplicados) |
| **Fase** | **0** | ❌ |
| **Iteración** | **0** | ❌ |
| **Actividad** | **0** | ❌ |
| **Concepto** (técnicas) | **0** | ❌ |
| **Patrón de Proceso** (soporte) | **0** | ❌ |
| **Proceso de Liberación** | **0** | ❌ |
| Biblioteca / Dominio | 0 | ⚠️ opcional |
| Compuertas (rombo genérico) | 4 | ⚠️ sin rol ni destino |
| Hito (elipse) | 1 (`Incremento Validado`) | ⚠️ |
| Cajas agrupadoras sin etiqueta | 7 | ❌ son las fases, sin nombre |

---

> ### ⚠️ Repriorización tras el feedback del profesor (ver `FEEDBACK_RETO1.md`)
>
> El profesor destacó **siete elementos** como el valor de la propuesta. Cinco de ellos **no se leen hoy en el
> diagrama**, así que las brechas que los afectan suben a bloqueantes: **G-02** (tres cadencias diferenciadas),
> **G-05** (responsabilidad social verificable como banda transversal), **G-07** (compuertas con rol y destino),
> **G-10** (combinación *contextual* → condicionalidad de EDA) y **G-13**. Se añade **G-17**: hacer visible la
> **separación de autoridad PO / Líder técnico** y **G-18**: rotular el **criterio de formalización de frontera**.
> Si el profesor no encuentra en el diagrama lo que ya elogió del paper, el modelo se ve más pobre que el texto.

## 1. Brechas — bloqueantes (hay que corregirlas sí o sí)

| ID | Brecha | Por qué importa | Corrección | Responsable |
|----|--------|-----------------|------------|-------------|
| **G-01** | **Las 7 fases no están tipificadas como `Fase` ni rotuladas.** Hoy son 7 cajas beige vacías (`&nbsp;`) | El evaluador no puede leer la secuencia de fases; es *lo primero* que pide el enunciado | Poner el icono `Fase` + rótulo `F1. Encuadre y contexto de uso` … `F7. Despliegue, operación y evolución` | Cada responsable en su bloque |
| **G-02** | **No existe `Iteración` (microciclo de 2 semanas) ni `Proceso de Liberación` (incremento validado)** | Las **cadencias anidadas** son la decisión #1 del paper y no se ven en el diagrama | Añadir un contenedor `Iteración — Microciclo (2 semanas)` sobre F1–F7 y un `Proceso de Liberación — Incremento validado (2–6 microciclos)` en la salida | Alejo + Quinnie (integración) |
| **G-04** | **Métodos y técnicas no aparecen como elementos.** Están diluidos dentro del nombre de la tarea (`Evaluación con Usuarios (SUS, NASA-TLX)`) | El enunciado exige que **técnicas y métodos estén "claramente visibles"** | Sacarlos como nodos `Concepto` colgados de su tarea: SUS · NASA-TLX · evaluación heurística · Wizard of Oz · entrevistas contextuales · personas y escenarios · prompt engineering · RAG · human-in-the-loop · guardrails · TDD · pub/sub · event streaming · CEP · IaC · promoción por ambientes · ADR | Todos, en su fase |
| **G-05** | **No hay actividades transversales / de soporte.** El enunciado las nombra explícitamente ("actividades de soporte adicionales") | Es una categoría entera del enunciado sin representar | Añadir la **banda transversal T1–T7** de `MODELO_PROCESO.md` §8 como `Patrón de Proceso` bajo el flujo de fases | Jhonnatan + Alejo |
| **G-06** | **`GenIA` está dibujado con icono de Rol** y **falta el rol externo `Responsable de los datos`** | Error de tipado conceptual (un enfoque no es una persona) + rol que el paper declara en G3 | Cambiar `GenIA` a marca de condicionalidad; añadir `Responsable de los datos` como Rol externo en F4/G3 | Lina |

| **G-17** | La **separación entre autoridad de producto y autoridad técnica** no se lee en el diagrama; PO y Líder técnico aparecen como dos roles más | Es uno de los siete elementos que el profesor destacó explícitamente | Anotar la autoridad en cada rol: `PO — decide el QUÉ · único que acepta el incremento`, `Líder técnico — decide el CÓMO · elige el destino cuando G1 falla` | Alejo + Quinnie |
| **G-18** | El **criterio de formalización** ("se formaliza lo que cruza una frontera entre equipos o entra al producto") no aparece | El profesor lo llamó *"especialmente valioso"* | Nota rotulada en la leyenda + distinguir visualmente productos de trabajo formales vs. semi-formales | José Manuel |

---

## 2. Brechas — importantes (restan puntos)

| ID | Brecha | Corrección | Responsable |
|----|--------|------------|-------------|
| **G-03** | Falta el nivel `Actividad` entre Fase y Tarea (SPEM: Fase > Actividad > Tarea). Las dos cadenas de F5 son el caso más claro | Crear `Actividad: Cadena de código` y `Actividad: Cadena de contenido` en F5, y agrupar en actividades las fases con >3 tareas | Jhonnatan |
| **G-07** | Compuertas sin **rol ejecutor** ni **fase de destino** anotados | `G1 — Rendimiento · ejecuta: Calidad · decide destino: Líder técnico → F3 \| F5`; `G2 — UX + resp. social · ejecuta: UX + Derechos + Usuario → F1 \| F2 \| F4`; `G3 — Generación · ejecuta: Contenido + Derechos + Datos → F4 \| F5` | Alejo (G1/G2), Lina (G3) |
| **G-08** | **Artefactos faltantes** frente al paper: `Informe de evaluación con usuarios (con métricas)`, `Backlog priorizado`, `Evidencias de compuerta / registro de causa de retorno`, `Release desplegado`, `Telemetría de campo` (existe la tarea, no el producto) | Añadirlos como Producto de Trabajo en F6/F7 | Alejo |
| **G-09** | `Declaración de Accesibilidad` aparece **4 veces**; solo una (F1) es legítima. Las otras 3 parecen residuo de copy/paste | Borrar duplicados o, si son intencionales, reemplazarlas por el artefacto correcto de esa fase | Quinnie (integración) |
| **G-10** | **Condicionalidad de EDA no marcada.** `Catalogar Eventos EDA`, `Implementar Eventos EDA`, `Catálogo de Eventos`, `Servicios de Eventos Desplegados` deberían llevar `*` igual que se hizo con GenIA/G3 | Añadir `*` + nota al pie `* solo si EDA está activo` | José Manuel + Jhonnatan |
| **G-12** | La **leyenda SPEM solo está en la página `Quinnie`**, no en la página que se va a presentar | Copiar la barra de símbolos + las convenciones de compuerta a la página final | Quinnie |
| **G-13** | Las **tres cadencias anidadas** (CI continua → microciclo → incremento) no son legibles | Rotularlas explícitamente junto a `nuevo microciclo` | Alejo |

---

## 3. Brechas — menores (pulido)

| ID | Brecha | Corrección |
|----|--------|------------|
| **G-11** | `Storyboards baja Fidelidad` aparece en el bloque de F3, pero en el paper el prototipado es F4 | Mover a F4 o justificar el diseño preliminar en F3 |
| **G-14** | Las métricas (instrumentación / resultado) no aparecen | Añadir `Tablero de indicadores` como Producto de Trabajo en F6–F7 (proceso de apoyo T7) |
| **G-15** | **Ortografía y tildes** — el diagrama es entregable evaluado | Corregir: `Especificación de Contexo`→**Contexto** · `Sevices IA`(×4)→**Servicios de IA** · `Compilacion Despegable`→**Compilación desplegable** · `Presición`→**Precisión** · `Lider Tecnico`→**Líder técnico** · `Evaluacion`→**Evaluación** · `produccion`→**producción** · `Declaracion`→**Declaración** · `telemetria`→**telemetría** · `Catalogo`→**Catálogo** · `observacion`→**observación** · `Integracion`→**Integración** · `Diseño`✓ |
| **G-16** | El `.drawio` tiene **6 páginas**: `General` (el modelo), `Quinnie` (**copia completa duplicada**) y 4 **vacías** (`Alejandro Rios`, `Lina Ballesteros`, `Jose Manuel`, `Jonathan`) | Consolidar en una sola página final antes de entregar |

---

## 4. Lo que SÍ está bien (no tocar, y defenderlo en la sustentación)

- ✅ Las **7 fases y sus tareas coinciden con el paper**, fase por fase.
- ✅ Los **9 roles internos** están todos presentes y ubicados en la fase correcta.
- ✅ La **doble cadena de F5** (código y contenido) está dibujada y converge en el candidato de versión.
- ✅ Las **tres compuertas** existen, con G3 correctamente marcada como *solo si GenIA*.
- ✅ Los **retornos están etiquetados por causa** (`[falla: contexto]`, `[falla: requisitos]`, `[falla: diseño]`,
  `[falla: build]`, `[falla: UX prototipo]`, `[falla: calidad/derechos]`, `[falla: contenido]`) — esto es
  exactamente la decisión distintiva del paper y **es lo más fuerte del diagrama**.
- ✅ La **cobertura de herramientas** (31 nodos, 5 familias DevOps + Unity + Figma + Kafka/CEP + servicios de IA)
  es la categoría mejor resuelta.
- ✅ El ciclo cierra con `nuevo microciclo`, no en una cascada.

---

## 5. Orden de trabajo recomendado (hasta el sábado 29)

| Prioridad | Bloque | Brechas | Tiempo estimado |
|-----------|--------|---------|-----------------|
| 1 | Rotular y tipar las 7 fases | G-01 | 30 min |
| 2 | Banda transversal T1–T7 | G-05 | 45 min |
| 3 | Técnicas como `Concepto` | G-04 | 1 h (repartido entre los 5) |
| 4 | Anotar compuertas (rol + destino) | G-07 | 20 min |
| 5 | Iteración + incremento validado | G-02, G-13 | 30 min |
| 6 | Rol de datos + destipar GenIA | G-06 | 10 min |
| 7 | Artefactos faltantes | G-08 | 20 min |
| 8 | Actividad en F5 | G-03 | 20 min |
| 9 | Leyenda en la página final | G-12 | 10 min |
| 10 | Ortografía, duplicados, consolidar páginas | G-09, G-15, G-16 | 30 min |
| 11 | Exportar PNG/PDF para slide 4 y figura del paper | — | 10 min |

**Con 1–4 hechos, el entregable ya cumple las siete categorías del enunciado.** Lo demás es nota.
