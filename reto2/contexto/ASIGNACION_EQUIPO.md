# ASIGNACIÓN — Reto #2

Acuerdo tomado por el equipo. Cada persona modela su bloque en SPEM 2.0 y **Quinnie integra visualmente**
el Draw.io final para que todos usen los mismos símbolos.

---

## 1. Tres acuerdos globales (antes de separarse)

1. **Microciclo de 2 semanas** como unidad de planificación (y el incremento validado de 1–3 meses encima).
2. **Convención visual SPEM 2.0** → `SPEM_CONVENCIONES.md`. Nadie improvisa símbolos.
3. **Entrada y salida principal** de cada bloque, para que las piezas encajen sin retoques.

---

## 2. Reparto

| Persona | Responsable de | Brechas de `AUDITORIA_DIAGRAMA.md` que le tocan |
|---------|----------------|--------------------------------------------------|
| **Quinnie** | **F1 + F2** · **integración visual del Draw.io final** | G-01 (rótulos), G-09 (duplicados), G-12 (leyenda), G-16 (consolidar páginas) |
| **José Manuel** | **F3** · **revisor de consistencia técnica** del modelo completo (nombres de artefactos, contratos, pipelines, retornos) | G-10 (condicionalidad EDA) |
| **Lina** | **F4 + G3** | G-06 (rol de datos, destipar GenIA), G-07 (anotar G3), G-11 (storyboards) |
| **Jhonnatan** | **F5** (doble cadena) | G-03 (Actividad en F5), G-05 (banda transversal, con Alejo), G-10 |
| **Alejo** | **F6 + F7 + G1/G2** · **métricas metodológicas y económicas** | G-02, G-07, G-08, G-13, G-14 |

---

## 3. Detalle por persona

### Quinnie — F1 + F2 (+ integración)
Dejar claras entradas, actividades, roles, artefactos y retornos de:
- **F1:** idea, usuarios, entorno y restricciones → UX + Usuario final + PO → contexto de uso + alcance.
  Retorno desde **G2** cuando el problema sea contexto, privacidad o accesibilidad.
- **F2:** requisitos F/NF · contrato de frontera → UX + Líder técnico (+ Dev servicios si EDA).
  Retorno por requisitos incompletos o contrato ambiguo.
- **Integración:** una sola página final, leyenda visible, mismos símbolos, sin duplicados ni páginas vacías.

### José Manuel — F3 (+ consistencia técnica)
Requisitos + contrato como entrada · diseño de arquitectura · **ADR** · especificación de pipelines ·
Líder técnico + DevOps + Dev RA/servicios · **retorno de G1 cuando la causa sea arquitectónica**.
Además: revisor de consistencia de nombres de artefactos, contratos, pipelines y retornos en todo el modelo.

### Lina — F4 + G3
- **F4:** requisitos de experiencia + arquitectura · prototipos · activos · evaluación temprana con usuarios ·
  derechos y licencias · GenIA si aplica.
- **G3:** calidad · trazabilidad · procedencia · derechos del contenido generado.
- Debe quedar explícito: `G3 falla → Contenido + Derechos (+ Datos) → F4 / F5`.
- Mostrar el **cuello de botella de autoría de contenido**: es el diferenciador más fuerte del dominio RA.

### Jhonnatan — F5 (doble cadena)

```
CÓDIGO                        CONTENIDO
Dev RA                        Resp. contenido
Dev servicios                 Derechos
DevOps
    ↓                             ↓
  Build                      Manifiesto
    \                           /
     \                         /
          INTEGRACIÓN
               ↓
        Build integrado
```

Entradas · roles · artefactos · integración · G3 si hubo contenido generado · retornos por código,
integración, contenido o derechos. Y sobre todo el cuello de botella: **una cadena puede estar lista
mientras la otra bloquea el incremento**.

### Alejo — F6 + F7 + G1/G2 (+ métricas)
- **F6:** verificación técnica · evaluación con usuarios · G1 · G2 · evidencias.
- **G1:** Calidad detecta y registra la causa; **el Líder técnico decide si vuelve a F3 o F5**.
- **G2:** UX + Derechos + Usuario final; puede devolver a F1, F2 o F4.
- Debe quedar clarísimo: **solo si G1 y G2 pasan, el incremento avanza a F7**.
- **F7:** despliegue · telemetría · feedback · backlog · nuevo microciclo.
- Métricas metodológicas y económicas (`MODELO_PROCESO.md` §10).

---

## 4. Formato uniforme de entrega (obligatorio para los cinco)

Cada bloque se entrega con **exactamente** estos ocho campos:

```
Entrada → Actividad → Rol → Técnica/Herramienta → Artefacto de salida → Compuerta/retorno → Cuello de botella → Métrica
```

Ejemplo:

```
Entrada:   Activos + arquitectura
Actividad: Integrar contenido
Rol:       Responsable de contenido
Salida:    Manifiesto versionado
Si falla:  Retorna al Responsable de contenido
Cuello:    El contenido bloquea el incremento
Métrica:   Horas de espera entre cadenas
```

Así, cuando Quinnie una todo, las cinco partes tendrán exactamente la misma lógica.

> Este formato ya está aplicado, bloque por bloque, en `MODELO_PROCESO.md` §4 — úsenlo como fuente y
> no lo vuelvan a derivar a mano.
