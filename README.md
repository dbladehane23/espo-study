# ESPO Study

An offline-first study PWA for the EPSO AD5 EU Knowledge test. The app contains **393 multiple-choice questions** — the **232** original questions extracted from the supplied **The Story of the Union — EU Knowledge for the EPSO AD5 Competition** guide (the guide's own *Check Yourself* quizzes with its official answer keys), plus **161 new medium/hard questions** (7 per chapter) written from the same guide and made deliberately more technical: treaty articles, voting thresholds, signed-vs-in-force traps, procedure sequences and institutional confusion sets.

Every question is tagged with a difficulty — **easy**, **medium** or **hard** — so you can drill exactly the level you need.

## Features

- **393 source-based MCQs** covering all 23 chapters (17 per chapter, 19 in Chapter 22)
- **Difficulty levels** — easy / medium / hard on every question, with filter chips and dedicated **Medium drill** and **Hard drill** sessions; exam simulation draws mostly medium and hard
- **Current affairs verified October 2026** — the newest EU laws, checked against official sources: the 2040 Climate Law target (−90%), the CBAM definitive regime, ETS2's delay to 2028, the AI Act Digital Omnibus, the deforestation regulation dates and the Nature Restoration Law
- **Chapter navigator** grouped into the guide's eight parts
- **Completion ticks** — a chapter (and its part card) ticks off with a ✓ once you have attempted every question in the active difficulty filter
- **AI-generated questions** — from any chapter's ✦ button, ask the AI to write extra easy/medium/hard questions grounded in that chapter's source text; they are validated, saved to this device, marked with an **AI** badge and clearable from Settings
- **Quick 5** short sessions
- **Exam simulation** — 30 questions with a 40-minute countdown
- **Weak areas** and **mistake review**, driven by real recorded answers
- **Exit session** button with confirmation at any point
- **AI tutor bubble** for contextual help on the current question
- Streaks, accuracy and progress tracking
- **Installable PWA** that works offline once loaded
- Stats start at zero — nothing is faked

## Run locally

From this folder, run:

```bash
python3 -m http.server 4173
```

Open <http://localhost:4173>.

The app must be served over HTTP/HTTPS for the PWA service worker to work; opening `index.html` directly from a file may disable offline installation.

## Publish on GitHub Pages

1. Create a new GitHub repository, for example `espo-study`.
2. Upload the contents of this folder to the repository root:
   - `index.html`
   - `data.js` (the question bank — required)
   - `app.js`
   - `styles.css`
   - `manifest.json`
   - `sw.js`
   - `README.md`

   Do not upload the source PDF.
3. Do not upload a Groq API key. The app stores the key locally in the browser.
4. In GitHub, open **Settings → Pages**.
5. Under **Build and deployment**, choose **Deploy from a branch**.
6. Select the `main` branch and `/ (root)`, then press **Save**.
7. GitHub will provide a URL such as `https://your-name.github.io/espo-study/`.
8. Open that URL on the iPhone in Safari, tap **Share → Add to Home Screen**.

GitHub Pages can take a few minutes to publish. If an old version is displayed after an update, close the tab and perform a hard refresh; the service worker will then update its cache.

## Groq AI

Open **Settings** in the app, enter a Groq key, and save it locally. AI is optional: normal questions and progress work without it. AI requests are made directly from the browser to Groq and require an internet connection. The app currently uses Groq model `qwen/qwen3.8-27b`.

## Content note

This is a study aid, not an official EPSO product. Always check the current Notice of Competition and candidate account for the final exam format, timing and pass mark.
