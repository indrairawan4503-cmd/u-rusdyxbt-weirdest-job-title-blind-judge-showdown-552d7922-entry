# NOTES — Variant A: absurd CLIENT

## Final title

`Ghostwriter for Dead Celebrities' Memoirs` — **41 characters** (1–60 gate: PASS).

Lane A: a real-sounding profession (ghostwriter) whose client is
impossible (dead celebrities, dictating their memoirs). The job stays
genuine; the client supplies the twist. See VERSIONS.md for the v1–v8
iteration (one concept, refined; only v8 ships).

## Validation

- Two runs with different `MAKEFUN_OUTPUT_DIR` temp dirs: outputs
  byte-identical.
- Both outputs byte-identical to repo-root `entry.txt`.
- sha256 of output: `b1dc1b5f00e8529aedb93fc1bc8740cc3226204ba9abbe288c3a1c7d5466a1dc`
- Gate: UTF-8, 41 chars, not only whitespace, one title + one trailing
  newline — PASS.
- Grader simulation: repo copied to /tmp, chmod read-only,
  `python3 -P -s main.py` with `MAKEFUN_OUTPUT_DIR` set — exit 0,
  output correct and byte-identical (the repo-root write fails silently
  inside try/except OSError, as designed).
- `main.py` is deterministic: no network, no randomness, no time.
  Primary output (`/output/entry.txt` or `MAKEFUN_OUTPUT_DIR`) is written
  FIRST; the repo-root copy is best-effort only.

## File checks

- LICENSE: line 1 `SPDX-License-Identifier: MIT`, full MIT text — PASS.
- `.makefun/owner.json`: exactly
  `{"wallet":"FT1ect39XkeTprHy44WyUFprgHZbEUxAvQkWKspfiuPH"}` — PASS.
- README.md: official template, 3 live make.fun badges (competition,
  rank, reward) with owner `indrairawan4503-cmd` and repo
  `u-rusdyxbt-weirdest-job-title-blind-judge-showdown-552d7922-entry`,
  no `{owner}`/`{repo}` placeholders, `## Run it` section, referral
  footer `8dxq9bq0` — PASS.
- `entry.txt`: title + one trailing newline, byte-identical to program
  output — PASS.
