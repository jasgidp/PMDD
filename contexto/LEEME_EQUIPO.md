# LEEME_EQUIPO.md — Cómo usar este repo

**Curso:** Universidad EAFIT — Procesos Modernos de Desarrollo de Software  
**Reto #1:** Dominio, Enfoque y Espina de Pescado  
**Equipo 2 — Dominio:** Realidad aumentada

## Qué es esto

La carpeta `contexto/` es la **única fuente de verdad** del trabajo. Lo que no esté escrito ahí no cuenta como acordado.

## Resumen del proyecto

Construir una **metodología de software** para AR, con cuatro enfoques (GenIA, DevOps, Event Driven Architecture, Human-Centered Design), anclada en la espina/taxonomía Céret et al. (Ciclo, Colaboración, Artefactos, Uso recomendado, Madurez, Flexibilidad).  
Abstract del paper: **inglés**. Cuerpo: **español**. Trabajo en Markdown → IEEE al final.

| Persona | Rol |
|---------|-----|
| Quinnie | Dominio AR |
| Jose Manuel Carvajal | GenIA |
| Jonathan Sandoval | DevOps (detalle industrial solo en `privado/`) |
| Lina Ballesteros | Event Driven Architecture |
| Alejandro Ríos | Human-Centered Design (HCD) |

## Qué entregar

| Entregable | Peso | Qué es |
|------------|------|--------|
| Socialización (PPT) | 40% | Dominio, enfoques + por qué, espina, valor diferencial |
| Paper IEEE + PPT corregida | 60% | Lo mismo, refinado |

## Estructura del paper (aprobada)

Ver detalle en `PLANTILLA_PAPER.md`. Resumen:

1. Introducción  
2. Dominio AR — **Quinnie**  
3. Enfoques (los 4): GenIA, DevOps, EDA, HCD  
4. Espina de pescado + valor diferencial — **equipo**  
5. Conclusión + Referencias  

## Archivos (organización acotada)

También: [`README.md`](../README.md) (raíz del repo) y [`README.md`](README.md) (esta carpeta).

| Archivo | Para qué |
|---------|----------|
| `LEEME_EQUIPO.md` | Este mapa + reglas del equipo |
| `REQUISITOS.md` | Enunciado literal + condiciones + rúbrica + ficha |
| `PLANTILLA_PAPER.md` | Outline IEEE aprobado |
| `BORRADOR_MAESTRO.md` | Paper en construcción |
| `FUENTES.md` | Bibliografía viva (pública) |
| `GESTION_PROYECTO.md` | Estado + decisiones + glosario + bitácora |
| `PRESENTACION.md` | PPT socialización + PPT corregida |
| `privado/` | **Solo local (gitignored):** detalle industrial — no subir |

**Ya no existen** (contenido fusionado): `00_`–`09_*.md`, `FICHA_DE_REQUISITOS.md`, `PPT_SOCIALIZACION.md`, `PPT_CORREGIDA.md`.

## Protocolo permanente (cada vez que llegue texto o un cambio)

**Sí: cada cambio se refleja en contexto.** Flujo fijo:

1. **Clasificar** qué es (requisito, fuente, texto de sección, decisión…).  
2. **Repartir** al archivo que toca:  
   - requisito/rúbrica/fecha → `REQUISITOS.md`  
   - outline → `PLANTILLA_PAPER.md`  
   - prosa del paper → `BORRADOR_MAESTRO.md`  
   - cita → `FUENTES.md` (o `privado/` si es industrial)  
   - estado/decisión/término → `GESTION_PROYECTO.md`  
   - diapositivas → `PRESENTACION.md`  
3. **Actualizar bitácora** (sección Bitácora en `GESTION_PROYECTO.md`).  
4. **Actualizar estado** de la sección en `GESTION_PROYECTO.md`.  
5. Reportar en el chat: archivos tocados, contradicciones, [SIN FUENTE], huecos.

No reescribir texto de un compañero sin pedirlo.  
Citas provisionales: `[@AutorAño]`. Fuentes reales y verificables.

## Cómo aportar texto

1. Escribe tu sección.  
2. Pásala al chat / al repo para integrarla en `BORRADOR_MAESTRO.md`.  
3. Revisa el checklist de tu parte en `REQUISITOS.md` (rúbrica).

## Pendiente de decidir

- Orden de autores  
- Nombre de la metodología (cuando armemos la espina)  
- En la entrega final: ¿versión sanitizada o detalle de `privado/` solo local?
