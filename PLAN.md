# PLAN: Van Conversion Design Repo Setup

## Task Restatement
Set up a van conversion design repository for a 2004 Ford E350 that integrates the image-blaster skillset for designing and visualizing van interior layouts, exterior wraps, and conversion concepts.

## Approaches Considered

### Approach 1: Fetch files via curl (chosen)
- Fetch each skill file directly from GitHub raw URLs
- Save to matching paths in the repo
- Simple, direct, matches the task instructions exactly
- Risk: network requests could fail; files may have changed upstream

### Approach 2: Clone image-blaster and copy files
- `git clone https://github.com/neilsonnn/image-blaster` then copy files
- More robust but heavier — downloads entire repo history
- Not needed when we only need specific files

### Approach 3: Submodule
- Add image-blaster as a git submodule
- Overkill; we just need static skill files, not ongoing sync

## Chosen Approach
Approach 1 — fetch individual files via curl, save to correct paths. Exactly matches the instructions.

## Files to Touch
- `PLAN.md` (this file)
- `TODO.md`
- `CLAUDE.md`
- `.env.example`
- `.claude/settings.json`
- `.claude/rules/project.md`
- `.claude/skills/image-blast-uncover/SKILL.md`
- `.claude/skills/image-blast-uncover/IMAGE-BLAST.md`
- `.claude/skills/image-blast-world/SKILL.md`
- `.claude/skills/image-blast-3d/SKILL.md`
- `.claude/skills/image-blast-image-edit/SKILL.md`
- `.claude/skills/image-blast-plate/SKILL.md`
- `.claude/skills/image-blast-sfx/SKILL.md`
- `.claude/skills/image-blast-project/SKILL.md`
- `.claude/skills/image-blast-wildcard/SKILL.md`
- `input/.gitkeep`
- `worlds/.gitkeep`
- `designs/.gitkeep`
- `designs/interior/.gitkeep`
- `designs/exterior/.gitkeep`
- `designs/electrical/.gitkeep`
- `designs/BRIEF.md`

## Risks and Unknowns
- GitHub raw URLs may be unavailable or return 404 if the repo structure differs
- `.env.example` content is unknown until fetched — must not commit real secrets
- settings.json may have paths or config specific to the original repo that need review
