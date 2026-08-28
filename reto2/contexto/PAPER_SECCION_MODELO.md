# PAPER — Entregable 3: incorporar el modelo al paper

**Vence:** domingo 30-ago-2026, 23:59.
**Pide el enunciado:** *"Incorporar este modelo al paper, explicando **las interacciones, los ciclos y los
artefactos** propuestos."*

Fuente del texto: `MODELO_PROCESO.md`. Fuente del formato: paper final del Reto #1
(`reto1/entrega-final/`, LaTeX en `reto1/paper/paper.tex`).

---

## 1. Dónde va (decisión pendiente de confirmar por el equipo)

**Opción recomendada:** nueva subsección **§IV-J "Modelo de proceso en SPEM 2.0"**, después de §IV-I
(comparación frente a Spiral, RAD y XP) y antes de las conclusiones.

Razón: §IV ya contiene toda la definición del método por ejes; el modelo SPEM es su **representación operativa**,
no un tema nuevo. Alternativa: sección **V** propia si el texto supera ~1.200 palabras.

---

## 2. Estructura propuesta de §IV-J (≈900–1.200 palabras + 1 figura)

| Subapartado | Contenido | Palabras |
|-------------|-----------|----------|
| **1) Propósito y notación** | Por qué SPEM 2.0; qué símbolo representa qué (fase, iteración, tarea, rol, producto de trabajo, herramienta, concepto, patrón de proceso); qué se representa fuera del estándar (compuertas como rombo) y por qué | 150 |
| **2) Los ciclos** | Las **tres cadencias anidadas**: CI/CD continua → microciclo de 2 semanas → incremento validado de 1–3 meses. Por qué el microciclo **no** recorre las siete fases (no es cascada en miniatura). Los seis elementos de control de cierre | 250 |
| **3) Las interacciones** | Flujo F1→F7 + los **retornos**: quién detecta, quién registra la causa, quién decide el destino y a qué fase se vuelve. Tabla "qué falla → quién retoma → a dónde vuelve". La **doble cadena** de F5 y su punto de convergencia | 350 |
| **4) Los artefactos** | Los productos de trabajo por fase y el **criterio de formalización de frontera**; los dos artefactos de lectura obligatoria (informe de evaluación con usuarios y contrato de frontera) como mecanismo real de coordinación | 250 |
| **5) Actividades de soporte** | Los siete procesos transversales T1–T7 y por qué son transversales y no fases | 150 |
| **6) Coste de coordinación y balance neto** | Respuesta al feedback: el método introduce un coste (compuertas, contratos, entregables, nueve roles) y la hipótesis falsable es que el beneficio lo supera. Añadir la tercera familia de indicadores y declarar la hipótesis (`MODELO_PROCESO.md` §10.3) | 200 |
| **Figura** | Diagrama SPEM 2.0 completo, a **doble columna** (`figure*`), con leyenda de símbolos y pie explicativo | — |

---

### Dónde tocar además de §IV-J

| Sección existente | Cambio |
|-------------------|--------|
| **§IV-F (Madurez)** | Añadir la familia de **coste de coordinación** a las dos familias de indicadores y enunciar el **balance neto** como hipótesis falsable |
| **§V (Conclusiones)** | Reformular el trabajo futuro: no basta "instrumentar y contrastar"; hay que decir que se contrasta el **beneficio neto frente al coste de coordinación que el método introduce** |
| **§IV-A (compuertas)** | Añadir la regla de no-sustituibilidad de G1 y G2 (`MODELO_PROCESO.md` §5) — es el diferencial que el profesor identificó |

---

## 3. Reglas de coherencia (verificar antes de entregar)

- [ ] Todo elemento del diagrama existe en el texto y viceversa — **cero elementos huérfanos**.
- [ ] Los nombres de fases, roles, artefactos y compuertas son **idénticos** en paper, diagrama y presentación.
- [ ] La condicionalidad (`*` EDA / GenIA) se explica en el pie de figura.
- [ ] El Cuadro II del paper (fases, enfoques activos, salidas, compuertas) **no contradice** el diagrama.
- [ ] La numeración de figuras se corrige: la espina es la Fig. 1, el modelo SPEM será la **Fig. 2**.
- [ ] Lo que el profesor destacó del paper aparece **también** en la figura (cadencias, compuertas con rol, autoridad separada, transversales, criterio de frontera)
- [ ] Las referencias nuevas (OMG SPEM 2.0) se añaden **al final** de la lista — el paper cita por orden de
      aparición, así que revisar dónde cae la primera mención.

## 4. Referencia nueva a añadir

```
[31] Object Management Group, Software & Systems Process Engineering Meta-Model Specification (SPEM),
     Version 2.0, OMG Document formal/2008-04-01, Apr. 2008.
```

Fuente sugerida por el profesor en la guía de apoyo: https://www.omg.org/spec/SPEM/2.0

---

## 5. Qué **no** hay que hacer

- No reescribir §II ni §III: el Reto #2 **evoluciona** el paper, no lo reemplaza.
- No introducir en el diagrama elementos que el paper no sostenga con literatura.
- No cambiar decisiones del modelo sin registrarlas en `GESTION_PROYECTO.md` **y** actualizar los tres
  entregables (paper, diagrama, presentación) a la vez.
