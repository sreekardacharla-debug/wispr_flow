# VaidehaVoice 🎙️

A voice-first companion for India's 50 million home caregivers.

## The Problem
50 million women in India manage sick relatives at home — no training,
no support, no product built for them. They make medical decisions
alone, every day, in the dark.

## The Solution
Speak. Get a real answer. In your language.

VaidehaVoice listens to caregivers describe symptoms in Hindi or
their local language, remembers each patient's history, and responds
with specific, calm, medically grounded guidance.

## How to Run
1. Clone this repo
2. Open `index.html` in Chrome on Android (or serve it: `npx serve .`)
3. Enter your Claude API key when prompted (stored locally only)
4. Tap the mic. Speak in Hindi.

**Note:** Web Speech API (mic input) requires HTTPS or localhost and works
best in Chrome on Android. If the mic is unavailable, a text-input fallback
appears automatically.

## No secret keys required
The app uses your own Claude API key, entered once and stored in
your browser. No backend. No server. No data leaves your device
except the voice query to Claude API.

## Features
- **One screen, one button** — no login, no typing, no English required
- **Voice in → AI processes → voice out** (Web Speech API + Speech Synthesis, hi-IN with en-IN fallback)
- **Patient memory** — profiles persist across sessions in localStorage (`vaidehavoice_patients`), updated silently after every exchange via Claude-based extraction
- **Voice-only new-patient setup** — 2–3 spoken questions create a profile
- **Emergency detection** — words like "behosh", "seene mein dard", "saans nahi" trigger an immediate spoken warning + red 108 call button *before* any API call
- **Error handling** — offline, API failure, and missing-mic paths all speak Hinglish guidance
- **Exact system prompt** from the spec, verbatim; patient context prepended as `[PATIENT: name, conditions, medications, recent]`

## Tech Stack
- Web Speech API (voice input)
- Claude API `claude-sonnet-4-6` (AI reasoning)
- Web Speech Synthesis (voice output)
- localStorage (patient memory)
- Zero dependencies, one HTML file

## Deploy
```bash
vercel deploy --prod
```
(Static site — index.html is served as-is.)

## Demo
[YouTube link]

## Built for
Build for Bharat Hackathon — Healthcare Access track
