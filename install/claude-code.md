# Install — Claude Code

## Quick install

```bash
# 1. Copy cognitive protocol to Claude's config
cp cognitive-protocol.md ~/.claude/second-order-thinking.md

# 2. Add reference in CLAUDE.md
echo '@~/.claude/second-order-thinking.md' >> ~/.claude/CLAUDE.md
```

## What gets loaded where

| File | Destination | Purpose |
|---|---|---|
| `cognitive-protocol.md` | `~/.claude/second-order-thinking.md` | Always-on core rules (~30 lines) |
| `SKILL.md` | `~/.claude/skills/second-order-thinking/SKILL.md` | Full reference (loaded on demand) |
| `anti-patterns.md` | `~/.claude/skills/second-order-thinking/anti-patterns.md` | Detailed anti-pattern guide |
| `examples.md` | `~/.claude/skills/second-order-thinking/examples.md` | Before/after reference |

## Full install (with skill files)

```bash
# 1. Core rules
cp cognitive-protocol.md ~/.claude/second-order-thinking.md

# 2. Skill files
mkdir -p ~/.claude/skills/second-order-thinking
cp SKILL.md ~/.claude/skills/second-order-thinking/
cp anti-patterns.md ~/.claude/skills/second-order-thinking/
cp examples.md ~/.claude/skills/second-order-thinking/

# 3. Register in CLAUDE.md
echo '@~/.claude/second-order-thinking.md' >> ~/.claude/CLAUDE.md
```

## Verify

Ask Claude Code: "What are the second-order thinking rules you're following?" It should list the four sections from `cognitive-protocol.md`: trace consequences forward, run the counterfactual, detect nonlinear transitions, anti-pattern self-check.

## Stacking with other cognitive bases

If First Principles (`~/.claude/first-principles.md`) or Tacit Knowledge (`~/.claude/tacit-knowledge.md`) are already referenced in `CLAUDE.md`, no changes needed. All protocols load independently. First Principles audits reasoning inputs; Second-Order Thinking traces reasoning consequences; Tacit Knowledge governs output quality. No conflicts.

## Uninstall

```bash
rm ~/.claude/second-order-thinking.md
rm -rf ~/.claude/skills/second-order-thinking
# Remove the @~/.claude/second-order-thinking.md line from ~/.claude/CLAUDE.md
```
