# Contratos de agentes — Referencia

Resumen de todos los agentes disponibles en Spine Agents y cómo usarlos.

## Cómo invocar un agente

En OpenCode, mencioná al agente con `@` seguido del nombre:

```
@marketing Escribí un borrador de email para anunciar el nuevo producto
@curator Actualizá el overview de finanzas con los datos de la última reunión
@producto Redactá la especificación de la feature de notificaciones
```

---

## Agente universal

### @curator
**Qué hace:** Mantiene actualizada la base de conocimiento del vault. Detecta info desactualizada, propone cambios y los ejecuta con confirmación.
**Cuándo usarlo:** Después de reuniones, cuando haya cambios en estrategia, producto, equipo o datos.
**Qué NO hace:** No modifica templates ni configuración del sistema. Siempre pide confirmación antes de editar docs.

---

## Agentes por área

### @marketing
**Qué hace:** Tareas de marketing: contenido, campañas, copy, estrategia de comunicación, análisis.
**Cuándo usarlo:** Cualquier tarea del área de marketing.

### @operaciones
**Qué hace:** Documentación de procesos, análisis de flujos, SOPs, coordinación operativa.
**Cuándo usarlo:** Cualquier tarea del área de operaciones.

### @finanzas
**Qué hace:** Análisis financiero, reportes, proyecciones, control de costos, métricas económicas.
**Cuándo usarlo:** Cualquier tarea del área de finanzas.

### @producto
**Qué hace:** Documentación de features, análisis de métricas de uso, specs, roadmap, user stories.
**Cuándo usarlo:** Cualquier tarea del área de producto.

### @rrhh
**Qué hace:** Job descriptions, onboarding, documentación de cultura, procesos de selección.
**Cuándo usarlo:** Cualquier tarea del área de recursos humanos.

### @legal
**Qué hace:** Borradores de contratos, análisis de compliance, documentación regulatoria.
**Cuándo usarlo:** Cualquier tarea del área de legal.

---

## Reglas generales

- Todos los agentes respetan `knowledge/voz-tono.md` para comunicación externa
- Los outputs se guardan en `_inbox/` para revisión humana
- Solo `@curator` puede modificar docs del vault (con confirmación)
- Si un agente necesita info que no tiene, pregunta antes de inventar
- Para agregar agentes especializados, ver `_meta/HOW-TO-ADD-AGENT.md`
