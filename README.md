# skill-index

Thin skill retrieval. The standing prompt stays short. Full instructions load only after a real match.

This is a method, not a skill library. Point it at your own store (files, Notion, Airtable, Coda, or a sheet). Locks stay in the bot profile. Procedures live in the index.

## Load order

1. Match purpose and keywords.
2. Drop negatives and edge-case vetoes.
3. If two skills still match, load neither and name both. A closer keyword does not cancel a second match.
4. Load one body, matching edge cases, and only related lessons.
5. Score the success line before calling the job done. If it cannot be scored from this turn, the score is not a hit.
6. If the store is down, use the local thin cache. Do not guess a body.

## Included

- `rules/skill-index.mdc` — short always-on line
- `skills/skill-index` — the load order
- `skills/import-agent-skill` — map a Claude or Codex `SKILL.md` into the index
- `starters/file-index` — three fixture rows, works with no Notion

## Not included

Other people's skill bodies, secrets, or bot identity. Those stay with you.

## Import

Claude skills and Codex skills are already `SKILL.md`. The importer maps that file to one index row. It does not paste the skill into a bot profile. If the name exists, it updates that row. Show the row before it lands. Skip secrets and any license you have not confirmed.

## Stores

Files first if there is no preference. Notion, Airtable, or Coda if that is what you already edit. Keep a small local copy of name, purpose, keywords, and negatives. Do not query the store on every message.
