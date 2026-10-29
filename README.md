# ESPO Study

An offline-first study PWA for the EPSO AD5 EU Knowledge test. The app contains **232 multiple-choice questions** extracted from the supplied **The Story of the Union — EU Knowledge for the EPSO AD5 Competition** guide — specifically the guide's own *Check Yourself* quizzes, with the guide's official answer keys and reasoning.

## Features

- **232 source-based MCQs** covering all 23 chapters (10 per chapter, 12 in Chapter 22)
- **Chapter navigator** grouped into the guide's eight parts
- **Quick 5** short sessions
- **Exam simulation** — 30 questions with a 40-minute countdown
- **Weak areas** and **mistake review**, driven by real recorded answers
- **Exit session** button with confirmation at any point
- **AI tutor bubble** for contextual help on the current question
- **Flashcards**, streaks, accuracy and progress tracking
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

Open **Settings** in the app, enter a Groq key, and save it locally. AI is optional: normal questions, flashcards and progress work without it. AI requests are made directly from the browser to Groq and require an internet connection. The app currently uses Groq model `qwen/qwen3.8-27b`.

## Content note

This is a study aid, not an official EPSO product. Always check the current Notice of Competition and candidate account for the final exam format, timing and pass mark.
