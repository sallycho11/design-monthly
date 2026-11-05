# sally-chat

Serverless function behind the "Ask about Sally" chat on [sallycho.design](https://sallycho.design).

- `api/ask.js`: `POST {question, history}` → `{answer, topic}`. Answers only from the portfolio facts in the file, via Google Gemini's free tier. Allowed origins: sallycho.design and Framer preview domains. Per-IP and hourly limits.
- Env var: `GEMINI_API_KEY` (Google AI Studio key; keep billing off on its Google project so it can never charge). Optional `GEMINI_MODEL` to pin a model.
- Any error returns a non-200 status and the chat falls back to its built-in answers.

Deploy on Vercel with **Root Directory** set to `sally-chat`.
