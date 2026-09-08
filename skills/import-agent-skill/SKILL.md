---
name: import-agent-skill
description: Use when the user gives a Claude skill, Codex skill, or SKILL.md and wants it in the skill index. Map the file. Do not paste it into a bot profile.
---

# Import an agent skill

Claude skills, Codex skills, and this index use the same file shape: `SKILL.md` with a name, a when-to-use line, a body, and optional references.

## Map

1. Read the `SKILL.md` frontmatter and body. Do not read scripts into the chat.
2. Write one index row:
   - name = frontmatter name
   - purpose = frontmatter description (must say when to use)
   - keywords = exact names already in the file, plus any the user adds. Do not invent a pile.
   - body pointer = a copy of the markdown body in the skill store, not a paste into a profile
   - references = paths under `references/` (or equivalent). Do not inline them.
3. Edge cases start empty unless the skill already has a clear "do not" section. Lift those as veto rows.
4. Lessons start empty.
5. Success check = one line taken from the skill if it states a done bar. If it does not, ask once, or write "worked if the steps completed without a listed veto."
6. If the name already exists, update that row. Do not create a second.
7. Show the mapped row before it lands.

## Skip

- Secrets, tokens, or private paths
- A license you cannot use
- Identity or standing locks. Those stay in the profile.

A imported skill is a retrieved skill. It does not become a standing instruction.
