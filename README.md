# Daily Telegram Quiz Bot

Posts four daily MCQ quizzes (Physics, Chemistry, Biology, Math) to a Telegram
group every day at 17:30 Asia/Riyadh, based on a pre-built 350-day plan.

## How it works

1. `خطة_350_يوم.xlsx` maps `day -> module + question numbers`.
2. `_build/answers.json` holds the correct letter for each of the
   35 × 40 questions.
3. Images live in `35 modules/<module>/<question>.png`.
4. `quiz_bot.py` figures out today's day number from `START_DAY` + `START_DATE`,
   then sends 4 photo+poll pairs to Telegram.
5. GitHub Actions schedules the run at 14:30 UTC (17:30 KSA) daily.

## Required secrets

Set these in **Settings → Secrets and variables → Actions**:

| Name                  | Value                              |
|-----------------------|------------------------------------|
| `TELEGRAM_BOT_TOKEN`  | Token from BotFather               |
| `TELEGRAM_CHAT_ID`    | `-100xxxxxxxxxx` (supergroup id)   |

`START_DAY` and `START_DATE` are set directly in the workflow file.

## Manual run

You can trigger the workflow at any time from the Actions tab via
**Run workflow** — useful for testing and for posting a missed day.
