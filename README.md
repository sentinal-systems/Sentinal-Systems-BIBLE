# Sentinal Systems UK Build Playbook

The reusable workflow proven on OSINT Sentinel Workstation — extracted
for every Sentinal product going forward.

Proven on: v0.1.1, 22 Sep 2026 — shipped, signed, hash-verified release
with a clean private/public split and a working license system.

## The documents

| Doc | What it encodes |
|---|---|
| [`RELEASE-PIPELINE.md`](RELEASE-PIPELINE.md) | The audit→verify→package→publish gate every release must pass |
| [`REPO-MODEL.md`](REPO-MODEL.md) | The three-tier repo split (DEV / OPS / OP) and the stability gate |
| [`AUDIT-CONVENTIONS.md`](AUDIT-CONVENTIONS.md) | How to write honest audits — verified vs claimed, gap tables, evidence |
| [`DOC-CONVENTIONS.md`](DOC-CONVENTIONS.md) | Living vs historical docs, drift prevention, two-audience rule |
| [`ONBOARDING.md`](ONBOARDING.md) | Bringing legacy/R&D code into the estate — discover → audit → conform → instrument → admit |
| [`FOUNDERS-ROTATION.md`](FOUNDERS-ROTATION.md) | The R&D / product / housekeeping cycle — parts of days count, modes follow the work, housekeeping IS shipping prep |

## The one-sentence philosophy

**Never claim what you haven't verified, never leak what you haven't
sanitized, never publish what isn't proven.**
