# Spine Agents

Sistema operativo de equipos basado en agentes de IA y documentación viva.

## Qué es esto

Spine Agents es una plantilla base para construir el sistema nervioso operativo de cualquier empresa. Combina un vault de Obsidian (base de conocimiento) con agentes de IA que operan sobre esa base mediante [OpenCode](https://opencode.ai).

Cada área de la empresa tiene su propia carpeta con documentación estructurada. Los agentes leen esa documentación para ejecutar tareas con contexto real de la empresa.

## Estructura

```
spine-agents/
├── areas/                ← Una carpeta por área de la empresa
│   ├── marketing/        ← Documentación del área de marketing
│   ├── operaciones/      ← Documentación del área de operaciones
│   ├── finanzas/         ← Documentación del área de finanzas
│   ├── producto/         ← Documentación del área de producto
│   ├── rrhh/             ← Documentación del área de RRHH
│   └── legal/            ← Documentación del área de legal
├── knowledge/            ← Base de conocimiento compartida entre áreas
├── templates/            ← Plantillas reutilizables
├── meetings/             ← Notas de reuniones
├── _inbox/               ← Outputs de agentes para revisión humana
├── _meta/                ← Docs del sistema
└── opencode-config/      ← Configuración de agentes y skills para OpenCode
    ├── agents/           ← Un agente por área + curator universal
    └── skills/           ← Skills reutilizables
```

## Cómo usar esta plantilla

1. Cloná o copiá este repositorio
2. Completá los archivos de `knowledge/` con la información de tu empresa
3. Completá los archivos de cada área en `areas/` con la información de cada equipo
4. Configurá los agentes en `opencode-config/agents/` para tu contexto
5. Seguí las instrucciones de setup en `_meta/SETUP.md`

## Convenciones

- **Formato de fechas:** YYYY-MM-DD en nombres de archivo, DD/MM/YYYY en contenido
- **Links internos:** Usar wikilinks de Obsidian `[[archivo]]` para conectar docs
- **Tags:** Usar tags de Obsidian para categorizar contenido
- **_inbox/:** Los agentes escriben aquí. Los humanos revisan y mueven.
- **Idioma:** Adaptar al idioma de tu empresa

## Setup rápido

Ver [[_meta/SETUP]] para instrucciones detalladas de instalación.

## Instancias de Spine Agents

Una vez configurada, esta plantilla genera una instancia específica de tu empresa. Por ejemplo:
- `spine-agents` → plantilla base (este repo)
- `spine-agents-[empresa]` → instancia configurada para tu empresa
