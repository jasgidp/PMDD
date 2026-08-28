# PAPER — Entregable 3: el modelo dentro del artículo

**Vence:** domingo 30-ago-2026, 23:59.
**Pide el enunciado:** *"Incorporar este modelo al paper, explicando las interacciones, los ciclos y los artefactos propuestos."*

**Versión vigente:** [`reto2/paper/pdms_reto2-2.pdf`](../paper/pdms_reto2-2.pdf) — 17 páginas.
Versión anterior conservada: `ARCA_paper_v2_en_desarrollo.pdf`.

---

## 1. Estado: el entregable 3 está cubierto

**El artículo está completo**, no es un borrador. Título: *ARCA: un modelo de proceso para el desarrollo de
software en realidad aumentada con aseguramiento continuo de experiencia, rendimiento y derechos*.

| Elemento | Estado |
|---|---|
| Secciones **I a X** | ✅ completas |
| **9 figuras** | ✅ Fig. 1 espina · **Figs. 2–8: un fragmento SPEM por fase (F1…F7)** · Fig. 9 vista general del modelo |
| **8 cuadros** (I–VIII) | ✅ |
| **42 referencias** | ✅ |

Las tres cosas que el enunciado nombra están cubiertas y localizables:

| Lo que pide el enunciado | Dónde está |
|---|---|
| **Los ciclos** | §V-B — las tres cadencias anidadas y su relación con las compuertas |
| **Las interacciones** | §V-I — los tres planos superpuestos + la tabla de destinos de retorno por causa |
| **Los artefactos** | §V-E y Cuadro II — con el tipado SPEM Artifact / Deliverable / Outcome |

Y §V-C cumple ahora su promesa al pie de la letra: *"Cada fase se presenta con el fragmento del modelo SPEM 2.0
que le corresponde **(Figs. 2–8)**"*.

> **Historial de este archivo.** Sus dos versiones anteriores planificaban redactar una §IV-J y luego señalaban
> que faltaban las figuras. Ambas cosas quedaron resueltas por el propio equipo: el modelo vive en una **sección V
> propia** —ubicación correcta— y las figuras ya están insertadas.

---

## 2. Estructura de §V, para ubicarse rápido

| Subsección | Contenido |
|---|---|
| V-A | Convenciones de modelado: elementos de SPEM 2.0 usados y marca `*` de condicionalidad |
| V-B | Vista de ciclo de vida: tres cadencias y compuertas |
| V-C | Recorrido fase por fase (V-C1…V-C7), cada una con su figura |
| V-D | Roles y autoridad — Cuadro I: 11 roles con su decisión exclusiva |
| V-E | Productos de trabajo — Cuadro II |
| V-F | Métodos, técnicas y herramientas — Cuadro III |
| V-G | Actividades de apoyo S1–S7 — Cuadro IV, alineadas con ISO/IEC/IEEE 12207:2017 |
| V-H | Patrones de proceso reutilizables CP1–CP4 |
| V-I | Interacciones entre planos + destinos de retorno |

---

## 3. Revisión final antes de enviar (checklist)

- [ ] **Coherencia de nombres** entre el diagrama reorganizado, el paper y la presentación: fases, actividades
      A1.1–A7.3, roles, compuertas G1/G2/G3, apoyos S1–S7, patrones CP1–CP4.
- [ ] Las **Figs. 2–8** se leen a tamaño de impresión (texto de los iconos legible en una columna).
- [ ] La **Fig. 9** va a doble columna (`figure*`) y su pie explica la marca `*` de condicionalidad.
- [ ] Referencias cruzadas de figuras consecutivas y sin huecos.
- [ ] La referencia a **OMG SPEM 2.0** está numerada (el texto la cita como [33]).
- [ ] Ortografía y tildes en los pies de figura.

## 4. Qué NO hay que hacer

- No reescribir §II ni §III: dominio y enfoques están cerrados.
- No añadir al diagrama elementos que el paper no sostenga con literatura.
- No cambiar decisiones del modelo sin registrarlas en `GESTION_PROYECTO.md` **y** actualizar los tres
  entregables a la vez (paper, diagrama y presentación).
