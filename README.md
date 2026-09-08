# skill-index

Your bot's instructions are full. Every extra job you paste in is charged on every message, even when that job is not the one you asked for.

skill-index keeps the instructions short. A skill is picked up only when the words in the request match it. The bot stays light. You use fewer tokens.

![skill-index](logo.png)

## The problem

You can only add so much to a bot's instructions. After a while they are bloated with jobs that are not needed right now. That extra text burns tokens, and the bot gets slower to the point. It grabs a leftover instruction and does the wrong thing.

Anthropic describes the same fix for Claude: keep only the skill's name in view, and load the full instructions when the task needs them. [Their write-up](https://www.anthropic.com/engineering/equipping-agents-for-the-real-world-with-agent-skills).

## What you get

A lighter instruction set. The bot stays nimble. Token use drops because unused skills are not sitting in the chat.

- Ask for the job in plain language. You do not need the skill's name.
- The bot matches on keywords and picks up one skill.
- If two skills both match, it picks neither and names both, so you can choose.
- The same skill found in more than one marketplace is one entry, with a link for each place. A copy from the same repo, or a fork of that repo, is another link. A different skill stays its own entry.
- Nothing is added to your library until you say add.

Your bots keep their own rules. A skill does not overwrite who the bot is.

## Try it

1. Copy this folder to `~/.cursor/plugins/local/skill-index`.
2. Reload the window.
3. Ask: "Write a short release note."
4. One skill matches. The bot uses that one.
5. Then ask, in one message, to check a class deck and a pull request. Two skills fit. It names both and uses neither.

## License

MIT. Author: SathiaAI.
