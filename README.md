# skill-index

A skill library for Grok Bot.

You do not have to know the skill name. Ask a bot what you want done. The plugin looks through the skill marketplaces you connected and shows you what fits. You add the ones you want. After that, your bots can use them.

![skill-index](logo.png)

## What you get

You get a short list, not a pile of instructions dumped into every chat.

- Ask in plain language. You do not need the skill's name.
- The bot shows matching skills: what they do, where they came from, and the marketplace links.
- Nothing is added until you say add.
- After you add it, your bots can use that skill. They do not load every skill on every message.
- If two skills could both do the job, the bot loads neither and names both, so you can pick.
- The same skill found in more than one marketplace is one entry, with a link for each place. A copy from the same repo, or from a fork of that repo, is another link on that same entry. A different skill stays its own entry.

Your bots keep their own rules. A found skill does not overwrite who the bot is.

## Try it

1. Copy this folder to `~/.cursor/plugins/local/skill-index`.
2. Reload the window.
3. Ask a bot: "Is there a skill for writing a short release note?"
4. It should find one match and use it.
5. Then ask, in one message, to check a class deck and a pull request. Two skills fit. It should name both and use neither.

The starter includes three example skills so you can try this with nothing else connected.

## Add a skill you found

When the bot shows a skill from a marketplace, say add. It goes into your local library. Show the row first. Skip anything whose license you have not confirmed.

If that skill is already in your library from the same repo, or from a fork of that repo, you get another marketplace link. You do not get a second copy of the same skill.

## What this is not

This is not a dump of other people's skills. It does not put their full instructions into your bots.

It is also not listed on the official Cursor marketplace. Install it from this repo.

## License

MIT. Author: SathiaAI.
