# Doc Conventions

Two audiences, two doc sets — never mix them.

## Living vs historical

Every doc is one of:

- **Living** — tracks current state; updated when reality changes
  (README, RELEASE, AUDIT, LICENSING, REPOS, ROADMAP).
- **Historical** — frozen point-in-time records (build plans, session
  logs). Gets a status banner at the top: `HISTORICAL — frozen at
  <date>; see <living doc> for current state.` Never silently goes
  stale, never deleted without reason.

## The drift rules

1. **Facts live in one place.** Version numbers, paths, counts get
   sourced from code where possible — docs reference, don't duplicate.
2. **Claims match code.** If a doc says a feature works, the feature
   works *as described*. Discovered mismatches go in the audit gap table
   same-day.
3. **Status banners on everything frozen.** Nothing rots silently —
   either it's maintained or it's marked historical.
4. **Dates on evidence.** "Verified" without a date is a rumor.

## Two-audience rule

| Private (DEV) | Public (OP / SDK) |
|---|---|
| Internals, paths, architecture, honest status | Capabilities, usage, positioning |
| Can name files, line counts, module internals | Never reveals implementation — describes what the product *does* |
| Audit machinery, plans, mistakes | The product face — clean, confident, accurate |

Same facts, different depth. Public docs are written assuming a hostile
reader looking for attack surface and a user looking for capability.
