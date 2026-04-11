# Install — Claude Code

## Quick install

```bash
# 1. Inject core rules into CLAUDE.md (direct content injection — works on all versions)
cat cognitive-protocol.md >> ~/.claude/CLAUDE.md
```

## What gets loaded where

| File | Destination | Purpose |
|---|---|---|
| `cognitive-protocol.md` | `~/.claude/CLAUDE.md` (appended) | Always-on core rules (~30 lines) |
| `SKILL.md` | `~/.claude/skills/second-order-thinking/SKILL.md` | Full reference (loaded on demand) |
| `anti-patterns.md` | `~/.claude/skills/second-order-thinking/anti-patterns.md` | Detailed anti-pattern guide |
| `examples.md` | `~/.claude/skills/second-order-thinking/examples.md` | Before/after reference |

## Full install (with skill files)

```bash
# 1. Core rules (inject directly into CLAUDE.md)
cat cognitive-protocol.md >> ~/.claude/CLAUDE.md

# 2. Skill files
mkdir -p ~/.claude/skills/second-order-thinking
cp SKILL.md ~/.claude/skills/second-order-thinking/
cp anti-patterns.md ~/.claude/skills/second-order-thinking/
cp examples.md ~/.claude/skills/second-order-thinking/

# 3. (Core rules already injected in step 1)
```

## Verify

Ask Claude Code: "What are the second-order thinking rules you're following?" It should list the four sections from `cognitive-protocol.md`: trace consequences forward, run the counterfactual, detect nonlinear transitions, anti-pattern self-check.

## Stacking with other cognitive bases

If First Principles or Tacit Knowledge is already injected into `CLAUDE.md`, no changes needed. All protocols load independently. First Principles audits reasoning inputs; Second-Order Thinking traces reasoning consequences; Tacit Knowledge governs output quality. No conflicts.

## Uninstall

```bash
# Remove the Second-Order Thinking section from ~/.claude/CLAUDE.md (search for "# Second-Order Thinking — Cognitive Protocol" header)
rm -rf ~/.claude/skills/second-order-thinking
```
