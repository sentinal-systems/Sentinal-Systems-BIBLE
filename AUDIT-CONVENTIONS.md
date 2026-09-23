# Audit Conventions

How Visentrix writes audits — the format that made the Sentinel audit
trustworthy instead of decorative.

## The structure

1. **Scope line** — what was walked, when, at which commit.
2. **Gap table** — every inconsistency found: what a doc/comment claims
   vs what the code does. Fixes noted inline.
3. **Verified list** — checked-box items, each with *how* it was
   verified. Not "works" — "drove the packaged binary via CDP, all N
   checks passed."
4. **Remaining items** — honest open items, severity, and what closes
   each. Deferred work gets a reason, not silence.

## The rules

- **Evidence or it didn't happen.** A verified claim names the method
  and result. "Code exists" is not verification — runtime behavior is.
- **Shameless gap table.** Docs claiming more than code does is the
  most common drift; list every instance without mercy.
- **Gap severity honest.** Deferred isn't failed — label accurately so
  priorities stay real.
- **Append, don't rewrite.** Audits are dated sections in a living doc.
  Later audits reference earlier scope lines.
- **Never in public.** Audit docs are DEV-only; the public sees the
  product, not the confidence-building machinery.

## Sample gap-table row

| Item | Status | Evidence |
|---|---|---|
| Rolling-trial evaluation in production | ✅ verified | fresh profile → `license:status` evaluated → stable fresh trial |
| Session dispatcher thread | ⚠️ code exists, runtime unverified | `start()` exists; never exercised end-to-end |
