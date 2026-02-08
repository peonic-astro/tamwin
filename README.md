# Krynn D&D Campaign Repository

This repository manages multiple D&D campaigns using git branches. Each campaign is isolated in its own branch with complete character sheets, world state, inventory, and session notes.

## Branch Structure

### `main` - Template & Shared Resources
- `CLAUDE.md` - DM instructions and campaign rules (shared across all campaigns)
- `DND.SRD.Wiki/` - D&D 5e SRD rules reference (shared)
- Template files for starting new campaigns
- This README

### Campaign Branches
Each active campaign lives in its own branch:

- **`hamm-campaign`** - Hamm Wildtongue (Human Bard), gritty dungeon crawl in dark fantasy Krynn
- **`tamwin-campaign`** - Tamwin Badgerfoot (Halfling Fighter), exploration and investigation

## Starting a New Campaign

1. Create a new branch from main:
   ```bash
   git checkout main
   git checkout -b new-campaign-name
   ```

2. Set up character files:
   - `character.md` - Character sheet
   - `inventory.md` - Equipment and currency
   - `world_state.md` - Current campaign state
   - `adventure_log.md` - Session recaps
   - `npcs.md` - Known NPCs
   - `names.md` - Name registry
   - `locations.md` - Visited locations
   - `adventure_style.md` - Tone and style guide
   - `dm_only/story_prep.md` - DM secrets (edit via Task agent only)

3. Commit and push:
   ```bash
   git add -A
   git commit -m "Initialize [Character Name] campaign"
   git push -u origin new-campaign-name
   ```

## Switching Between Campaigns

To switch to a different campaign:
```bash
git checkout campaign-name
```

To see all campaigns:
```bash
git branch -v
```

## Syncing Across Devices

On your first device:
```bash
git add -A
git commit -m "Session X progress"
git push
```

On your second device:
```bash
git checkout campaign-name
git pull
```

## Updating Shared Resources

If you update `CLAUDE.md` or other shared files on `main`, merge them into campaign branches:

```bash
git checkout main
# Make changes to CLAUDE.md
git commit -am "Update DM instructions"
git push

git checkout hamm-campaign
git merge main
git push
```

## File Structure

Each campaign branch contains:

| File | Purpose |
|------|---------|
| `character.md` | PC stats, abilities, backstory |
| `inventory.md` | Equipment, currency, consumables |
| `world_state.md` | Authoritative current state |
| `adventure_log.md` | Session recaps |
| `adventure_style.md` | Tone, pacing, difficulty |
| `npcs.md` | Known NPCs (player knowledge) |
| `names.md` | Name registry |
| `locations.md` | Visited locations |
| `session_X_notes.md` | Active session notes (temporary) |
| `dm_only/story_prep.md` | Secrets, plots, NPC agendas |

See `CLAUDE.md` for complete campaign management rules.

## Tips

- **Commit frequently** during sessions to avoid losing progress
- **Always pull before starting** a session on a different device
- **Keep main branch clean** - only shared resources, no campaign-specific content
- **Each campaign is independent** - changes in one don't affect others
- **Use descriptive commit messages** - "Session 3: Arrived in Brackford" not "Update files"

---

*For questions about Claude Code DM system, see CLAUDE.md*
