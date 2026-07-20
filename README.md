# rlangan-skills

Bobby Langan's personal Claude Code plugin library. One marketplace, one plugin per skill — install only what you want.

## Install the marketplace

```bash
claude plugin marketplace add BobbyLangan/rlangan-skills
```

Then install individual skills:

```bash
claude plugin install <skill-name>@rlangan-skills
```

## Skills

| Skill | What it does |
|---|---|
| [i-have-adhd](./plugins/i-have-adhd/README.md) | Shapes output for an ADHD reader: action-first, numbered steps, no tangents, no preamble. |

```bash
claude plugin install i-have-adhd@rlangan-skills
```

Then type `/i-have-adhd`. See [plugins/i-have-adhd/README.md](./plugins/i-have-adhd/README.md) for details.

## Adding a new skill

1. Create `plugins/<name>/.claude-plugin/plugin.json`:
   ```json
   {
     "name": "<name>",
     "description": "One-line description shown in the plugin list."
   }
   ```
2. Add `plugins/<name>/skills/<name>/SKILL.md` with the skill's frontmatter (`name`, `description`) and instructions.
3. Register it in [.claude-plugin/marketplace.json](./.claude-plugin/marketplace.json):
   ```json
   {
     "name": "<name>",
     "description": "...",
     "source": "./plugins/<name>",
     "category": "..."
   }
   ```
4. Add a row to the Skills table above.
5. `claude plugin marketplace update rlangan-skills` (or re-add) to pick up the change locally.

## Manage

```bash
claude plugin list                              # see installed skills
claude plugin disable <skill-name>              # turn one off
claude plugin uninstall <skill-name>             # remove one
claude plugin marketplace update rlangan-skills   # pull latest changes
```

## License

MIT — see [LICENSE](./LICENSE). Individual skills may carry their own license/credits in their plugin folder.
</content>
