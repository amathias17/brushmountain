# Agent Instructions

This project uses **bd** (beads) for issue tracking. Run `bd onboard` to get started.

## Memory

Keep `memory.jsonl` updated with changes, fixes, and completed work.

## Working Agreement
- Any change (add/remove/update feature, data, tooling, or process) must be reflected in this file and memory.jsonl immediately; remove entries when features are removed.
- No extra permission needed to edit/add/remove files or run necessary commands (respect safety constraints). Keep entries concise and ASCII unless existing content differs.

## Tooling Directives
- Available MCPs: `sequential-thinking`, `context7`, `astrodocs`, `deepwiki`, `playwright`.
- Usage: follow the required tool order below; explicitly state what you learned from each MCP; note any MCP that is unavailable and use the closest local alternative.
- Required tool order (use ALL MCPs sequentially; explicitly state what you learned from each):
  - sequential-thinking: produce phases + acceptance criteria + "definition of done". Allow only 3-5 thoughts at a time.
  - context7 + deepwiki: inspect repo structure, existing logic, models/data, and how key flows consume data.
  - astrodocs: confirm best practices for server-side data fetching/scraping patterns in Astro and where this logic should live.
  - deepwiki: map domain rules that affect correctness (points vs %, weighting, dropped/exempt/missing, extra credit, rounding).
  - playwright: open real pages and identify where data lives (network requests, GraphQL/REST responses, or DOM). Capture evidence: endpoints (paths only), response shapes, and robust selectors.

## Quick Reference

```bash
bd ready              # Find available work
bd show <id>          # View issue details
bd update <id> --status in_progress  # Claim work
bd close <id>         # Complete work
bd sync               # Sync with git
```

## Landing the Plane (Session Completion)

**When ending a work session**, you MUST complete ALL steps below. Work is NOT complete until `git push` succeeds.

**MANDATORY WORKFLOW:**

1. **File issues for remaining work** - Create issues for anything that needs follow-up
2. **Run quality gates** (if code changed) - Tests, linters, builds
3. **Update issue status** - Close finished work, update in-progress items
4. **PUSH TO REMOTE** - This is MANDATORY:
   ```bash
   git pull --rebase
   bd sync
   git push
   git status  # MUST show "up to date with origin"
   ```
5. **Clean up** - Clear stashes, prune remote branches
6. **Verify** - All changes committed AND pushed
7. **Hand off** - Provide context for next session

**CRITICAL RULES:**
- Work is NOT complete until `git push` succeeds
- NEVER stop before pushing - that leaves work stranded locally
- NEVER say "ready to push when you are" - YOU must push
- If push fails, resolve and retry until it succeeds
