# LEEME — Reto #2: Diseñar un modelo de procesos (SPEM 2.0)

**Curso:** Universidad EAFIT — Procesos Modernos de Desarrollo de Software
**Equipo 2 — Dominio:** Realidad aumentada (RA)
**Metodología:** **ARCA — Augmented Reality Continuous Assurance** (*Aseguramiento Continuo para Realidad Aumentada*)
**Vence:** domingo **30 de agosto de 2026, 23:59** (varios envíos permitidos)

## Qué es esto

`reto2/contexto/` es la **única fuente de verdad** del Reto #2, igual que `reto1/contexto/` lo fue del Reto #1.
Lo que no esté escrito aquí no cuenta como acordado.

## Punto de partida (no se reinventa nada)

El Reto #2 **no es un trabajo nuevo**: es la formalización en SPEM 2.0 de la metodología ya publicada en el
Reto #1. La fuente normativa del contenido es:

- **Paper vigente (ARCA)** → [`reto2/paper/pdms_reto2-2.pdf`](../paper/pdms_reto2-2.pdf) — **es la fuente normativa**:
  secciones I–X, 9 figuras, 8 cuadros, 42 referencias
- **Paper final Reto #1** → [`reto1/entrega-final/Equipo2_2026_Metodologia_AR_EAFIT.pdf`](../../reto1/entrega-final/Equipo2_2026_Metodologia_AR_EAFIT.pdf)
  (punto de partida; superado por el anterior)
- **Diagrama del equipo** → [`reto2/diagrama/Diagrama-SPEM2.0-PMDS.drawio`](../diagrama/Diagrama-SPEM2.0-PMDS.drawio) — página **`General 3`** es la de trabajo; `General 2` se conserva como respaldo
- **Feedback del profesor al Reto #1** → [`FEEDBACK_RETO1.md`](FEEDBACK_RETO1.md) (marca qué defender y qué corregir)

Regla dura: **si el diagrama y el paper se contradicen, gana el paper (versión `pdms_reto2-2.pdf`)** — salvo que el equipo registre
la decisión de cambio en `GESTION_PROYECTO.md` y actualice ambos.

## Mapa de archivos

| Archivo | Para qué |
|---------|----------|
| `LEEME_RETO2.md` | Este mapa + reglas |
| `REQUISITOS.md` | Enunciado literal, fechas, entregables y checklist de cumplimiento |
| `FEEDBACK_RETO1.md` | **Feedback literal del profesor** + qué valida, qué exige y la tabla comentario→modificación de la slide 3 |
| `MODELO_PROCESO.md` | **Especificación canónica** del modelo: F1–F7, roles, tareas, técnicas, artefactos, herramientas, compuertas, retornos, cuellos de botella, métricas |
| `SPEM_CONVENCIONES.md` | Notación SPEM 2.0 acordada: qué icono usa cada cosa y cómo se nombra |
| `AUDITORIA_DIAGRAMA.md` | **Estado real del diagrama vs. lo que pide el enunciado** — brechas priorizadas (G-01…G-16) |
| `ASIGNACION_EQUIPO.md` | Quién modela qué + formato uniforme de entrega de cada sección |
| `PRESENTACION.md` | Entregables 1 y 2: 4 diapositivas + guion de 5 minutos (deck: `index.html` en la raíz) |
| `PAPER_SECCION_MODELO.md` | Entregable 3: estado del paper y checklist de revisión final |
| `GESTION_PROYECTO.md` | Estado, decisiones, bitácora del Reto #2 |

## Apoyos del profesor

En [`reto2/apoyos/`](../apoyos/):

- `ST01605-2021-1-Guía de Apoyo SPEM2.0.pdf` — enunciado + barra de herramientas SPEM 2.0 + metamodelo
- `Plantilla Modelar Procesos SPEM2.0.drawio` — **paleta oficial** de iconos (14 símbolos)
- `The-ADELFE-20-Implementation-phase-in-SPEM-20.png` — ejemplo de referencia de una fase modelada en SPEM
- `Referencias-1.pdf` — bibliografía por dominio (el PDF es imagen; no tiene capa de texto)

## Protocolo (igual que en el Reto #1)

1. **Clasificar** lo que llega (requisito, decisión, sección del modelo, corrección del diagrama…).
2. **Repartir** al archivo que toca:
   - requisito/fecha/rúbrica → `REQUISITOS.md`
   - definición del modelo (fase, rol, artefacto, métrica) → `MODELO_PROCESO.md`
   - notación/símbolos → `SPEM_CONVENCIONES.md`
   - hallazgo sobre el diagrama → `AUDITORIA_DIAGRAMA.md`
   - diapositivas/guion → `PRESENTACION.md`
   - texto para el paper → `PAPER_SECCION_MODELO.md`
   - estado/decisión → `GESTION_PROYECTO.md`
3. **Actualizar bitácora** en `GESTION_PROYECTO.md`.
4. Reportar: archivos tocados, contradicciones con el paper, huecos.
