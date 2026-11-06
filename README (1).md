# VA Squad

Nine AI specialists built for the modern Tech Virtual Assistant. Automation, GoHighLevel, web marketing, contracts, outreach, pricing, onboarding, and more. One premium console, no build step, runs anywhere.

![status](https://img.shields.io/badge/status-live-e10600) ![license](https://img.shields.io/badge/license-MIT-fafafa) ![stack](https://img.shields.io/badge/stack-html%20%2B%20react%20cdn-000)

## What it is

A single-file web app that gives you nine specialized AI agents to work with. Each agent has its own persona, goals, rules, and memory. Chat with them, save conversations locally, view and copy any agent's system prompt to use elsewhere.

Built for freelance Tech VAs who want to sharpen their craft without juggling ten different tools.

## The roster

| Agent | Role | What they do |
|-------|------|--------------|
| **Sage** | Contract Expert | Spots red flags, drafts airtight client agreements |
| **Mira** | Interview Coach | Preps you for discovery calls and client interviews |
| **Rex** | GHL Troubleshooter | Diagnoses and fixes GoHighLevel issues fast |
| **Vera** | Graphic Designer | Design direction, color, and layout critique |
| **Pitch** | Cold Outreach Writer | Writes cold emails and DMs that get replies |
| **Max** | Proposal and Pricing Coach | Helps you charge more and close bigger deals |
| **Flow** | SOP and Workflow Builder | Turns messy processes into clean SOPs |
| **Nova** | Client Onboarding Specialist | Designs smooth client onboarding experiences |
| **Volt** | GHL and N8N Automation Architect | Designs and builds automation workflows |

## Features

- **Nine specialized agents** with distinct personas, goals, and rules
- **Real streaming chat** powered by Anthropic's Claude API
- **Persistent memory** per agent, stored in your browser via localStorage
- **View prompt** button on every agent so you can copy the system prompt to use in ChatGPT, Claude.ai, or anywhere else
- **Model picker** in settings: switch between Sonnet, Haiku, and Opus
- **Starter prompts** on every agent so you never face a blank page
- **Premium dark UI** with editorial serif headlines and racing-red accents
- **Zero build step**: single HTML file, React and Tailwind via CDN
- **Mobile responsive** with safe-area handling for iOS

## Setup

### Option 1: Just open the file locally

1. Download `index.html` from this repo
2. Double-click it, or open it in any modern browser
3. Paste your Anthropic API key when prompted
4. Pick an agent and start chatting

### Option 2: Deploy to GitHub Pages

1. Fork this repo (or create your own with these files)
2. Go to **Settings** then **Pages**
3. Set **Source** to **Deploy from a branch**
4. Pick the `main` branch and `/root` folder
5. Save, wait a minute, visit `https://<your-username>.github.io/<repo-name>/`

### Option 3: Deploy to Netlify, Vercel, or Cloudflare Pages

Drop the folder into any static host. There's no build step. Just point it at `index.html`.

## Getting an Anthropic API key

1. Go to [console.anthropic.com/settings/keys](https://console.anthropic.com/settings/keys)
2. Sign in or create an account
3. Click **Create Key**, name it something like "VA Squad"
4. Copy the key (starts with `sk-ant-`)
5. Paste it into VA Squad on first launch

You'll need credit in your Anthropic account. The pay-as-you-go tier is enough for personal use. Typical cost is pennies per chat on Sonnet or Haiku.

## Privacy and security

- Your API key is stored **only in your browser's localStorage**, never sent anywhere except directly to Anthropic when you chat
- Your chat history is stored **only in your browser's localStorage**, never uploaded
- Nothing leaves your device except API calls to `api.anthropic.com`
- **Do not use this on a shared or public machine.** Anyone with access to your browser can read your key
- If you deploy a public version, each visitor uses their own key stored in their own browser

## Customizing

### Change an agent's persona

Open `index.html`, find the `AGENTS` array near the top of the script section, and edit the `systemPrompt`, `tagline`, `starters`, or `role` for any agent.

### Add a new agent

Add a new object to the `AGENTS` array. Each needs: `id`, `name`, `role`, `emoji`, `tagline`, `starters`, and `systemPrompt`.

### Swap models

Open settings in the app and pick a different model. Or edit the `MODELS` array in `index.html` to change the default or add new model IDs. Check [Anthropic's model docs](https://docs.anthropic.com/en/docs/about-claude/models) for current IDs.

### Rebrand the look

All colors live in CSS variables at the top of the `<style>` block in `index.html`. Change `--red` to swap the accent color. Change `--bg` for a different base.

## Tech stack

- Vanilla HTML, no build step
- React 18 via CDN (unminified Babel for JSX in-browser)
- Tailwind CSS via Play CDN
- Instrument Serif and Inter via Google Fonts
- Anthropic Messages API with streaming

## Known limitations

- Babel in-browser transpilation adds a small startup delay (less than a second on most machines). Fine for a personal tool. For a production app, pre-compile the JSX
- Browser localStorage caps around 5 to 10 MB depending on browser. Very long conversations across all nine agents could hit this
- No search across past conversations (yet)
- Model IDs in the code may go stale over time. Update them inline when Anthropic releases new ones

## Roadmap ideas

- Export conversation as Markdown
- Search across all agent chats
- Custom agents you can create in the UI
- Shared team deployment with backend proxy (so a team can share the tool without each person managing a key)

## License

MIT. See [LICENSE](LICENSE).

## Credits

Built as a personal tool for Tech VAs working in automation, GoHighLevel, and web marketing. Inspired by the idea that a specialist beats a generalist every time.
