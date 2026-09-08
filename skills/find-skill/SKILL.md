---
name: find-skill
description: >-
  Use when the user does not know if a skill exists, asks what skill can do a
  job, or wants the plugin to look through connected marketplaces. Present
  listings. Do not add them until the user says add.
---

# Find a skill

The user does not need to know the skill name. They ask a bot. The bot uses this plugin. The plugin looks through the marketplaces the user connected and returns matching listings.

## Do

1. Read the local thin index first. If a listing already covers the ask, say so and name its marketplace links. Do not crawl if the local listing is enough and the user only asked what they already have.
2. If they want skills they do not have, look through each marketplace they connected. Read listings only: name, purpose, keywords, source repo, marketplace URL. Do not load every body.
3. Drop anything whose license you cannot use, and anything that is a secret or a standing lock.
4. Present a short list. For each: name, when to use it, source repo, and the marketplace links. If the same skill appears on more than one marketplace, or on a fork of the same repo, show it once with every link.
5. Same name from a different repo that is not a fork is a different skill. Show it as its own line.
6. Stop. Wait for the user to say which to add.

## Do not

- Add a listing because it matched. The user adds it.
- Paste a body into a bot profile.
- Query every marketplace on an ordinary message. This runs when the user asks what is available, or asks the bot to look.
- Guess a body if a marketplace is down. Say which store you could not read.

## After they say add

Hand the chosen listing to the import path. One listing in the local database. Extra marketplaces for the same repo, or a fork of that repo, are links on that entry.
