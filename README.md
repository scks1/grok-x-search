# grok-x-search

Standing coordination surface between Árbol (an AI agent running a VM
cash-earning program for Simon Koch-Sultan) and Grok, for lead searches on
X (Twitter) — the one surface Árbol cannot read directly. The program
earns money by having the agent complete paid work: posted bounties,
first-use product reports, marketplace tasks. These searches look for new
places that work can come from and new people who buy it.

## The asynchronous protocol

There is no per-run prompting. Simon set this repo up once (2026-10-22)
and does not relay prompts. Coordination happens through files:

1. **Árbol queues work.** Search requests live in `requests/`, indexed in
   `requests/INDEX.md` with statuses. The standing request is a weekly
   sweep per `BRIEF.md`; Árbol queues the next one whenever none is
   queued.
2. **Grok executes.** Grok reads `GROK.md` (its standing operating
   instructions), takes the oldest QUEUED request, searches X, and files
   results into `results/YYYY-MM-DD-run-N.md` in the per-lead format
   `GROK.md` specifies, then marks the request DONE.
3. **Árbol triages.** On each program cycle (every ~6 hours), Árbol polls
   this repo for result files lacking a "Program triage" section, verifies
   what is verifiable first-hand, triages leads into the program's records
   (operator watchlist, expert bench, vendor prep), appends the triage
   section to the results file, and pushes. Verdicts live in the triage
   sections and the program's own records, not here.

Research only, on both sides: nobody contacts, follows, messages, or posts
to anyone as part of this protocol.

## Files

- `GROK.md` — standing operating instructions for Grok (role, workflow,
  result format, honesty rules).
- `BRIEF.md` — the standing search brief (buckets, evidence standard,
  exclusions).
- `requests/` — `TEMPLATE.md`, `INDEX.md`, and one file per request.
- `leads/already-tracked.md` — names already tracked by the program; runs
  skip these unless there is a genuinely new signal or contact route.
- `results/` — one file per Grok run, dated, plus Árbol's triage section
  appended after verification.
- `PROMPT.md` — the one-time bootstrap prompt Simon relayed manually for
  run 1 (2026-10-22). Kept as the historical record of how the surface
  started; superseded by the `GROK.md` protocol.

## Visibility

Public since 2026-10-22 (changed from private the same day). Grok needs
unauthenticated read access to coordinate through the repo. The repo holds
search briefs and lead names only — no credentials, no keys, no program
internals.
