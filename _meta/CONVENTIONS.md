# Convenciones — Spine Agents

Reglas de formato y estructura que aplican a todo el vault.

---

## Nombres de archivo

- **Documentos de área:** `nombre-descriptivo.md` (kebab-case, minúsculas)
- **Outputs de agentes en `_inbox/`:** `YYYY-MM-DD-area-descripcion.md`
- **Notas de reuniones:** `YYYY-MM-DD-tipo-descripcion.md`
- **Templates:** `nombre-del-template.md`

## Formato de fechas

| Contexto | Formato |
|----------|---------|
| Nombres de archivo | `YYYY-MM-DD` |
| Contenido visible | `DD/MM/YYYY` |
| Frontmatter YAML | `YYYY-MM-DD` |

## Frontmatter YAML

Todo documento del vault debe incluir frontmatter con al menos:

```yaml
---
title: "Título del documento"
description: "Qué contiene y cuándo leerlo. Esta descripción la leen los agentes."
tags:
  - [área]
  - [tag adicional]
---
```

La `description` es especialmente importante: es lo que los agentes leen para decidir si un documento es relevante para su tarea. Hacela descriptiva y específica.

## Wikilinks internos

Usá wikilinks de Obsidian para conectar documentos relacionados:

```markdown
Ver [[knowledge/empresa]] para el contexto general.
```

Incluí siempre un bloque de "Documentos relacionados" al final de cada doc.

## Tags

Usá tags de Obsidian para categorizar el contenido:

| Tag | Cuándo usarlo |
|-----|---------------|
| `#[área]` | Todo documento de un área específica |
| `#MOC` | Mapas de contenido (índices) |
| `#agente-output` | Outputs generados por agentes |
| `#pendiente` | Documentos que necesitan ser completados |
| `#template` | Templates del vault |

## Estructura de carpetas

```
areas/[area]/     ← Documentación específica del área
knowledge/        ← Conocimiento compartido entre todas las áreas
templates/        ← Plantillas reutilizables (no tocar sin consenso del equipo)
_inbox/           ← Solo outputs de agentes. Revisar y mover periódicamente.
_meta/            ← Docs del sistema. No tocar sin actualizar SETUP y CONVENTIONS.
opencode-config/  ← Configuración de agentes. Solo editar con conocimiento del sistema.
```

## Idioma

El idioma por defecto es el que use la empresa internamente. Definirlo en `knowledge/empresa.md`.

## `_inbox/` — Reglas

- Los agentes escriben aquí. Los humanos revisan y mueven.
- Los archivos en `_inbox/` son borradores, no documentación definitiva.
- Limpiar periódicamente: mover lo aprobado, eliminar lo descartado.
- Solo `@curator` puede mover archivos de `_inbox/` al vault permanente.
