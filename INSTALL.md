# Install

A Claude Code plugin marketplace. Each skill installs independently.

## Add the marketplace

```bash
claude plugin marketplace add BobbyLangan/claude-skills
```

No local clone needed — Claude Code fetches the repo and keeps it updated.

## Install a skill

```bash
claude plugin install <skill-name>@claude-skills
```

For example:

```bash
claude plugin install i-have-adhd@claude-skills
```

See each plugin's own README under `plugins/<name>/README.md` for how to invoke it.

## Verify

```bash
claude plugin list
```

Look for `<skill-name>  (enabled)`.

## Update

```bash
claude plugin marketplace update claude-skills
```

Next Claude Code session picks up changes.

## Disable / uninstall

```bash
claude plugin disable <skill-name>
claude plugin uninstall <skill-name>
```

To remove the whole marketplace:

```bash
claude plugin marketplace remove claude-skills
```

## Troubleshooting

**Skill not in autocomplete.** Restart Claude Code. The plugin index is read at startup.

**`claude plugin marketplace add` fails.** Use the `owner/repo` form: `claude plugin marketplace add BobbyLangan/claude-skills`. If pointing at a local path instead, it must be the repo root (the directory containing `.claude-plugin/marketplace.json`), not `.claude-plugin/` itself.

**Skill activates but behavior doesn't change.** Open a new session — old context may carry over from before install.

**Want to tweak a skill.** Edit `plugins/<name>/skills/<name>/SKILL.md` directly, then `claude plugin marketplace update claude-skills`.
</content>
