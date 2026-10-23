# grok-x-search

Shared workspace for X (Twitter) lead searches delegated to Grok, supporting a
VM cash-earning program in which an AI agent (Árbol, assistant to Simon
Koch-Sultan) earns money by completing paid work: posted bounties, first-use
product reports, marketplace tasks.

## How the relay works

1. Simon pastes the current prompt (PROMPT.md) into Grok, which can search X.
2. Grok returns leads in the format the prompt specifies. Research only —
   Grok does not contact anyone.
3. Returned findings are filed under results/ with their date, then triaged
   into the program's records (operator watchlist, expert bench, DEC-020
   vendor prep). Duplicates are checked against leads/already-tracked.md.

## Files

- PROMPT.md — the paste-ready orientation prompt for Grok (source of truth).
- BRIEF.md — the standing search brief the prompt is generated from
  (buckets, evidence standard, exclusions).
- leads/already-tracked.md — names already tracked by the program; new Grok
  runs skip these unless there is a genuinely new signal or contact route.
- results/ — one file per Grok run, dated.
