# skill-index

Your agent stops loading the wrong skill.

A closer keyword does not cancel a second match. If two skills still fit, this loads neither and names both.

![skill-index](logo.png)

Most agents with a pile of skills do one of two bad things. They paste every skill into the standing prompt, so the prompt gets long, expensive, and confused. Or they grab the nearest keyword and run the wrong procedure, then call the job done.

This plugin does the opposite. The standing prompt stays short. A full skill loads only when it is the only match. If the match is unclear, nothing loads. The bot's own locks still win.

## What you get

- One skill, or none. Never a silent wrong load.
- A named collision when two skills still match, so you can pick.
- Done only when that skill's own success check can be scored from this turn. Loaded but unscored is not a hit.
- Your locks stay in the bot profile. This index never overwrites who the bot is.
- A way to point at your own store: files, Notion, Airtable, Coda, or a sheet.
- An importer for Claude and Codex `SKILL.md` files. It maps a file to one index row. It does not paste the skill into the profile.

This is a method, not a skill library. Other people's skill bodies, secrets, and bot identity stay with you.

## Try it in 60 seconds

This repo ships a file starter with three fixture rows. No Notion required.

1. Copy this folder to `~/.cursor/plugins/local/skill-index`.
2. Reload the window so Cursor picks up the always-on rule in `rules/skill-index.mdc`.
3. Point the index at `starters/file-index`. Read `index.md` only. Do not load every body.
4. Ask for a short release note. One row matches (`release-note`). One body should load.
5. Ask, in one turn, to check a class deck and a fail-closed pull-request diff. Two rows match (`deck-text-check` and `pr-text-check`). The agent should load neither and name both.

If the store is down, use the local thin cache: name, purpose, keywords, and negatives only. Do not guess a body.

## The rule

1. Match purpose and keywords.
2. Drop negatives and edge-case vetoes.
3. If two skills still match, load neither and name both. A closer keyword does not cancel a second match.
4. Load one body, matching edge cases, and only related lessons.
5. Score the success line before calling the job done. If it cannot be scored from this turn, the score is not a hit.
6. If the store is down, use the local thin cache. Do not guess a body.

Locks in the standing prompt always win over a retrieved skill.

## What is in this repo

- `rules/skill-index.mdc` is the short always-on line.
- `skills/skill-index` is the load order.
- `skills/import-agent-skill` maps a Claude or Codex `SKILL.md` into one index row. Show the row before it lands. Skip secrets and any license you have not confirmed.
- `starters/file-index` is three fixture rows so the method runs with no Notion.
- `EVAL.md` is how a hit, a miss, a wrong load, and a fake done are scored.

## Stores

Files first if you have no preference. Notion, Airtable, or Coda if that is what you already edit. Keep a small local copy of name, purpose, keywords, and negatives. Do not query the store on every message.

## Not included

This is not a dump of other people's skills. It is not an official listing on the Cursor marketplace at cursor.com/marketplace. Install it from this repo, as above.

## License

MIT. Author: SathiaAI.
