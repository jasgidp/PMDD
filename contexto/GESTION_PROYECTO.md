# GESTION_PROYECTO — estado, decisiones, glosario y bitácora

Archivo operativo del equipo. Al integrar texto nuevo: actualizar **Estado** + **Bitácora**.

---

## 1. Estado del entregable


**Última actualización:** 2026-08-07

## Paper IEEE (60%) — trabajo en Markdown → convertir al final

| Sección | Responsable | Estado | Palabras actuales vs objetivo | Fuentes usadas | Qué falta |
|---------|-------------|--------|-------------------------------|----------------|-----------|
| Título | Equipo | pendiente | 0 | — | Incluir AR; nombre metodología **aplazado** |
| Autores / afiliación | Equipo | pendiente | 0 | — | Orden autores [FALTA]; EAFIT + curso **ok** |
| Abstract (EN) | por asignar | pendiente | 0 / ~150–200 | — | Redactar en inglés |
| Índice de Términos | por asignar | pendiente | 0 | — | Keywords |
| I. Introducción | por asignar | pendiente | 0 / ~300–450 | — | Redactar (outline ya aprobado) |
| II. Dominio AR | Quinnie | pendiente | 0 / ~450–650 | — | Texto + fuentes |
| III.A GenIA (IA gen. general) | Jose Manuel Carvajal | pendiente | 0 / ~200–350 | — | Él aporta contenido |
| III.B DevOps | Jonathan Sandoval | borrador sanitizado | ver maestro | [@Bass2015] [@Jabbari2016] [@Vaquero2020] | Detalle industrial solo en `privado/` |
| III.C Event Driven Architecture | Lina Ballesteros | redactada | 334 / ~200–350 ✅ | [@Cabane2024] [@RosaBilbao2023] [@Vaquero2020] [@Oberhauser2023] [@AsyncAPI] | Pendiente feedback de socialización |
| III.D Human-Centered Design (HCD) | Alejandro Ríos | **redactada** | 343 / ~200–350 ✅ | [@ISO9241210] [@Seffah2005] [@Ferre2005] [@Graser2024] [@Nielsen1994] [@Paterno2000] [@OMG-IFML] | Fuentes verificadas; extensión dentro de objetivo. Pendiente: consolidar aporte en §IV |
| IV. Espina (6 ejes) + valor diferencial | Equipo | pendiente | 0 / ~700–900 | [@Ceret2013] | Definir roles/formatos/ciclos |
| Conclusión | Equipo | pendiente | 0 / ~150–250 | — | Tras cuerpo |
| Referencias | Equipo | borrador catálogo | ver `FUENTES.md` | [@Ceret2013] | Fuentes AR/enfoques |

## PPT (versionada en `PRESENTACION.md`)

| Artefacto | Archivo | Estado | Qué falta |
|-----------|---------|--------|-----------|
| Socialización (40%) | `PRESENTACION.md` Parte I | esqueleto | Contenido de diapositivas |
| PPT corregida (anexa al 60%) | `PRESENTACION.md` Parte II | pendiente | Feedback de clase |

**Progreso paper:** 0 % redactado. **Outline Fase 4:** aprobado. **4 enfoques:** confirmados en el paper.


---

## 2. Decisiones y supuestos


**Última actualización:** 2026-08-07 (cierre parcial de contexto)

---

## Decisiones tomadas

| ID | Decisión | Fecha | Quién |
|----|----------|-------|-------|
| D1 | Memoria solo en `/contexto/` | 2026-08-07 | Usuario |
| D2 | Citas provisionales `[@Clave]`; IEEE al ensamblar | 2026-08-07 | Usuario |
| D3 | No redactar paper completo hasta aprobar outline Fase 4 | 2026-08-07 | Protocolo |
| D4 | Dominio = **Realidad aumentada** (Equipo 2) | 2026-08-07 | Equipo |
| D5 | Enfoques = GenIA, DevOps, EDA, **HCD** *(sustituye Progressive Delivery, ver D26)* | 2026-08-07 | Enunciado + equipo |
| D6 | Espina = 6 ejes Céret et al. | 2026-08-07 | Enunciado + usuario |
| D7 | Referencias por **orden de aparición** | 2026-08-07 | Usuario |
| D8 | Digital.ai / Gartner = **solo apoyo** | 2026-08-07 | Usuario |
| D9 | ~4 páginas = base, no norma | 2026-08-07 | Usuario |
| D10 | No alucinar; priorizar fuentes académicas | 2026-08-07 | Usuario |
| D11 | Abstract en **inglés** | 2026-08-07 | Usuario |
| D12 | Afiliación: **Universidad EAFIT** — curso **Procesos Modernos de Desarrollo de Software** | 2026-08-07 | Usuario |
| D13 | Trabajo interno en **Markdown**; conversión a formato IEEE de entrega **al final** | 2026-08-07 | Usuario |
| D14 | Fechas del enunciado: no priorizar / “no importan” para la gestión asistida | 2026-08-07 | Usuario |
| D15 | Nombre de la metodología: **aplazar** hasta construir el trabajo | 2026-08-07 | Usuario |
| D16 | GenIA = **IA generativa en general**; contenido a cargo de Jose Manuel | 2026-08-07 | Usuario |
| D17 | DevOps: caso industrial de augmentación en tiempo real (detalle **solo** en `contexto/privado/`) | 2026-08-07 | Usuario |
| D23 | §III.B: versión completa en privado; versión sanitizada en borrador público | 2026-08-07 | Usuario |
| D24 | Información del empleador / infra interna **no se versiona** (`.gitignore` → `contexto/privado/`) | 2026-08-07 | Usuario |
| D18 | Versionar la **PPT** en `PRESENTACION.md` | 2026-08-07 | Usuario |
| D19 | No hay rúbrica analítica con sub-pesos **aún** (solo 40/60 + checklist) | 2026-08-07 | Usuario |
| D20 | Los **cuatro** enfoques van al paper (GenIA, DevOps, EDA, **HCD**) | 2026-08-07 | Usuario |
| D21 | Outline de `PLANTILLA_PAPER.md` **aprobado** (Fase 4) | 2026-08-07 | Usuario |
| D25 | Estructura de `contexto/` consolidada (7 archivos públicos + `privado/`) | 2026-08-07 | Usuario |
| D26 | **Progressive Delivery se descarta**; Alejandro Ríos pasa a **Human-Centered Design (HCD)**. Motivo: HCD tiene literatura AR específica y normalización ISO, y cubre la validación con usuarios —que la evidencia señala como déficit del dominio [@Graser2024]—; Progressive Delivery quedaba sin respaldo bibliográfico propio en AR. Siguen siendo 4 enfoques, cumple la rúbrica. | 2026-08-07 | Equipo (Alejandro) |

---

## Supuestos

| ID | Supuesto | Estado |
|----|----------|--------|
| S1 | Metodología vía espina/taxonomía | Confirmado (enunciado) |
| S2 | Dominio Agile | Descartado → AR |
| S3 | ~4 páginas | Base orientativa |
| S4 | Cuerpo en español | Vigente |
| S5 | Sin biografías IEEE de revista | Vigente |
| S6 | Año 2026 de las fechas del enunciado | Irrelevante para gestión (D14); se deja anotado en 02 |
| S7 | Los cuatro enfoques entran en el paper | **Confirmado** (D20) |
| S8 | SUPUESTO: el caso industrial de augmentación broadcast (detalle en `privado/`) es transferible al dominio AR del curso con el matiz broadcast ≠ AR móvil | Vigente |

---

## Contradicciones

| ID | Estado |
|----|--------|
| C1–C3 | Resueltas (ver entradas previas) |

---

## Preguntas aún abiertas (mínimas)

1. **Orden de autores** en el paper.  
2. Canal LMS concreto (opcional).  
3. Nombre de la metodología (aplazado, D15).  
4. ¿Acortar §III.B sanitizado?  
5. En la entrega final al profesor: ¿usar versión sanitizada o la de `privado/` (solo local)?


---

## 3. Glosario


**Última actualización:** 2026-08-07

| Término / sigla | Definición o traducción acordada | Fuente | Notas |
|-----------------|----------------------------------|--------|-------|
| Espina de pescado (atributos) | En este reto: Ciclo, Colaboración, Artefactos, Uso recomendado, Madurez, Flexibilidad | Enunciado Reto #1 | Equivalen a los 6 ejes de Promote / Céret et al. |
| Promote | Process Models Taxonomy for Enlightening choices | [@Ceret2013] | Base teórica de la espina |
| AR / Realidad aumentada | Dominio del Equipo 2: Realidad aumentada (*Augmented Reality*) | Asignación equipo | Primera mención: “realidad aumentada (AR)” |
| GenIA | IA generativa en sentido amplio (no un marco propietario del curso, salvo que Jose Manuel precise otro) | Usuario 2026-08-07 | Contenido: Jose Manuel Carvajal |
| DevOps | Enfoque CI/CD + colaboración dev/ops; caso industrial de augmentación en tiempo real documentado solo en `privado/` | [@Bass2015] [@Jabbari2016] | No publicar detalle de empleador en repo público |
| Augmentación (broadcast) | Superposición de gráficos sobre video en tiempo real (matiz vs AR móvil) | Notas en `privado/` | Usar con cuidado en el paper |
| Universidad EAFIT | Afiliación institucional del equipo | Usuario | Pie IEEE |
| PMDD / Procesos Modernos de Desarrollo de Software | Nombre del curso | Usuario (ortografía corregida: Software) | Afiliación |
| EDA / Event Driven Architecture | Arquitectura orientada a eventos | Equipo (Lina) | Expandir en primera mención |
| HCD / Human-Centered Design | Diseño centrado en el humano; normalizado en ISO 9241-210 | Equipo (Alejandro) | Expandir en primera mención. Sustituye a Progressive Delivery (D26) |
| Metodología de SW | Forma de trabajo / método que el equipo va a proponer (primera aproximación) | Enunciado | Distinguir de “método”/“modelo de proceso” según [@Ceret2013] cuando haga falta |
| Ciclo | Eje 1 espina / Axis Cycle | [@Ceret2013] + enunciado | |
| Colaboración | Eje 2 / Collaboration | idem | Incluye roles |
| Artefactos | Eje 3 / Artifacts | idem | Incluye formatos |
| Uso recomendado | Eje 4 / Recommended Use | idem | |
| Madurez | Eje 5 / Maturity | idem | |
| Flexibilidad | Eje 6 / Flexibility | idem | |
| Valor diferencial | Qué aporta la metodología propuesta frente a las actuales del dominio | Enunciado E6/E7 | Sección obligatoria |

## Registro

| Aspecto | Valor | Estado |
|---------|-------|--------|
| Idioma cuerpo | Español | Confirmado |
| Persona | Impersonal / “se propone” | Provisional (plantilla IEEE) |


---

## 4. Bitácora

> **Nota de estructura (D25):** desde la consolidación, la memoria pública vive en 7 archivos + `privado/`. Entradas antiguas de esta bitácora pueden nombrar `00_`–`09_`, `FICHA_*` o `PPT_*`; ese contenido ya está en `REQUISITOS.md`, `PLANTILLA_PAPER.md`, `FUENTES.md`, `GESTION_PROYECTO.md` y `PRESENTACION.md`.

Registros en orden cronológico (más reciente abajo).

---

## 2026-08-07 — Inicialización (Fases 1–2)

**Qué se hizo**
- Inventario completo del directorio PMDD.
- Lectura/extracción de: PDF Digital.ai (retos), Céret et al. 2013, plantilla IEEE `.doc`, ebook Gartner 2024, OCR del ejemplo IEEE diligenciado (PDF escaneado).
- Creación de `contexto/` y archivos de memoria.
- Verificación web del DOI de Céret et al. y existencia pública del 17th State of Agile (Digital.ai).

**De quién venía**
- Materiales: repositorio del usuario.
- Protocolo de trabajo: mensaje de inicio del usuario.

**Archivos creados/actualizados**
- `contexto/FICHA_DE_REQUISITOS.md` (nuevo)
- `contexto/00_CONTEXTO.md` (nuevo)
- `contexto/01_INSTRUCCIONES.md` (nuevo)
- `contexto/02_CONDICIONES_ENTREGA.md` (nuevo)
- `contexto/03_RUBRICA.md` (nuevo — vacía: sin rúbrica en repo)
- `contexto/04_PLANTILLA.md` (nuevo — estructura provisional)
- `contexto/05_FUENTES.md` (nuevo)
- `contexto/06_ESTADO_ENTREGABLE.md` (nuevo)
- `contexto/07_DECISIONES_Y_SUPUESTOS.md` (nuevo)
- `contexto/08_GLOSARIO.md` (nuevo)
- `contexto/09_BITACORA.md` (este archivo)
- `contexto/BORRADOR_MAESTRO.md` (nuevo — vacío de contenido académico)

**Hallazgo bloqueante**
- No hay enunciado del profesor, rúbrica, fecha ni mínimo de fuentes en el repositorio.

---

## 2026-08-07 — Ingesta enunciado Reto #1 + respuestas del equipo

**Clasificación:** enunciado oficial (chat) + asignaciones de dominio/enfoques + aclaraciones de formato/fuentes.

**Qué se integró**
- Reto #1: Dominio, Enfoque y Espina de Pescado; paper IEEE; socialización 40% / paper 60%.
- Dominio: Realidad aumentada (Quinnie). Enfoques: GenIA, DevOps (Jonathan), EDA, Progressive Delivery. *(Nota posterior: Progressive Delivery sustituido por HCD — ver D26 y entrada de bitácora del 2026-08-07.)*
- Espina = 6 ejes; referencia `A taxonomy…pdf` [@Ceret2013].
- Fechas: sábado próximo (socialización); miércoles 12 ago (paper + PPT corregida).
- Refs por aparición; ~4 pp. base no norma; Digital.ai/Gartner solo apoyo; no alucinar; fuentes académicas prioritarias.

**Archivos actualizados**
- `FICHA_DE_REQUISITOS.md`, `00_CONTEXTO.md`, `01_INSTRUCCIONES.md`, `02_CONDICIONES_ENTREGA.md`, `03_RUBRICA.md`, `04_PLANTILLA.md`, `05_FUENTES.md`, `06_ESTADO_ENTREGABLE.md`, `07_DECISIONES_Y_SUPUESTOS.md`, `08_GLOSARIO.md`, `BORRADOR_MAESTRO.md`, `09_BITACORA.md`

**Contradicciones**
- C1 y C2 resueltas; C3 (materiales Agile vs dominio AR) resuelta como “solo apoyo”.
- No se sobrescribió en silencio ningún requisito previo del enunciado (no existía).

**[SIN FUENTE VERIFICADA]**
- Ninguna afirmación nueva de contenido AR/DevOps/etc. redactada aún; solo requisitos y roles.

**Huecos que quedan**
- Canal de entrega, Abstract idioma, afiliación, orden autores, nombre metodología, sub-rúbrica, confirmación fechas calendario, alcance DevOps/GenIA.

---

## 2026-08-07 — Cierre parcial de contexto (respuestas usuario)

**Clasificación:** condiciones de entrega + afiliación + Abstract + flujo MD + PPT + alcance GenIA/DevOps.

**Qué se añadió/cambió**
- Abstract en inglés; afiliación Universidad EAFIT / Procesos Modernos de Desarrollo de Software.
- Trabajo en MD; conversión IEEE al final.
- Fechas: no priorizar (D14). Nombre metodología: aplazado (D15).
- GenIA = IA generativa general (Jose Manuel). DevOps = caso industrial (luego en `privado/`).
- PPT versionada (hoy: `PRESENTACION.md` Partes I y II; antes `PPT_SOCIALIZACION.md` / `PPT_CORREGIDA.md`).
- Sin rúbrica analítica extra aún (D19).

**Huecos mínimos restantes (entonces):** orden autores; S7; outline Fase 4.

---

## 2026-08-07 — Aprobación Fase 4 + 4 enfoques

- D20: los 4 enfoques van al paper.  
- D21: outline `PLANTILLA_PAPER.md` aprobado (antes `04_PLANTILLA.md`).  
- S7 confirmado.  
- Siguiente: redacción incremental; DevOps con caso industrial restringido.

---

## 2026-08-07 — Sección III.B DevOps (borrador)

- Definición académica [@Bass2015] [@Jabbari2016]; puente AR [@Vaquero2020].
- Checklist E4 cubierto.
- Detalle del caso industrial **no** queda en archivos públicos (ver entrada de privacidad).

---

## 2026-08-07 — Repo en GitHub

- Repositorio: https://github.com/jasgidp/PMDD  
- Rama: `main`  
- Incluye materiales del curso + `contexto/` (sin `.venv` ni `_extract`).

---

## 2026-08-07 — Sondeo industrial (augmentación) + reescritura III.B

- Notas y versión completa movidas después a `contexto/privado/` (gitignored).
- Matiz: augmentación broadcast ≠ AR móvil.

---

## 2026-08-07 — Privacidad: industria → gitignore

- Añadido `contexto/privado/` al `.gitignore`.
- Detalle industrial (notas, §III.B completo, fuentes internas) solo en `privado/`.
- Borrador público / PPT / glosario / fuentes: **sanitizados**.
- D24: esa información no se versiona ni se publica en el remoto.

---

## 2026-08-07 — Reorganización: menos archivos

- Consolidación pública: `REQUISITOS.md`, `PLANTILLA_PAPER.md`, `FUENTES.md`, `GESTION_PROYECTO.md`, `PRESENTACION.md`, `LEEME_EQUIPO.md`, `BORRADOR_MAESTRO.md`.
- Eliminados los `00`–`09`, ficha suelta y PPTs separados (contenido preservado en los nuevos).
- `privado/III_B_DEVOPS_GENIUS.md` ampliado (checklist E4 + lenguaje principiante).
- Protocolo de ingesta confirmado en `LEEME_EQUIPO.md`.

---

## 2026-08-07 — READMEs + referencias a la estructura nueva

**Clasificación:** documentación / mapa del repo.

**Qué se hizo**
- Creados `README.md` (raíz), `contexto/README.md` y actualizado `privado/README.md`.
- Corregidas referencias rotas a `01_INSTRUCCIONES`, `03_RUBRICA`, `04_PLANTILLA`, `FICHA_*`, `PPT_*`, `09_BITACORA`.
- D25: estructura consolidada documentada.
- Bitácora histórica anotada para no confundir nombres viejos con archivos actuales.

**Archivos:** `README.md`, `contexto/README.md`, `LEEME_EQUIPO.md`, `REQUISITOS.md`, `PLANTILLA_PAPER.md`, `PRESENTACION.md`, `GESTION_PROYECTO.md`, `privado/README.md`.

---

## 2026-08-07 — Cambio de enfoque: Progressive Delivery → HCD + §III.D redactada

**Clasificación:** decisión de alcance + prosa de sección + fuentes.

**Qué se hizo**
- **D26:** se descarta Progressive Delivery; Alejandro Ríos asume **Human-Centered Design (HCD)**. Siguen siendo 4 enfoques (mínimo de la rúbrica cumplido: DevOps y GenIA + 2).
- Actualizadas todas las referencias al enfoque en los archivos de contexto (roster, outline, rúbrica, PPT, cola de fuentes, glosario).
- Redactada **§III.D HCD** en `BORRADOR_MAESTRO.md`: qué es, relación con IS, ejecución, técnicas/herramientas, lenguajes de modelado, métodos, y razón de elección.
- Añadida la **tabla de aporte a los 6 ejes** de la espina al final de §III.D, como insumo para §IV.
- Añadidas **7 fuentes** a `FUENTES.md`.
- Añadido a `PLANTILLA_PAPER.md` §IV el desglose de los **34 sub-ejes** de [@Ceret2013], extraídos del PDF del repo.

**Fuentes nuevas:** `[@ISO9241210]`, `[@Seffah2005]`, `[@Ferre2005]`, `[@Graser2024]`, `[@Nielsen1994]`, `[@Paterno2000]`, `[@OMG-IFML]`.

**Verificación:** `[@Graser2024]` confirmada contra arXiv — autores (S. Graser, F. Kirschenlohr, S. Böhm), título, fecha y publicación en actas CENTRIC 2024 (Venecia, pp. 23–40). Se cita la versión de actas, no el preprint.

**Huecos / pendientes**
- ⚠️ Falta confirmar número de página exacto en `[@Ferre2005]`, `[@Nielsen1994]` y `[@Paterno2000]` antes del ensamblado IEEE.
- §III.D quedó en ~450 palabras contra un objetivo de 200–350: hay que recortar o renegociar el objetivo con el equipo.
- §IV sigue pendiente: falta el insumo de espina de los otros tres enfoques para consolidar.

**Contradicción resuelta:** el repo asignaba Progressive Delivery a Alejandro Ríos en 7 archivos mientras el acuerdo del equipo era HCD. Queda alineado.

**Archivos:** `LEEME_EQUIPO.md`, `REQUISITOS.md`, `PLANTILLA_PAPER.md`, `BORRADOR_MAESTRO.md`, `FUENTES.md`, `PRESENTACION.md`, `GESTION_PROYECTO.md`.

---

## 2026-08-07 — §III.D: cita faltante, compresión y cierre de fuentes

**Clasificación:** corrección de sección + fuentes.

**Qué se hizo**
- **Corregido:** `[@Picardi2024]` figuraba en `FUENTES.md` sin citarse en la prosa. En IEEE las referencias se numeran por orden de aparición, así que una fuente no citada no puede numerarse. Se integró en el párrafo de razón de elección.
- **Comprimida §III.D de 483 a 343 palabras**, dentro del objetivo de 200–350. Se mantienen las seis preguntas de la rúbrica y las ocho citas. Lo recortado fue redundancia de redacción, no contenido: enumeración completa de los seis principios ISO y desglose por fase de las técnicas.
- **Fuentes cerradas:** confirmadas páginas de `[@Ferre2005]` (pp. 173–200) y `[@Nielsen1994]` (pp. 25–62), y edición de `[@Paterno2000]` (1.ª ed., 2000). Sin marcas pendientes.
- `[@ISO9241210]` reformateada al estilo IEEE de normas (sin la organización como autor).

**Pendiente para el equipo**
- Fijar criterio único de formato para normas y especificaciones: `[@OMG-IFML]` todavía lleva la organización como autor, `[@ISO9241210]` ya no.
- Confirmar el DOI de `[@Picardi2024]`: se derivó del patrón MDPI, la página devolvió 403.
- **§IV sigue vacía.** Es lo único que el profesor pidió explícitamente para llegar a clase con una propuesta. Falta el insumo de espina de GenIA, DevOps y EDA.

**Archivos:** `BORRADOR_MAESTRO.md`, `GESTION_PROYECTO.md`.
