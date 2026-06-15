---
name: NasBeat CI fixes
description: Durable lessons from fixing Build & Release CI for nastech-ai/NasBeat
---

## windows-latest runner regression (June 2025)
`windows-latest` moved to Windows Server 2025 which lacks VS2019, breaking Flutter's CMake generator.
**Fix:** pin to `runs-on: windows-2022` explicitly.
**Why:** Flutter Windows desktop uses CMake with VS2019 toolchain; Server 2025 changed default toolchain.
**How to apply:** Any Flutter Windows CI job should use `windows-2022` not `windows-latest` until Flutter explicitly supports Server 2025.

## GitHub Actions job-level secret guard pattern
`if: secrets.SOME_SECRET != ''` is invalid at the **job** level (secrets are not available in job-level conditionals).
**Fix:** expose secret as an env var on the job, then guard individual steps:
```yaml
jobs:
  my-job:
    env:
      HAS_SECRET: ${{ secrets.SOME_SECRET != '' && 'true' || 'false' }}
    steps:
      - name: Use secret
        if: env.HAS_SECRET == 'true'
        run: ...
```
**Why:** GitHub Actions only evaluates `secrets.*` in `env:` and `with:` contexts, not in `if:` expressions at job level.
**How to apply:** Whenever a job needs to conditionally skip based on a secret being present/absent.

## Build & Release run verification (June 2026)
Full end-to-end run `27582308781` completed all jobs successfully:
- 🪟 Windows & 🤖 Android ✅ (windows-2022 fix confirmed working)
- 🐧 Linux ✅
- 🍎 macOS ✅  
- 📝 Release Notes Bot ✅
- 🛒 Google Play (internal track) ✅ (skipped gracefully — no secret configured)
