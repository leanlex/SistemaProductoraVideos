# Anexos – Actividad Obligatoria 1 (AO1)

> Este documento centraliza **fuentes**, **evidencias** y **trazabilidad** (RF ↔ CU ↔ Clases), además de decisiones y pendientes de la iteración.

## 1. Material de origen (inputs)
- 📧 **Mail de la productora:** [01 - Mail de la productora.pdf](./archivos-adjuntos-para-analizar/01%20-%20Mail%20de%20la%20productora.pdf)
- 🗣️ **Transcripción de reunión:** [02 - Transcripción Gemini GMeet - Reunión interna – Área de Producción & Desarrollo – Fecha 14/03/2025](./archivos-adjuntos-para-analizar/02%20-%20Transcripción%20Gemini%20GMeet%20-%20Reunión%20interna%20–%20Área%20de%20Producción%20%26%20Desarrollo%E2%80%A8Fecha_%2014_03_2025.pdf)

- 📝 **Notas/Fotos de pizarrón:** 
    - 📷 [Foto de pizarrón #1 – “Mapa inicial”](./archivos-adjuntos-para-analizar/04%20-%20Foto%20de%20pizarrón%20%231%20–%20“Mapa%20inicial”.png)
    - 📷 [Foto de pizarrón #2 – “Alarmas y métricas”](./archivos-adjuntos-para-analizar/05%20-%20Foto%20de%20pizarrón%20%232%20–%20“Alarmas%20y%20métricas”.png)
    - 📷 [Foto de pizarrón #3 – “Flujo y UX”](./archivos-adjuntos-para-analizar/06%20-%20Foto%20de%20pizarrón%20%233%20–%20“Flujo%20y%20UX”.png)
    - 📷 [Foto de pizarrón #4 – “Ideas sueltas y preguntas”](./archivos-adjuntos-para-analizar/07%20-%20Foto%20de%20pizarrón%20%234%20–%20“Ideas%20sueltas%20y%20preguntas”.png)
      📷 [Foto de pizarrón #5 – “Roles y permisos (borrador)”](./archivos-adjuntos-para-analizar/08%20-%20Foto%20de%20pizarrón%20%235%20–%20“Roles%20y%20permisos%20%28borrador%29”.png)

- 🔊 **Audios** 
  - 🔊 [Audio de Whatsapp – Laura (09)](./archivos-adjuntos-para-analizar/09%20-%20Audio%20de%20Whatsapp%20-%20Laura.mp3)
  - 🔊 [Audio de Whatsapp – Laura (10)](./archivos-adjuntos-para-analizar/10%20-%20Audio%20de%20Whatsapp%20-%20Laura.mp3)

## Enlace a la consigna
[📄 Consigna – Actividad Obligatoria N.º 1](./ACTIVIDAD_OBLIGATORIA_N_1.pdf)
---

## 2. Documentación elaborada
- 📄 **Introducción (POO, RF/RNF, Casos de uso):** [anexos/introduccion.md](anexos/introduccion.md)

- 🧩 **Diagrama de clases (PlantUML + PNG):**  
  - `.puml`: [diagramas/01-diagrama-clases/01-boceto-inicial.puml](diagramas/01-diagrama-clases/01-boceto-inicial.puml)  
  - `.png`: [diagramas/01-diagrama-clases/01-boceto-inicial.png](diagramas/01-diagrama-clases/01-boceto-inicial.png)

- 🎬 **Casos de uso (PUML/PNG):**  
  - [diagramas/02-diagrama-casos-uso/01-boceto-inicial.puml](diagramas/02-diagrama-casos-uso/01-boceto-inicial.puml)  
  - [diagramas/02-diagrama-casos-uso/01-boceto-inicial.png](diagramas/02-diagrama-casos-uso/01-boceto-inicial.png)


---

## 3. Matriz de trazabilidad (RF ↔ CU ↔ Clases)
| RF  | Descripción breve                              | CU vinculados         | Clases/Entidades                        |
|-----|--------------------------------------------------|---------------------|-----------------------------------------|
| RF1 | Gestión de proyectos por etapas                | CU-01, CU-03 , CU-05  | Proyecto, Etapa, Usuario                |
| RF2 | Responsable por etapa y asignación de tareas   | CU-01, CU-03          | Etapa, Usuario, Tarea                   |
| RF3 | Notificaciones automáticas                     | CU-02, CU-03, CU-04   | Notificacion, Etapa, Usuario            |
| RF4 | Registro centralizado de enlaces               | CU-01, CU-04          | Enlace, Proyecto, Etapa                 |
| RF5 | Vista de estado / tablero                      | CU-03, CU-05          | Proyecto, Tarea, Etapa                  |
| RF6 | Incidencias y entregas versionadas             | CU-02, CU-04          | Incidencia, Entrega (nroVersion), Etapa |


---

## 4. Decisiones y supuestos (v1)
- **Alcance v1:** uso **interno** (sin portal del cliente).
- **Flujo flexible:** etapas configurables por proyecto.
- **Notificaciones:** email y WhatsApp (prioridad a WhatsApp).
- **Versionado de entregas:** `Entrega.version` por etapa/proyecto.

---

## 5. Riesgos y pendientes
- Aprobación por cliente (**post-AO1**).
- Métricas/BI ampliadas (**post-AO1**).
- Integraciones externas (APIs) sujetas a disponibilidad.

---

## 6. Enlaces útiles
- 📄 **Consigna:** `anexos/ACTIVIDAD_OBLIGATORIA_N_1.pdf`
- 🔁 **PRs relevantes (ejemplos de tu repo):** #12 (Docs/Coord), #13 (Clases), #14 (Analista)
- 🚀 **PR de Release:** *(agregar link cuando la abras)* `release/actividad-obligatoria-1 → main`
- 🏷️ **Tag/Release:** *(si creás v0.1, enlazar aquí)*

