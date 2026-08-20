# Local AI — Ollama Chat Client

A simple browser-based chat interface for [Ollama](https://ollama.com/), built with plain HTML, CSS, and JavaScript.  
No frameworks, no build tools — just open `index.html` and start chatting with your local models.

---

## Features

- Chat with locally running Ollama models.
- Switch between installed models on the fly.
- Create, switch, and delete conversations.
- Conversations and settings auto‑save to `localStorage`.
- Adjust temperature, top‑p, top‑k, min‑p, repeat penalty, context size, max tokens, and seed.
- Set a custom system prompt.
- Streamed responses with basic Markdown rendering (headings, lists, inline code, code blocks with copy).
- Responsive layout (desktop and mobile).
- Keyboard shortcuts: `Enter` to send, `Shift+Enter` for newline, `Ctrl+K` to focus input, `Escape` to close menus.

---

## Getting Started

### Prerequisites

- [Ollama](https://ollama.com/download) installed and running.
- At least one model pulled, e.g.:

```bash
ollama pull llama3.2
```

### Run the client

1. Clone or download this repository.
2. Open `index.html` in any modern web browser.  
   (Using a local server like VS Code’s *Live Server* is recommended for full CORS compatibility.)
3. Ensure Ollama is running (`http://localhost:11434` by default).

The app will auto‑detect your installed models — select one and start chatting.

---

## Configuration

All settings are stored in `localStorage` and persist across sessions.

| Parameter        | Description                                 |
|------------------|---------------------------------------------|
| Temperature      | Randomness (0.0 = deterministic, 2.0 = max) |
| Top‑P            | Nucleus sampling threshold                  |
| Top‑K            | Limit vocabulary to top K tokens            |
| Min‑P            | Minimum token probability                   |
| Repeat penalty   | Penalise repetition (1.0 = none)            |
| Context size     | Max tokens in model’s memory                |
| Max output tokens| Max length of generated response            |
| Seed             | Fixed seed for reproducible output          |

You can also provide a custom **system prompt** in the settings panel.

---

## Tech Stack

- **HTML5** – structure  
- **CSS3** – styling, dark theme, responsiveness  
- **Vanilla JavaScript (ES6+)** – logic, state, API calls  
- **Ollama REST API** – `/api/chat`, `/api/tags`, `/api/show`  
- **localStorage** – persistence  

---

## Project Structure

```
.
└── index.html          # Everything (HTML, CSS, JS) in one file
```

Keeping it simple — a single file for easy deployment and experimentation.

---

## What I Learned

- Streaming HTTP responses with `fetch()` and `ReadableStream`.
- Building a reactive UI without frameworks.
- Managing state and persistence with `localStorage`.
- Handling asynchronous operations and request abortion (`AbortController`).
- Integrating with a local LLM via a REST API.

---

## License

MIT — use it as you like.