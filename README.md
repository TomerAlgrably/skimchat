# skimchat

A self-hostable Telegram bot that reads a noisy group chat so you don't have to.

**Status: v0.0.1, week 1.** The bot joins a group and stores its messages in a local
SQLite file. It does not summarise anything yet.

Planned, not built: a digest and action items with Claude Code as the extractor
(week 2), dates as a calendar file (week 3).

Built in public, one ticket at a time, in the course *Ticket to Ship*: [course link]

## Requirements

- Node 22 or newer
- A Telegram bot token from [@BotFather](https://t.me/BotFather)

## Setup

1. In BotFather: `/newbot`, then `/setprivacy` → Disable, so the bot sees all group
   messages and not only commands. Do this **before** adding the bot to your group; if it
   is already in the group, remove it and add it again. (Making the bot a group admin also
   works.) On start, the bot prints whether it can read all messages.
2. `cp .env.example .env` and put the token after `TELEGRAM_BOT_TOKEN=`. Never commit `.env`.
3. `npm install`

## Run

```
npm run dev     # start the bot
npm run seed    # load the invented demo group into the database
npm test        # run the tests
```

Messages are stored in `data/` on your machine and nowhere else.

## Privacy

The bot stores every text message in the groups it is added to. Only add it to a group
whose members know it is there. The demo data in `fixtures/` is invented: no real
people, groups or places.

## How this repo is run

Claude Code works from tickets in `tickets/` following `tickets/AGENT.md`; `CLAUDE.md`
holds the project rules; session logs are in `ai/sessions/`. A human reviews every diff.

## License

MIT. See `LICENSE`.
