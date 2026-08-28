# GESTIÓN — Reto #2: estado, decisiones y bitácora

---

## 1. Estado de los entregables

**Última actualización:** 2026-08-27 (noche)

| Entregable | Fecha | Estado | Qué falta |
|------------|-------|--------|-----------|
| **1. Presentación 4 slides** | sáb 29-ago | 🟢 **lista** — `index.html` en la raíz | Detalles menores de contenido desactualizado (el equipo los revisa) |
| **2. Socialización ≤5 min** | sáb 29-ago | 🟡 guion escrito | **Ensayar con cronómetro** y repartir quién dice qué |
| **3. Modelo en el paper** | dom 30-ago | 🟢 **cubierto** — `reto2/paper/pdms_reto2-2.pdf` | Revisión final: legibilidad de figuras y coherencia de nombres |
| **Diagrama SPEM** | — | 🟢 completo y reorganizado | ⚠️ **El `.drawio` reorganizado no está en el repo** (ver riesgos) |

### Paper — versión vigente `pdms_reto2-2.pdf` (17 pp.)

Secciones **I a X** completas · **9 figuras** (espina + un fragmento SPEM por fase F1–F7 + vista general) ·
**8 cuadros** · **42 referencias**. Los tres elementos que pide el entregable 3 están localizables:
ciclos §V-B · interacciones §V-I · artefactos §V-E y Cuadro II.

### Diagrama — página `General 4`

13 de los 14 símbolos SPEM en uso · 7 fases con hitos M1–M4 · compuertas G1, G2, G3.1 y G3.2 con rol y destino ·
18 actividades A1.1–A7.3 · banda de apoyo S1–S7 con ISO/IEC/IEEE 12207 · patrones CP1–CP4 · métodos y técnicas
por fase. Exportado a `arca-general4.svg`, que alimenta el visor de la diapositiva 4.

---

## 2. Decisiones

| ID | Decisión | Fecha | Quién |
|----|----------|-------|-------|
| R2-D1 | El Reto #2 **formaliza** el modelo del Reto #1 en SPEM 2.0; no se rediseña la metodología | 2026-08-27 | Equipo |
| R2-D2 | **Si diagrama y paper se contradicen, gana el paper**, salvo decisión registrada aquí | 2026-08-27 | Equipo |
| R2-D3 | Microciclo de **2 semanas** como unidad de planificación acordada globalmente | 2026-08-27 | Equipo |
| R2-D4 | Convención visual única en `SPEM_CONVENCIONES.md`; nadie improvisa símbolos | 2026-08-27 | Equipo |
| R2-D5 | Reparto F1+F2 Quinnie · F3 José Manuel · F4+G3 Lina · F5 Jhonnatan · F6+F7+G1/G2 Alejo | 2026-08-27 | Equipo |
| R2-D6 | **Quinnie integra** el Draw.io final; **José Manuel** revisa consistencia técnica; **Alejo** lleva métricas | 2026-08-27 | Equipo |
| R2-D7 | Formato uniforme de entrega de cada bloque: 8 campos (`ASIGNACION_EQUIPO.md` §4) | 2026-08-27 | Equipo |
| R2-D8 | Las **actividades de soporte** se modelan como banda transversal T1–T7 y como `Patrón de Proceso` | 2026-08-27 | **[PROPUESTA — falta confirmar con el equipo]** |
| R2-D9 | El modelo entra al paper como **§IV-J**, no como sección nueva | 2026-08-27 | **[PROPUESTA — falta confirmar]** |
| R2-D10 | Estructura del repo: `reto1/` y `reto2/` separados; contexto por reto | 2026-08-27 | Jonathan |
| R2-D11 | Los **siete elementos que el profesor destacó** deben ser legibles en el diagrama; las brechas que los afectan suben a bloqueantes (G-02, G-05, G-07, G-10, G-13, G-17, G-18) | 2026-08-27 | Feedback profesor |
| R2-D12 | Se añade la familia de métricas de **coste de coordinación** y la hipótesis de **balance neto** (`MODELO_PROCESO.md` §10.3) | 2026-08-27 | Feedback profesor |
| R2-D14 | **Nombre de la metodología: ARCA — Augmented Reality Continuous Assurance** (Aseguramiento Continuo para Realidad Aumentada). Cierra D15 del Reto #1 | 2026-08-27 | Equipo |
| R2-D16 | El archivo de trabajo es **`Diagrama-SPEM2.0-ARCA.drawio`**, página **`General 4`**. `General`, `General 2` y `General 3` se conservan como historial | 2026-08-27 | Jonathan |
| R2-D17 | Vocabulario: **pipeline de código / pipeline de contenido**, no "cadena" (coherente con A3.3 y CP3 del paper v2) | 2026-08-27 | Jonathan |
| R2-D20 | El visor del deck usa el **SVG** exportado (vectorial, no pixela al ampliar); los encuadres por fase se leen del propio SVG y **hay que recalcularlos si se reorganiza y reexporta el diagrama** | 2026-08-27 | Jonathan |
| R2-D19 | **No se añade una quinta diapositiva**: el enunciado pide exactamente 4. El diagrama SPEM completo va como visor a pantalla completa dentro de la diapositiva 4 | 2026-08-27 | Jonathan |
| R2-D18 | **G3 es una sola compuerta con dos puntos de aplicación** (G3.1 salida de F4, G3.2 salida de F5); no se consolidan porque el paper las define así | 2026-08-27 | Paper v2 |
| R2-D15 | Se trabaja sobre la página **General 3** del `.drawio` (General 2 se conserva intacta como respaldo) | 2026-08-27 | Jonathan |
| R2-D13 | El cierre de la socialización es la pregunta **G1 pasa / G2 falla** y la frase *"calidad técnica sin experiencia humana validada no es calidad completa"* | 2026-08-27 | Feedback profesor |

---

## 3. Riesgos abiertos

| Riesgo | Impacto | Mitigación |
|--------|---------|------------|
| **El `.drawio` con el layout reorganizado no está en el repo.** El repo tiene la versión anterior; la buena solo existe en draw.io / Drive del equipo y en el SVG exportado | **Alto** — si hay que corregir algo del diagrama, se parte de un layout peor y hay que rehacer el trabajo de reorganización | **Guardar el `.drawio` reorganizado en `reto2/diagrama/`** antes del sábado |
| Si el diagrama se reorganiza y se reexporta, los encuadres por fase del visor quedan desalineados | Medio — botones F1–F7 apuntando a la zona equivocada | Recalcular los focos leyendo el SVG nuevo (ya se hizo una vez; el procedimiento está en `PRESENTACION.md`) |
| Cinco minutos es muy poco y hay tentación de repetir el Reto #1 | Medio | Ensayo cronometrado; regla 30/70 |
| El archivo `.drawio` tiene páginas de historial y cuatro personales vacías | Medio — mala impresión al abrirlo | Consolidar antes de entregar (decisión del equipo) |
| Legibilidad de las Figs. 2–8 a tamaño de impresión | Medio | Revisar en PDF al 100 % |
| ~~No tenemos el feedback literal del Reto #1~~ | — | ✅ cerrado — `FEEDBACK_RETO1.md` |
| ~~Faltan las figuras del modelo en el paper~~ | — | ✅ cerrado — 9 figuras insertadas |

---

## 4. Bitácora

| Fecha | Qué pasó |
|-------|----------|
| 2026-08-27 | **Reorganización del repo**: todo el Reto #1 movido a `reto1/` (contexto, paper, presentaciones, estado del arte, apoyos, entrega final en PDF); creado `reto2/` con `apoyos/`, `diagrama/` y `contexto/`. `.gitignore` actualizado (`reto1/contexto/privado/`). |
| 2026-08-27 | **Ingesta de la versión final del Reto #1** (`Equipo2_2026_Metodologia_AR_EAFIT.pdf`): 7 fases, 3 compuertas, 9+2 roles, doble cadena, formalización mixta, responsabilidad social transversal, métricas en dos familias, comparación vs. Spiral/RAD/XP. Volcado a `MODELO_PROCESO.md`. |
| 2026-08-27 | **Ingesta del enunciado del Reto #2** y de los apoyos del profesor (guía SPEM 2.0, plantilla de 14 símbolos, ejemplo ADELFE, referencias). → `REQUISITOS.md`, `SPEM_CONVENCIONES.md`. |
| 2026-08-27 | **Ingesta del trabajo de los compañeros** (descomposición F1–F7 con cuellos de botella y métricas económicas + reparto de responsabilidades). → `MODELO_PROCESO.md` §4/§10, `ASIGNACION_EQUIPO.md`. |
| 2026-08-27 | **Paper v3** (`pdms_reto2-2.pdf`): el equipo insertó las **9 figuras** que faltaban — Fig. 1 espina, Figs. 2–8 un fragmento SPEM por fase y Fig. 9 vista general — con lo que §V-C cumple su promesa y el **entregable 3 queda cubierto**. Registrado como fuente normativa. |
| 2026-08-27 | **Diagrama reorganizado por el equipo** en draw.io (lienzo de 4250 → 3340 px de ancho, rótulos reubicados) y exportado a SVG/HTML/PDF. El deck usa `arca-general4.svg`; los encuadres del visor se recalcularon leyendo las posiciones reales del SVG. |
| 2026-08-27 | **Deck del Reto #2 terminado** (`index.html` en la raíz): recuperado desde `reto1/presentacion/v2-corregida.html`, actualizadas las 3 diapositivas existentes al paper v2 (nombre ARCA, orden de enfoques, flujo F1–F7, 11 roles, tres cadencias, cuatro familias de indicadores) y **añadida la diapositiva 4** — mapa interactivo del modelo con 7 fases, 4 compuertas, hitos, banda de apoyo, 8 momentos clave y overlay de ampliación. Añadido después un **mini-diagrama de entradas → interior → salidas** por fase, un segundo diagrama **herramienta ⇢ rol → tarea**, **revelado progresivo** de las actividades al tocarlas, y **un diagrama de destinos propio para cada compuerta** (G1, G2 y G3 dejaron de compartir la misma ficha). Verificado en navegador: 4 diapositivas, sin errores de consola. |
| 2026-08-27 | **`General 4` completada con el nivel de actividad y los patrones**: 18 actividades **A1.1–A7.3** con su rol primario, en panel por fase (antes solo existían las de F5); **CP1–CP4** (Capability Patterns de SPEM 2.0) en panel propio, más marcas de dónde aplica cada uno — CP1 en el microciclo, **CP2 en las cuatro compuertas**, CP3 en la convergencia de pipelines, CP4 sobre F1–F4. Verificado: XML válido, 0 solapamientos, 443 celdas. |
| 2026-08-27 | **Creada la página `General 4`** en `Diagrama-SPEM2.0-ARCA.drawio`, sobre la `General 3` del equipo (v2). Correcciones: iconos 19→32 px y tipografía +1; 20 productos retipados a **Artefacto** (Cuadro II del paper v2); "cadena"→**pipeline**; las dos G3 diferenciadas como **G3.1** (salida de F4) y **G3.2** (salida de F5); herramientas de F6 corregidas según Cuadro III; llave (Concepto) dentro de las cuatro compuertas; **hitos M1–M4**; técnicas movidas **dentro de cada fase** (7 paneles); T1–T7 renombradas a **S1–S7** con ISO/IEC/IEEE 12207; salidas reales de F7 en lugar de las 3 `Declaración de accesibilidad` duplicadas; artefactos de F6 cableados; herramientas del líder técnico en F3. Verificado: XML válido, **0 solapamientos**. |
| 2026-08-27 | **Ingesta del paper ARCA v2** (`reto2/paper/ARCA_paper_v2_en_desarrollo.pdf`): 11 roles con decisión exclusiva, actividades A1.1–A7.3, hitos M1–M4, S1–S7 alineadas con ISO/IEC/IEEE 12207:2017, patrones CP1–CP4, productos tipados Artifact/Deliverable/Outcome, cuatro familias de indicadores. Registrado como fuente normativa por encima de `MODELO_PROCESO.md`. |
| 2026-08-27 | **Creada la página `General 3`** a partir de General 2: 13 de los 14 símbolos SPEM en uso, 7 fases rotuladas, banda transversal T1–T7, panel de métodos y técnicas, leyenda, cadencias anidadas, convergencia de cadenas en F5, compuertas anotadas con rol y destino, 6 artefactos nuevos, 71 correcciones de ortografía. Nombre **ARCA** incorporado. Verificado: XML válido, 0 solapamientos. |
| 2026-08-27 | **Feedback del profesor al paper final** ("trabajo sobresaliente"): valida 7 elementos (combinación contextual, tres cadencias, doble cadena, G1–G3, autoridad separada, responsabilidad social verificable, criterio de frontera) y pide **demostrar empíricamente que el beneficio supera el coste de coordinación**. Cierra la slide 3 y aporta el cierre de la socialización. → `FEEDBACK_RETO1.md`, `PRESENTACION.md`, `MODELO_PROCESO.md` §5 y §10.3, `AUDITORIA_DIAGRAMA.md` (G-17, G-18), `PAPER_SECCION_MODELO.md`. |
| 2026-08-27 | **Auditoría del `.drawio`** (6 páginas, 121 nodos etiquetados en la página `General`): inventario de símbolos, 16 brechas clasificadas en bloqueantes / importantes / menores. → `AUDITORIA_DIAGRAMA.md`. |
