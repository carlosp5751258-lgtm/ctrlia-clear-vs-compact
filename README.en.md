# /clear vs /compact in Claude Code, and idle compaction

[Leer en español](README.md)

The files from the Ctrl+IA recipe about context in Claude Code: compaction instructions for your `CLAUDE.md`, settings to turn off or tune idle compaction, the prompt to save the state to `NOTES.md` and a command cheat sheet.

The full recipe (when to `/clear` and when to `/compact`, what survives a compaction, `/rewind`, `/autocompact` and idle compaction):

- English: https://ctrlia.dev/en/recetas/clear-vs-compact.html
- Español: https://ctrlia.dev/recetas/clear-vs-compact.html

## What's included

| File | What for |
| --- | --- |
| `compact-instructions.en.md` | "# Compact instructions" section for your `CLAUDE.md` (Spanish: `compact-instructions.md`) |
| `settings-sin-compactacion-en-reposo.json` | `"idleCompaction": false` for `~/.claude/settings.json` (2.1.290 or later) |
| `settings-umbral-150k.json` | Keeps idle compaction on, but from 150 k tokens |
| `prompt-notes.en.txt` | Prompt so Claude saves the state to `NOTES.md` before compacting (Spanish: `prompt-notas.txt`) |
| `chuleta.en.md` | Commands and rules on one page (Spanish: `chuleta.md`) |

## How to use it

```bash
git clone https://github.com/carlosp5751258-lgtm/ctrlia-clear-vs-compact.git
cd ctrlia-clear-vs-compact
cat compact-instructions.en.md >> /path/to/your-project/CLAUDE.md
```

For the settings, copy the key from the `.json` you choose into your `~/.claude/settings.json` (merge it with what you already have; don't overwrite it). Use only one of the two: either turn it off or change its threshold. You can also turn it off from the session with `/config` > Idle compaction (2.1.302 or later).

## What was tested

`python3 -m json.tool` on both settings files. With Claude Code **2.1.316** on Linux, `claude -p "/context"` returned the table by category; `/compact` with `-p` on an empty session answers "Not enough messages to compact". Idle compaction has not been tested yet (it needs more than an hour of idle session): what the recipe says comes from the official documentation and the CHANGELOG.

## License

MIT. See [LICENSE](LICENSE).

---
Part of **[Ctrl+IA](https://ctrlia.dev/)**: Claude Code like a pro, in Spanish. Made by Carlos P.
