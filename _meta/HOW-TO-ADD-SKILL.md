# Cómo agregar una skill nueva

Las skills son módulos de conocimiento reutilizables que los agentes cargan cuando los necesitan. A diferencia de los agentes, las skills no ejecutan tareas: proveen contexto.

---

## Cuándo crear una skill nueva

Creá una skill cuando:
- Hay un set de documentos que múltiples agentes necesitan leer para la misma función
- Querés empaquetar un framework o metodología para que varios agentes lo usen
- El contexto es demasiado específico para estar en el agente base pero se repite entre tareas

Ejemplos:
- `brand-voice` — Tono y terminología de marca (usada por marketing, producto, rrhh)
- `competitive-analysis` — Marco competitivo (usada por marketing, producto, finanzas)
- `legal-frameworks` — Marcos regulatorios (usada por legal y finanzas)

---

## Paso 1: Crear la carpeta y el SKILL.md

```
.opencode/skills/[nombre-skill]/SKILL.md
```

El nombre de la carpeta define cómo se invoca la skill: `@agente cargá [nombre-skill]`.

### Estructura base de SKILL.md

```yaml
---
name: [nombre-skill]
description: >
  [Una o dos oraciones que describan QUÉ provee esta skill y CUÁNDO usarla.
  Esta descripción es lo que los agentes leen para decidir si la necesitan.]
---

# [Nombre de la skill]

## Instrucciones

Leé los siguientes archivos:

1. `[path/al/doc.md]` — [Para qué sirve]
2. `[path/al/otro-doc.md]` — [Para qué sirve]

## Qué encontrás en este contexto

[Descripción de qué información provee esta skill.]

## Cómo aplicar

[Instrucciones específicas de cómo usar esta información al ejecutar tareas.]

## Completar con información de tu empresa

[Instrucciones de qué documentos del vault hay que completar para que esta skill funcione.]
```

---

## Paso 2: Vincular en OpenCode

```bash
VAULT="[ruta-al-vault]"
ln -sf "$VAULT/.opencode/skills/[nombre-skill]" ~/.config/opencode/skills/[nombre-skill]
```

---

## Paso 3: Referenciar en los agentes que la usan

En el archivo del agente, agregá en la sección correspondiente:

```markdown
## Skills disponibles

- Cargá `[nombre-skill]` cuando necesites [para qué]
```

---

## Buenas prácticas

- **Una skill = un propósito.** No mezcles contexto de producto con contexto de audiencias en la misma skill.
- **Las skills apuntan a docs, no los reemplazan.** El SKILL.md es un índice con instrucciones, no el contenido en sí.
- **Mantené las skills actualizadas.** Si los docs que apunta una skill se mueven o renombran, actualizá el SKILL.md.
