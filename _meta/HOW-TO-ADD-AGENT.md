# Cómo agregar un agente nuevo

Guía para crear agentes especializados dentro de un área existente o para una función nueva.

---

## Cuándo crear un agente nuevo

Creá un agente nuevo cuando:
- El agente genérico del área es demasiado amplio para una tarea específica y recurrente
- Necesitás un set de instrucciones, skills o permisos distintos al del agente base
- Hay una función que se repite y merece su propio "contrato"

Ejemplos:
- En Marketing: un agente `@copywriter` separado del `@marketing` genérico
- En Producto: un agente `@product-analyst` separado del `@producto` genérico
- En Finanzas: un agente `@reportes` separado del `@finanzas` genérico

---

## Paso 1: Crear el archivo del agente

Creá un `.md` en `.opencode/agents/[area]/[nombre-agente].md`.

### Estructura base

```yaml
---
description: |
  [Una o dos oraciones que describan QUÉ hace este agente y CUÁNDO usarlo.
  Esta descripción es lo que el orquestador lee para decidir a quién llamar.]
mode: subagent
temperature: 0.3
tools:
  write: true
  edit: true
  bash: false
permission:
  edit: ask
---

Sos el especialista en [función] del área de [área].

## Antes de empezar

[Lista ordenada de qué documentos leer antes de ejecutar cualquier tarea.]

1. Leé `knowledge/empresa.md` — Contexto general
2. Leé `areas/[area]/overview.md` — Contexto del área
3. [Docs específicos relevantes para este agente]

## Tu trabajo

[Descripción clara de qué puede hacer este agente. Sé específico.]

## Skills disponibles

[Si el agente usa skills, listarlas aquí:]
- Cargá `brand-voice` para tareas de contenido externo
- Cargá `campaign-context` para tareas de marketing

## Output

- Guardá outputs en `_inbox/YYYY-MM-DD-[agente]-descripcion.md`
- [Otras instrucciones de output específicas]

## Límites

- No modifiques archivos fuera de `_inbox/`
- [Límites específicos de este agente]
```

---

## Paso 2: Configurar los permisos correctos

| Herramienta | Cuándo habilitarla |
|-------------|-------------------|
| `write: true` | El agente crea archivos nuevos |
| `edit: true` | El agente modifica archivos existentes |
| `bash: true` | El agente necesita ejecutar comandos (solo si es necesario) |
| `permission.edit: ask` | Pedí confirmación antes de editar (recomendado) |
| `permission.edit: allow` | Edición libre (solo para agentes de alta confianza) |

### Temperaturas recomendadas

| Tipo de tarea | Temperature |
|--------------|-------------|
| Análisis, datos, precisión | 0.1 - 0.2 |
| Estrategia, estructura | 0.2 - 0.4 |
| Contenido, redacción | 0.4 - 0.6 |
| Brainstorming, creatividad | 0.6 - 0.8 |

---

## Paso 3: Vincular en OpenCode

```bash
VAULT="[ruta-al-vault]"
ln -sf "$VAULT/.opencode/agents/[area]/[nombre-agente].md" ~/.config/opencode/agents/[nombre-agente].md
```

---

## Paso 4: Registrar en AGENTS.md

Agregá el agente nuevo a la tabla de agentes en `AGENTS.md` y actualizá las reglas de enrutamiento si es necesario.

---

## Paso 5: Documentar en el README del área

Actualizá `.opencode/agents/[area]/README.md` con el nuevo agente.

---

## Buenas prácticas

- **La `description` del frontmatter es lo más importante.** El orquestador la usa para decidir a quién llamar. Tiene que ser precisa, incluir cuándo usarlo y cuándo NO.
- **Sé específico en los límites.** Un agente que sabe qué NO puede hacer es más confiable que uno sin límites.
- **Menos es más.** Un agente con 5 responsabilidades claras es mejor que uno con 20 vagas.
- **Los agentes leen docs, no inventan.** Siempre apuntá a documentación concreta en el vault.
