# Repo Model — the three-tier split

Every Sentinal product gets three repos. Same shape every time — no
reinventing the boundary per project.

| Tier | Naming | Audience | Contains |
|---|---|---|---|
| **DEV** | `<Product>-DEV` (private) | owner + in-house | full source, internals, keygen/secrets, audit docs. **All production builds are cut here.** Moves freely — experiments and regressions welcome. |
| **OPS** | `<Product>-SDK` (private or limited) | collaborators, staff operators | contract surface only: interface `.d.ts`, API reference, fresh examples, submission docs. *Contract, not implementation.* |
| **OP** | `<Product>-OP` (public) | the world | product docs, community files, release assets. Never source, never internals. |

## The stability gate

**DEV is the permanent working point.** OP and SDK are only updated
after a proven-stable release run through the pipeline. The outside
world only ever sees verified states — if DEV is mid-refactor, the
public artifact stays untouched.

## Flow rules

```
DEV ──build──▶ artifacts ──verified──▶ OP release assets
DEV ──verified──▶ OP doc updates + SDK contract updates
SDK ──module submissions──▶ DEV (reviewed, land in builds)
OP  ──community signal──▶ DEV  (issues, discussions — that's all)
```

- Sync check script (`repo-sync-status.mjs` pattern): per-repo HEAD,
  dirty files, unpushed/behind counts. Covers the release-critical pair.
- `dist/` and all binary output: gitignored everywhere, always.
- Public docs describe **capability, never implementation** — no source
  paths, no internals, nothing that aids reversing.

## Leak checklist (run before any public push)

- [ ] No private source paths in public files
- [ ] No keygen/codec/secret material
- [ ] No internal audit references
- [ ] No build commands that reveal internals
- [ ] grep for secrets + internal file names
