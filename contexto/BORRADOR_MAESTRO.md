# BORRADOR MAESTRO — Entregable en construcción

**Estado:** estructura alineada al Reto #1; §III.B DevOps en borrador sanitizado.  
**Dominio:** Realidad aumentada (Equipo 2).  
**Outline:** `PLANTILLA_PAPER.md` · **Fuentes:** `FUENTES.md` · **Gestión:** `GESTION_PROYECTO.md`  
**Citas:** `[@Clave]` hasta el ensamblado.

---

## Título

*[pendiente — AR + metodología / espina de pescado]*

## Autores

*[pendiente — orden por confirmar]*  
Universidad EAFIT — Procesos Modernos de Desarrollo de Software  
Quinnie; Jose Manuel Carvajal; Jonathan Sandoval; Lina Ballesteros; Alejandro Ríos

## Abstract (English)

*[pending — no references]*

## Índice de Términos

*[pendiente]*

---

## I. Introducción

*[pendiente]*

---

## II. Dominio: realidad aumentada — estado actual

*Responsable: Quinnie. Checklist: qué es; estado; cómo se abordan proyectos; metodologías; principios diseño/arquitectura; ciclo de vida.*

*[pendiente]*

---

## III. Enfoques seleccionados y razón de elección

### A. GenIA
*Responsable: Jose Manuel Carvajal.*  
*[pendiente]*

### B. DevOps
*Responsable: Jonathan Sandoval.*  
*Nota: el detalle del caso industrial (empleador) vive solo en `contexto/privado/III_B_DEVOPS_GENIUS.md` (gitignored). Aquí, versión sanitizada para el repo compartido.*

DevOps es un enfoque de ingeniería de software que busca acortar el tiempo entre un cambio en el sistema y su operación en producción, manteniendo calidad, mediante colaboración entre desarrollo y operaciones, automatización y entrega continua [@Bass2015], [@Jabbari2016]. En la ingeniería de software, articula prácticas (CI/CD, infraestructura como código, monitoreo) que condicionan arquitectura y operación [@Bass2015], [@Jabbari2016].

Como referente de ejecución, se toma experiencia industrial en **augmentación gráfica en tiempo real sobre video deportivo broadcast** (superposición de gráficos a partir de tracking y estado del juego): pipelines CI/CD con lint, build, test, release y deploy; contenedores e imágenes en registro cloud; promoción mediante *release candidates* y ambientes de staging/producción; QA con roles de operaciones, ingeniería y contenido; y un **pipeline de contenido** que genera instrucciones de augmentación (artefactos tipados + manifiesto de plugins) además del pipeline de código. [SIN FUENTE PÚBLICA — respaldo en notas privadas del autor; no citar paths internos en la entrega pública sin autorización]

Para el dominio AR del curso se declara el matiz: el referente es *realtime augmentation* sobre video broadcast, no necesariamente AR móvil con *headset*; aun así, comparte con AR la necesidad de entregar software y contenido gráfico de forma repetible. La literatura en AR colaborativa basada en microservicios refuerza la orquestación de componentes heterogéneos [@Vaquero2020]. Se propone transferir CI/CD, contenedores, promoción por ambientes, QA multi-rol y el dual pipeline **código + instrucciones/contenido** a la metodología AR.

Técnicas/herramientas típicas del enfoque: CI/CD, contenedores, registros de imágenes, IaC, secretos, observabilidad y pruebas automatizadas (incl. escenarios costosos de simulación). Lenguajes de modelado/especificación: YAML de pipelines, diagramas de flujo de aplicación, IaC y esquemas JSON de artefactos de contenido. Métodos: entrega continua con RC, commits convencionales, QA operacional previo a producción.

Se elige DevOps porque el dominio AR exige iterar con seguridad operativa sobre software y contenido; el referente industrial de augmentación en tiempo real aporta un modelo concreto transferible al ciclo de vida AR del equipo.

### C. Event Driven Architecture
*Responsable: Lina Ballesteros.*  
*[pendiente]*

### D. Progressive Delivery
*Responsable: Alejandro Ríos.*  
*[pendiente]*

---

## IV. Espina de pescado y propuesta metodológica

*Base: [@Ceret2013]. Definir roles, formatos, ciclos y justificación; valor diferencial.*

### A. Ciclo
*[pendiente]*

### B. Colaboración
*[pendiente]*

### C. Artefactos
*[pendiente]*

### D. Uso recomendado
*[pendiente]*

### E. Madurez
*[pendiente]*

### F. Flexibilidad
*[pendiente]*

### G. Valor diferencial frente a metodologías actuales
*[pendiente]*

---

## V. Conclusión

*[pendiente]*

---

## Referencias

- [@Ceret2013]
- *(añadir fuentes AR y de cada enfoque tras verificación)*
