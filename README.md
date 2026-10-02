# IDE

An **AI Web IDE** — describe a website in natural language and generate it, then edit, preview, and export the result, all from a single HTML file. No build step, no backend, no login.

## Features

- **Natural-language generation** — Enter a prompt; the IDE calls the AI provider to generate site code
- **Monaco editor** — Full VS Code-style code editing with syntax highlighting (via CDN)
- **Live preview** — Rendered preview of the generated site in an embedded frame
- **Multiple AI providers** — Model selector with **Gemini**, **DeepSeek**, and **OpenRouter**; keys entered in-page and stored in `localStorage` (never leave your browser)
- **Format code** — One-click code formatting
- **Export ZIP** — Download the generated project as a `.zip` (JSZip)
- **Console + terminal panels** — Bottom panels for console output and a mock terminal
- **Dark/light theme** — Toggleable UI theme
- **Open in new tab** — Open the preview standalone

## Tech Stack

- Single static `index.html` (vanilla JavaScript)
- Monaco Editor (CDN)
- Tailwind CSS (CDN)
- JSZip (CDN)
- Google Gemini / DeepSeek / OpenRouter APIs (user-provided keys)

## Quick Start

No install needed — it's one static file:

```bash
npx serve .
# or
python3 -m http.server 8000
```

Open `http://localhost:8000`, paste your API key for one of the supported providers (Gemini / DeepSeek / OpenRouter), and describe the site you want.

## Usage

1. Enter your API key in the settings panel (stored only in your browser's `localStorage`)
2. Choose a provider/model from the model selector
3. Type a prompt, e.g. *"a landing page for a coffee shop with a menu section"*
4. Click **Generate** — the code appears in the Monaco editor and renders in the live preview
5. Edit, re-generate, or **Export ZIP** to download the project

## Security Notes

- API keys are stored in `localStorage` and sent directly from your browser to the provider — never to a third-party server.
- This is a demo/prototype tool; treat it like a scratchpad, not a production pipeline.
- Note: Git history may contain earlier secrets if keys were ever committed — rotate any exposed keys.

## Project Structure

```
.
├── index.html   # The entire IDE (UI + editor + preview + provider integrations)
├── README.md
```

## Deploy Notes

Fully static — serve `index.html` from GitHub Pages, Cloudflare Pages, Netlify, or any static host. No environment variables; API keys are entered by the user at runtime.

---

Built by Girish Lade — https://ladestack.in
