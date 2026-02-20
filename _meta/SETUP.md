# Setup — Spine Agents

## Requisitos

- [Obsidian](https://obsidian.md) instalado
- [OpenCode](https://opencode.ai) instalado y configurado con un provider

---

## Cómo funciona (leer antes de empezar)

Spine Agents usa **configuración local de OpenCode**. La carpeta `.opencode/` dentro del vault contiene los agentes y skills del proyecto. OpenCode la detecta automáticamente cuando lo abrís desde esa carpeta.

Esto significa que:
- Cada vault tiene sus propios agentes y skills, completamente aislados
- No se toca la configuración global de OpenCode (`~/.config/opencode/`)
- Podés tener múltiples instancias de Spine Agents (una por empresa) sin que se mezclen

---

## Paso 1: Ubicar la carpeta

Descomprimí el ZIP y mové la carpeta `spine-agents/` al lugar donde querés que viva de forma permanente. Por ejemplo:

```
~/Documentos/Obsidian/spine-agents-miempresa
```

> Si es una instancia para una empresa específica, renombrá la carpeta con el nombre de la empresa.

## Paso 2: Abrir en Obsidian

Obsidian → "Open folder as vault" → seleccioná la carpeta del vault.

## Paso 3: Completar la base de conocimiento

Antes de usar los agentes, completá los archivos con la información de tu empresa:

**Obligatorios:**
- `knowledge/empresa.md`
- `knowledge/equipo.md`
- `knowledge/voz-tono.md`
- `knowledge/glosario.md`

**Por área (completar las que vayas a usar):**
- `areas/[area]/overview.md`
- `areas/[area]/objetivos.md`
- `areas/[area]/estrategia.md`

## Paso 4: Actualizar las rutas en los agentes

Abrí cada archivo en `.opencode/agents/` y reemplazá `[PATH_AL_VAULT]` con la ruta real a tu vault. Por ejemplo:

```
~/Documentos/Obsidian/spine-agents-miempresa
```

## Paso 5: Usar OpenCode

```bash
cd ~/Documentos/Obsidian/spine-agents-miempresa
opencode
```

OpenCode detecta `.opencode/` automáticamente y carga solo los agentes y skills de este vault.

---

## Verificar que funciona

Una vez dentro de OpenCode, probá:

```
@curator ¿Qué documentos faltan completar en el vault?
```

Si el agente responde con contexto del vault, todo funciona.

---

## Agregar instancias para otras empresas

Para crear una instancia para otra empresa:

1. Copiá la carpeta `spine-agents/` y renombrala: `spine-agents-otraempresa/`
2. Completá los archivos con la info de esa empresa
3. Para usarla: `cd spine-agents-otraempresa && opencode`

Cada instancia es completamente independiente.

---

## Agregar agentes o skills

- Para agregar un agente nuevo: ver `_meta/HOW-TO-ADD-AGENT.md`
- Para agregar una skill nueva: ver `_meta/HOW-TO-ADD-SKILL.md`

## Plugins de Obsidian recomendados

- **Obsidian Git** — Auto-commit y sync con GitHub
- **Templater** — Para usar los templates del vault
- **Dataview** — Para consultas dinámicas sobre el contenido
