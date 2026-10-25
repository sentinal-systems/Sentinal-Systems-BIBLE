# Onboarding — bringing existing code into the estate

The admission procedure for code that predates the doctrine — legacy
projects, R&D spikes, inherited tooling. Proven on Homelab Tools,
25 Oct 2026.

A codebase found on disk is a claim, not a product. Onboarding is the
pipeline that turns claims into admitted products — or honest archives.

## The stages

```
DISCOVER ──▶ REGISTER ──▶ AUDIT ──▶ CONFORM ──▶ INSTRUMENT ──▶ CANDIDATE ──▶ ADMIT
```

| Stage | What it means | It is done when |
|---|---|---|
| **Discover** | Find the real thing. Estates lie by accumulation — stale registry paths, shadow copies, multiple generations on top of each other. Locate the live tree; quantify source vs junk. | You know which directory is real and roughly what it weighs |
| **Register** | Make the estate map true. Registry entity points at the real path and remote; Atlas maps reality, not memory. | A fresh scan reflects the actual tree |
| **Audit** | Per `AUDIT-CONVENTIONS.md`: compile sweep, entry-point truth, claim-vs-code table, variant map, transport map. Written as a living doc in the repo. | Every headline claim is either evidenced or struck |
| **Conform** | Brand and entity. Run brand-guard; fix live code *and* archived generations — legacy code gets promoted back and must arrive correct. Allowlist only records. Public docs name the entity. | `brand-guard` passes with a minimal, reasoned allowlist |
| **Instrument** | Make proof repeatable: a validation harness in the repo — inventory, safe/mutating classification by static analysis, supervised runs for anything that can change the machine. | A rerunable check exists; nobody blind-runs mutating tools |
| **Candidate** | `PRODUCTS.md` entry marked *candidate — admission pending*: four planes described honestly (a plane may be "simulated" — say so), class declared, gate listed. | The entry exists and its gate is real work, not cosmetics |
| **Admit** | The §5 test satisfied *with evidence*: planes real, honest degradation demonstrated, contracts not internals, operator policy respected, standalone-first proven. | Full registry entry — or an honest archive/sunset record |

## The rules

- **Never amend the doctrine to fit a codebase.** If it can't satisfy
  §5, the code is wrong or it isn't a product.
- **Runtime evidence beats file inspection.** "It compiles" < "it ran"
  < "a human watched it work." Validation is visual where possible.
- **No blind runs.** Trust is staged: static analysis → headless →
  supervised → free. Installers, network config, cleaners, and firewall
  tools are never auto-executed.
- **Legacy is data, not debris.** Older generations are archived and
  rebranded, not deleted — they are frequently better than their
  replacements, and comparison is the only way to know.
- **Docs rot; gates don't.** Every stage leaves its evidence in a
  durable place — registry, in-repo audit doc, PRODUCTS.md — so the
  next audit starts from truth.
- **Branding is part of admission, not polish.** A product carrying a
  superseded entity name is not onboarded, however good its code.
