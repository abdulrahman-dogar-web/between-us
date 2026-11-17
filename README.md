# Between Us 💕

A private Q&A room for two people. Pick a mood, share a 6-letter code, answer honestly — answers reveal only when both have submitted.

**Live:** https://abdulrahman-dogar-web.github.io/between-us/

## How it works

1. Enter your name, pick an avatar emoji and a colour.
2. Choose a mood and **Create room**, or **Join** with a room code.
3. Share the code with your partner — they join from their own phone, over the internet.
4. Tap **Next question**. Each of you types an answer and submits.
5. When **both** have submitted, the answers reveal side-by-side. Talk about it in free chat, then go to the next one.

## Moods

- 💗 **Lovely** — sweet & romantic
- 🌙 **Deep** — real & honest
- 😄 **Fun** — silly & playful
- ✨ **Manifesting** — dreams & the future
- 🦄 **Delulu** — wild what-if scenarios

Each mood has 20 questions, in English and Roman Urdu (EN/UR toggle in the room). The host can switch moods between questions.

## Add a question

Either player can type their own question. It is **rephrased automatically** (locally, no AI service — e.g. “what if…”, “rate 1–10…”, “finish the sentence…”, “pick one…”) so it feels like the game asked it, and it becomes the next question.

## Tech

- Static single-page app, no signup, no login. Mobile-first.
- Live sync through the shared Cloudflare Worker backend (`https://apps-backend.abdulrahman-dogar.workers.dev`, generic KV `PUT/GET /v1/kv/:key`), same as Watch Party. Room state lives under key `bu:<CODE>`.
- Clients poll every 2s while the tab is visible and stop polling when hidden (saves the shared KV read budget). Writes happen only on real changes: join, answer, chat, question advance.
- Rooms expire after ~24h of inactivity and are never listed — only joinable via the code.
- No games yet (tic-tac-toe etc. deferred).

## Files

- `index.html` — the whole app (HTML + CSS + JS, question banks included)
- `LICENSE` — MIT

© 2026 Mr. Abdul Rahman Dogar
