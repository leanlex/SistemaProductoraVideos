## Paradigma de orientado a objetos
Es un modelo de programación que organiza el software en torno a objetos. Estos objetos representan entidades del mundo real y combina *Atributos* (datos o caracteristicas) y *Métodos* (comportamiento o funciones).
Este modelo de programación facilita el modelado de sistemas complejos a partir de ejemplos concretos de la realidad. Permite una buena organización del código, favoreciendo la reutilización, evitando duplicación. Promueve la colaboración y se adapta bien a proyectos que evolucionan.

---
## Fundamentos de POO
**Abstracción:** Consiste en simplificar la complejidad del mundo real modelando solo los aspectos esenciales relevantes para el sistema.

**Encapsulamiento:** Es el proceso de ocultar la implementación interna de un objeto, permitiendo el acceso solo mediante métodos controlados.

**Herencia:** Es un mecanismo que permite que un objeto herede propiedades y comportamientos de otro objeto. Esto fomenta la reutilización del código y la creación de jerarquías de clases.

**Polimorfismo:** Se refiere a la capacidad de los objetos de una misma jerarquía de clases para responder de manera diferente a un mismo mensaje.

---
## Requisitos iniciales del sistema

### Requisitos funcionales (RF)
- **RF1. Gestión de proyectos por etapas.** El sistema debe permitir crear proyectos y gestionarlos por etapas (grabación, edición, revisión, publicación) y que estas puedan **variar** por proyecto.
- **RF2. Responsable por etapa y asignación de tareas.** Cada etapa puede tener un **responsable distinto**; las tareas suelen asignarse a una persona (posible co-asignación futura).
- **RF3. Notificaciones automáticas.** Enviar avisos por **mail y WhatsApp** cuando se complete una etapa o se asigne una nueva tarea.
- **RF4. Registro centralizado de enlaces.** Guardar **links** a Drive/Vimeo u otras plataformas asociados al proyecto/etapas.
- **RF5. Vista de estado / tablero.** Mostrar un tablero para ver de un vistazo estados, tareas pendientes y “quién hace qué”.
- **RF6. Incidencias y entregas versionadas.** Registrar **observaciones/incidencias** por etapa y permitir **versionar** entregas (v1, v2…).

### Requisitos no funcionales (RNF)
- **RNF1. Usabilidad.** Interfaz **simple** (lista de proyectos, **filtros** y botones rápidos para cargar avances).
- **RNF2. Oportunidad de notificación.** Las alertas deben ayudar a que “todos se enteren **rápido**” (preferencia por WhatsApp además de mail).
- **RNF3. Flexibilidad del flujo.** Posibilidad de **agregar nuevas etapas** sin fricción (p. ej., animación, subtitulado).
- **RNF4. Trazabilidad.** Mantener **histórico** de incidencias y comentarios internos por etapa.
- **RNF5. Reportabilidad.** Estadísticas simples (mensuales), y también por **cliente/tipo/etapa** y tiempos promedio.
- **RNF6. Evolutividad.** Prever una futura extensión para que **clientes** consulten/ **aprueben** etapas (no en v1).


---
## Casos de uso

A continuación se documentan los actores y cinco casos de uso iniciales del sistema.

### Actores
- **Productora/Coordinadora**: crea proyectos, configura etapas, asigna responsables, consulta KPIs.
- **Editor/Operador**: ejecuta tareas por etapa, sube entregables/versiones, marca avances.
- **Asistente de Producción**: carga datos operativos, comentarios e incidencias, enlaces.
- **Sistema**: gestiona estados, notificaciones (mail/WhatsApp) y métricas/alertas.

---

### CU1 – Crear proyecto y configurar etapas
**Actor principal:** Productora/Coordinadora  
**Descripción:** Crea un proyecto con datos básicos, define etapas estándar (grabación, edición, revisión, publicación) y puede agregar extras (animación, subtitulado). Asigna responsables por etapa.

**Flujo principal:**
1. La Productora selecciona “Nuevo proyecto”.
2. Ingresa cliente, tipo de proyecto y fecha objetivo.
3. Elige plantilla de etapas y agrega/quita etapas extra.
4. Asigna responsable por cada etapa.
5. (Opcional) Agrega enlaces iniciales (Drive/Vimeo).
6. Guarda; el Sistema crea el backlog de etapas.

**Precondiciones:** Usuario con permiso de creación.  
**Postcondiciones:** Proyecto en **Planificado** con etapas y responsables definidos.

---

### CU2 – Avanzar etapa y notificar al siguiente responsable
**Actor principal:** Editor/Operador  
**Descripción:** El responsable marca su etapa como **Completada**; el Sistema activa la siguiente y notifica por mail/WhatsApp.

**Flujo principal:**
1. El Editor abre su etapa activa.
2. Adjunta entregables/versiones finales.
3. Marca la etapa como **Completada**.
4. El Sistema registra tiempos real vs. estimado y demora.
5. El Sistema pone la siguiente etapa en **Listo para iniciar**.
6. El Sistema notifica al siguiente responsable (mail/WhatsApp).

**Precondiciones:** Etapa activa y usuario responsable.  
**Postcondiciones:** Etapa actual **Completada**; siguiente **Listo para iniciar**; métricas y notificación realizadas.

---

### CU3 – Asignar o reasignar tareas dentro de una etapa (uno o varios responsables)
**Actor principal:** Productora/Coordinadora  
**Descripción:** Crea tareas dentro de una etapa, define prioridad y fechas, y asigna uno o varios responsables (p. ej., dos editores en paralelo).

**Flujo principal:**
1. La Productora abre el tablero del proyecto.
2. Crea una o más tareas en una etapa.
3. Define prioridad (alta/media/baja) y fecha estimada.
4. Asigna una o varias personas responsables.
5. Guarda; el Sistema notifica a los asignados.
6. Las tareas quedan visibles con filtros por responsable/estado.

**Precondiciones:** Proyecto y etapa existentes.  
**Postcondiciones:** Tareas creadas/asignadas con prioridad y fechas; notificaciones enviadas.

---

### CU4 – Registrar incidencias y comentarios internos por etapa
**Actor principal:** Cualquier miembro del equipo  
**Descripción:** Registra incidencias (bloqueante/mejora/consulta) y comentarios con evidencia (archivos/enlaces), dejando histórico y trazabilidad.

**Flujo principal:**
1. El usuario abre “Incidencias/Comentarios” de la etapa.
2. Redacta el comentario o describe la incidencia.
3. (Opcional) Adjunta evidencia o enlace.
4. Etiqueta el tipo (bloqueante/mejora/consulta).
5. Guarda el registro.
6. El Sistema notifica a la persona responsable de la etapa.

**Precondiciones:** Acceso al proyecto/etapa.  
**Postcondiciones:** Incidencia/comentario registrado y notificado; visible en histórico.

---

### CU5 – Consultar tablero y estadísticas operativas
**Actor principal:** Productora/Coordinadora  
**Descripción:** Visualiza proyectos activos, tareas pendientes, tiempos reales vs. estimados y totales mensuales filtrables por cliente y tipo de proyecto; permite exportar/compartir reportes.

**Flujo principal:**
1. La Productora abre el tablero general.
2. Aplica filtros (cliente, tipo, responsable, estado).
3. Revisa KPIs: proyectos activos, % avance, tareas vencidas.
4. Abre reportes con totales del mes y tiempos por etapa.
5. Exporta o comparte reporte (PDF/CSV o enlace interno).
6. (Opcional) Programa envío automático mensual.

**Precondiciones:** Existencia de datos de proyectos/etapas.  
**Postcondiciones:** Información de seguimiento disponible; reportes generados/compartidos.

**DIAGRAMAS DE CLASES:**

[Ver código PlantUML](../diagramas/01-diagrama-clases/01-boceto-inicial.puml)


![01-boceto-inicial.png](../diagramas/01-diagrama-clases/01-boceto-inicial.png)

**DIAGRAMAS DE CASOS DE USO:**

[Ver código PlantUML](../diagramas/02-diagrama-casos-uso/01-boceto-inicial.puml)


![01-boceto-inicial.png](../diagramas/02-diagrama-casos-uso/01-boceto-inicial.png)

## Enlace a la consigna
[📄 Consigna – Actividad Obligatoria N.º 1](./ACTIVIDAD_OBLIGATORIA_N_1.pdf)