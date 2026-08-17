# Cinephile

Curated movie recommendations powered by your taste and an LLM.

## What it does

- Paste your favorite films or a taste profile as a "seed"
- Get personalized movie recommendations via an LLM API
- Mark movies as watched — future recommendations adapt
- Tier system: Start Here → Essential → Deep Cuts → Modern Torch
- Filter by genre and movement (Film Noir, Nouvelle Vague, etc.)

## Setup

1. Open the page (or deploy to GitHub Pages)
2. Click **⚙️ Settings** and enter your API key
3. Click **✏️ Edit Seed** and paste your taste profile
4. Click **＋ Get Recommendations**

## Supported providers

| Provider | Endpoint | Notes |
|----------|----------|-------|
| DeepSeek | `https://api.deepseek.com` | Default. Cheap, fast. |
| OpenAI | `https://api.openai.com/v1` | |
| OpenRouter | `https://openrouter.ai/api/v1` | Many models, some free |
| Anthropic | `https://api.anthropic.com/v1` | Claude models |
| Ollama | `http://localhost:11434/api` | Local, no API key |
| Custom | Any OpenAI-compatible | |

## Data

All data is stored in your browser's localStorage. No backend, no tracking.

Use the export/import buttons in the page to back up your data.

## Deploy

This is a single `index.html` file. To deploy on GitHub Pages:

```bash
gh repo create cinephile --public --clone
cp index.html cinephile/
cd cinephile
git add index.html && git commit -m "Initial commit"
git push -u origin main
gh api repos/{owner}/cinephile/pages -X POST --input - <<EOF
{"build_type":"legacy","source":{"branch":"main","path":"/"}}
EOF
```

Or just open `index.html` directly in your browser.
