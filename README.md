# Voice — English Speaking Partner

A voice-in, voice-out AI conversation partner that runs entirely in your browser. Talk out loud, it listens, replies (in text + spoken voice), and keeps the conversation going — like practicing with a real person.

Built for daily spoken English fluency practice: daily conversation, office/workplace English, or interview mock practice.

## How it works
- **Speech-to-text**: your browser's built-in `SpeechRecognition` (free, no setup)
- **AI reply**: calls the Google Gemini API (`gemini-2.0-flash`) directly with your own free API key (stored only in your browser's local storage — never sent anywhere except Google's API)
- **Text-to-speech**: your browser's built-in `SpeechSynthesis` (free, no setup)
- Tracks a simple daily practice streak

No backend, no build step, no npm install, no cost. It's a single `index.html` file.

## Requirements
- **Chrome** (best support for speech recognition — Safari/Firefox support is limited/absent)
- A free Google AI Studio API key from https://aistudio.google.com/apikey — sign in with any Google account, no credit card required, generous free daily quota (plenty for a 15 min daily practice session)

## Install it as an app on your phone (PWA)

This app is now a Progressive Web App — you can install it on your OnePlus so it sits on your home screen with its own icon and opens full-screen, like a real app. To install, Chrome requires the app to be served over HTTPS (not just opened as a local file), so host it free on GitHub Pages:

1. Push this folder to GitHub (see steps above) if you haven't already
2. On GitHub, go to your repo → **Settings** → **Pages**
3. Under "Source," choose **Deploy from a branch**, pick `main` branch and `/ (root)` folder, click **Save**
4. Wait ~1 minute, then GitHub gives you a live URL like `https://divya8810.github.io/voice-ai-english-agent/`
5. Open that URL in Chrome on your phone
6. Tap the **⋮ menu** → **Add to Home screen** → **Install**
7. Vox now appears as an app icon on your home screen — tap it to open full-screen, no browser bar

You'll paste your Gemini API key once inside the installed app, same as before.

## Run it locally

Clone the repo, then from inside the folder:

```bash
# Option A — just double click index.html
open index.html        # Mac
start index.html        # Windows

# Option B — run a tiny local server (recommended, some browsers block mic access on file:// URLs)
python3 -m http.server 8000
# then open http://localhost:8000 in Chrome
```

## Run it on your phone (OnePlus / Android)
1. Make sure your phone and laptop are on the same Wi-Fi network
2. On your laptop, run the local server: `python3 -m http.server 8000`
3. Find your laptop's local IP (Windows: `ipconfig`, look for IPv4 Address, e.g. `192.168.1.5`)
4. On your phone's Chrome browser, go to `http://192.168.1.5:8000`
5. Allow microphone permission when prompted
6. Paste your API key once — it's saved on that device/browser going forward

## First-time setup in the app
1. Go to https://aistudio.google.com/apikey, sign in with a Google account, click "Create API key" — copy it (starts with `AIza...`)
2. Open the app
3. Paste the key into the setup box
4. Pick a practice mode: Daily / Office / Interview
5. Tap the orb, speak, and it replies out loud automatically

## Notes
- Completely free — no billing set up, no card required.
- Your API key never leaves your browser except to call Google's Gemini API directly.
- If you clear browser data/local storage, you'll need to re-paste the key.
- The free tier has a daily request limit (generous enough for daily practice, but if you hit it, wait until the quota resets the next day).
