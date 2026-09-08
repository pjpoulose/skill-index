---
name: find-skill
description: >-
  Use when the user does not know if a skill exists, asks what skill can do a
  job, or wants the plugin to look through connected marketplaces. Show
  matches. Do not write them to the local SQLite library until the user says add.
---

# Find a skill

The user does not need to know the skill name. They ask a bot. The bot uses this plugin. The plugin searches the marketplaces on the default list, plus any the user added, and shows matching skills.

## Do

1. Search the marketplaces. Read listings only: name, purpose, keywords, source repo, marketplace URL. Do not load every body.
2. Show a short list. If the same skill appears on more than one marketplace, or on a fork of the same repo, show it once with every link.
3. Stop. Do not write the search results to SQLite.

## Do not

- Save a match because it was found. Connecting a marketplace does not fill the library.
- Paste a body into a bot profile.
- Search on an ordinary message. This runs when the user asks what is available.

## After they say add

Write that one skill to the local SQLite library. Only saved skills live there. Same repo, or a fork of that repo, is another link on that entry, not a second row.
