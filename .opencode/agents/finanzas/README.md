# Agentes — Finanzas

## Agentes disponibles

- `finanzas.md` — Agente genérico del área de Finanzas

## Cómo agregar agentes especializados

Si el área de Finanzas necesita agentes más específicos, podés crearlos siguiendo la guía en `_meta/HOW-TO-ADD-AGENT.md`.

### Estructura básica de un agente especializado

```yaml
---
description: |
  [Descripción breve de qué hace este agente y cuándo usarlo.]
mode: subagent
temperature: 0.3
tools:
  write: true
  edit: true
  bash: false
permission:
  edit: ask
---

Sos el especialista en [tema específico] del área de Finanzas.

## Antes de empezar
[Qué documentos leer y en qué orden]

## Tu trabajo
[Descripción detallada de las tareas que puede hacer]

## Límites
[Qué NO puede hacer]
```
