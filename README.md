# /clear vs /compact en Claude Code y la compactación en reposo

[Read in English](README.en.md)

Los archivos de la receta de Ctrl+IA sobre el contexto en Claude Code: instrucciones de compactación para tu `CLAUDE.md`, ajustes para apagar o ajustar la compactación en reposo (idle compaction), el prompt para guardar el estado en `NOTAS.md` y una chuleta de comandos.

La receta completa (cuándo `/clear` y cuándo `/compact`, qué sobrevive a una compactación, `/rewind`, `/autocompact` y la compactación en reposo):

- Español: https://ctrlia.dev/recetas/clear-vs-compact.html
- English: https://ctrlia.dev/en/recetas/clear-vs-compact.html

## Qué incluye

| Archivo | Para qué |
| --- | --- |
| `compact-instructions.md` | Sección «# Compact instructions» para tu `CLAUDE.md` (en inglés: `compact-instructions.en.md`) |
| `settings-sin-compactacion-en-reposo.json` | `"idleCompaction": false` para `~/.claude/settings.json` (2.1.290 o posterior) |
| `settings-umbral-150k.json` | Deja la compactación en reposo activada, pero desde 150 k tokens |
| `prompt-notas.txt` | Prompt para que Claude guarde el estado en `NOTAS.md` antes de compactar (en inglés: `prompt-notes.en.txt`) |
| `chuleta.md` | Comandos y reglas en una página (en inglés: `chuleta.en.md`) |

## Cómo usarlo

```bash
git clone https://github.com/carlosp5751258-lgtm/ctrlia-clear-vs-compact.git
cd ctrlia-clear-vs-compact
cat compact-instructions.md >> /ruta/a/tu-proyecto/CLAUDE.md
```

Para los ajustes, copia la clave del `.json` que elijas dentro de tu `~/.claude/settings.json` (júntala con lo que ya tengas; no lo sobrescribas). Usa solo uno de los dos: o la apagas o le cambias el umbral. También puedes apagarla desde la sesión con `/config` > Idle compaction (2.1.302 o posterior).

## Qué se probó

`python3 -m json.tool` sobre los dos ajustes. Con Claude Code **2.1.316** en Linux, `claude -p "/context"` devolvió la tabla por categorías; `/compact` con `-p` en una sesión vacía responde «Not enough messages to compact». La compactación en reposo no se ha probado todavía (necesita más de una hora de sesión parada): lo que dice la receta sale de la documentación oficial y del CHANGELOG.

## Licencia

MIT. Ver [LICENSE](LICENSE).

---
Parte de **[Ctrl+IA](https://ctrlia.dev/)**: programa con Claude Code como un pro, en español. Hecho por Carlos P.
