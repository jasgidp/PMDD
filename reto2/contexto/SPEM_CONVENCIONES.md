# SPEM_CONVENCIONES — notación acordada

Base: `reto2/apoyos/Plantilla Modelar Procesos SPEM2.0.drawio` (paleta oficial del profesor) y
`ST01605-2021-1-Guía de Apoyo SPEM2.0.pdf`. **Nadie improvisa símbolos.**

---

## 1. Paleta oficial (14 símbolos de la plantilla)

`Grupo` · `Iteración` · `Fase` · `Artefacto` · `Biblioteca` · `Concepto` · `Dominio` · `Herramienta` ·
`Patrón de Proceso` · `Producto de Trabajo` · `Rol` · `Actividad` · `Proceso de Liberación` · `Tarea`

### Uso en nuestro modelo

| Símbolo SPEM | Lo usamos para | Ejemplos |
|--------------|----------------|----------|
| **Fase** | Cada una de F1…F7 | `F1. Encuadre y contexto de uso` |
| **Iteración** | El **microciclo de 2 semanas** | `Microciclo (2 semanas)` |
| **Proceso de Liberación** | El **incremento validado** (1–3 meses) y la promoción a producción | `Incremento validado (2–6 microciclos)` |
| **Actividad** | Agrupador dentro de una fase cuando hay >3 tareas o dos cadenas paralelas | `Cadena de código`, `Cadena de contenido` |
| **Tarea** | Trabajo concreto y atómico | `Definir anclaje espacial` |
| **Rol** | Los 9 internos + 2 externos, **y solo esos** | `Líder técnico`, `Usuario final` |
| **Producto de Trabajo** | Artefactos que produce o consume una tarea | `Contrato de frontera versionado` |
| **Artefacto** | Variante para artefactos **formales/ejecutables** (contratos, pipelines, manifiesto) | `Manifiesto de contenido` |
| **Concepto** | **Métodos y técnicas** (lo que el enunciado pide "claramente visible") | `SUS`, `NASA-TLX`, `RAG`, `TDD`, `Wizard of Oz` |
| **Herramienta** | Producto software concreto | `Unity`, `Kafka`, `Terraform` |
| **Biblioteca** | Repositorios de conocimiento reutilizable | `Repositorio de hallazgos UX`, `Registro de derechos` |
| **Dominio** | Agrupación de productos de trabajo por naturaleza | `Dominio: contenido de augmentación` |
| **Patrón de Proceso** | Los **procesos de apoyo transversales** (T1–T7) | `Gestión de derechos y licencias` |
| **Grupo** | Encuadre visual de una fase o carril | caja contenedora de F1 |

> ⚠️ **Regla:** un enfoque (GenIA, DevOps, EDA, HCD) **nunca** lleva icono de Rol. Se representa como
> marca de condicionalidad o como `Patrón de Proceso`, no como persona.

---

## 2. Elementos sin símbolo SPEM propio → convención del equipo

SPEM 2.0 no tiene un icono de compuerta. Se acuerda:

| Elemento | Representación | Anotación obligatoria |
|----------|----------------|-----------------------|
| **Compuerta de retorno (G1, G2, G3)** | Rombo (decisión), color distintivo | `Gn — qué verifica` + **rol que la ejecuta** + salidas `[ok]` y `[falla: causa] → Fn` |
| **Hito de incremento validado** | Elipse | `Incremento validado — acepta: PO` |
| **Condicionalidad** | Sufijo `*` en el nodo + nota al pie | `* solo si EDA` / `* solo si GenIA` |
| **Retorno** | Flecha **discontinua roja** | siempre etiquetada con la causa |
| **Flujo normal** | Flecha continua | — |

**Toda página que se presente debe llevar la leyenda visible** con la paleta y estas convenciones.

---

## 3. Convenciones de nombrado

| Tipo | Regla | Ejemplo correcto | Incorrecto |
|------|-------|------------------|------------|
| Fase | `Fn. Sustantivo` | `F3. Diseño y arquitectura` | `Diseño` |
| Tarea | **verbo en infinitivo** + objeto | `Definir contrato de frontera` | `Contrato de frontera` |
| Producto de trabajo | **sustantivo**, sin verbo | `Registro de derechos` | `Registrar derechos` |
| Rol | nombre del rol **tal como está en el paper** | `Responsable de derechos y licencias` | `Derechos` (abreviado sin leyenda) |
| Técnica | nombre propio de la técnica | `NASA-TLX` | `medir carga` |

**Tildes y ortografía obligatorias**: el diagrama es un entregable evaluado. Ver la lista de correcciones
pendientes en `AUDITORIA_DIAGRAMA.md` (G-15).

---

## 4. Layout acordado

```
  ┌── leyenda SPEM ──┐
  │                  │
  F1 → F2 → F3 → F4 →[G3*]→ F5 →[G3*]→ F6 →[G1]→[G2]→ F7 →( Incremento validado )
   ↑     ↑     ↑      ↑                        │  │      │
   └─────┴─────┴──────┴──── retornos rojos ────┘──┘      └→ nuevo microciclo
  ────────────────────────────────────────────────────────────────────────
  BANDA TRANSVERSAL (T1–T7): derechos · configuración · microciclo · riesgos IA · observabilidad · resp. social · medición
```

- Fases de izquierda a derecha, en carriles por rol dentro de cada fase.
- **Retornos por debajo**, en rojo discontinuo, sin cruzar el flujo principal.
- **Banda transversal al pie**, cruzando todas las fases (esto es lo que responde a "actividades de soporte").
- Herramientas y técnicas **ancladas a su tarea**, no flotando.

---

## 5. Higiene del archivo `.drawio`

- **Una sola página final** llamada `Modelo de proceso` (o `General`). Las páginas por persona son borrador.
- **No entregar el archivo con páginas vacías** (hoy `Alejandro Rios`, `Lina Ballesteros`, `Jose Manuel` y
  `Jonathan` están vacías) ni con una copia duplicada del modelo completo (hoy `Quinnie` duplica `General`).
- Exportar además a **PNG/PDF en alta resolución** para la diapositiva 4 y para la figura del paper.
- El archivo vive en `reto2/diagrama/Diagrama-SPEM2.0-PMDS.drawio` y se versiona en git.
