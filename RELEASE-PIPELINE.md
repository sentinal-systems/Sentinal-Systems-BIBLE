# Release Pipeline — the gate

Every Visentrix release runs this. No shortcuts — the pipeline is the
product's credibility.

```
audit → fix gaps → typecheck → harness → production build → package
→ packaged-runtime test → commit → tag → publish assets
```

## The rules

1. **Audit first.** Walk the codebase against the last audit's open
   items. Fix or honestly re-classify before building.
2. **Static gate.** Typecheck clean; lint where configured. Warnings
   get recorded, not ignored.
3. **Harness.** Run the self-check suite. A release candidate that fails
   its own harness doesn't ship.
4. **Package the real artifact.** Installer + portable, signed.
5. **Test the packaged artifact, not the dev build.** Dev proves code;
   packaging proves shipping. Drive the actual binary — IPC, panels,
   workers inside the bundle, license flows.
6. **Disposable profiles for destructive tests.** `--user-data-dir`
   sandboxes so license/tamper tests never touch real state.
7. **Commit + tag** the exact commit the build came from. The tag IS
   the release marker — binaries must trace to it.
8. **Publish assets, not binaries-in-git.** Release assets on the public
   repo; `dist/` stays gitignored forever.
9. **Hash-verify uploads.** sha256 local == sha256 on the release, or it
   didn't happen.
10. **Record evidence in the audit doc** — what was tested, how, and
    what remains honestly unverified.

## Never-regress invariants (product-agnostic)

- Users are never hard-locked out — degrade, don't lock.
- The public artifact only ever sees proven-stable states.
- Secrets/keys/internals never cross to public or collaborator repos.
