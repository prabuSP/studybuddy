*This is a submission for the [Hacktoberfest Weekend Challenge: Build for a Friend](https://dev.to/challenges/hacktoberfest-weekend-2026-10-01)*

## What I Built

I built **StudyCraft**, a clean, distraction-free study companion designed for my friend Maya, a biology student who was struggling with study burnout, endless exam anxiety, and the bloat of modern study tools.

Maya was tired of existing flashcard and quiz apps that hit her with paywalls after 20 cards, bombard her with unsolicited ads in the middle of review sessions, and require messy account setups. Most importantly, she was constantly tab-switching between an external Pomodoro timer website, a flashcard site, and her course notes, breaking her deep study flow.

**StudyCraft** solves this by unifying the entire study routine into one calm, local-first workspace:
- **Custom Study Set Builder**: Create subject decks with terms, definitions, and hints in seconds. Includes a **Quick Batch Import** feature that lets Maya copy-paste 30 lecture terms at once using simple delimiters (`Term | Definition`), saving hours of manual data entry.
- **Companion Pomodoro Clock**: A customizable focus timer (25/5/15 intervals or custom minute blocks) with a subtle radial countdown and synthesized Web Audio chime alerts. Crucially, the timer remains pinned in the top navigation as a companion ticker, allowing Maya to review flashcards or take quizzes without pausing her Pomodoro session.
- **Tactile 3D Flashcards**: Realistic flip cards with spaced self-assessment ratings (*Again*, *Hard*, *Good*, *Easy*), full keyboard navigation (<kbd>Space</kbd> to flip, <kbd>1-4</kbd> to rate), card starring, and offline text-to-speech pronunciation.
- **Self-Testing Practice Quiz**: Students can test themselves with custom multiple-choice questions or click **Auto-Generate Quiz from Cards**, which instantly generates 4-choice tests with plausible distractors from their own deck, providing explanations for every answer.
- **Zero Login Friction & 100% Privacy**: All cards, streaks, mastery ratings, and high scores are persisted locally in the browser, with instant one-click JSON backup and restore.

---

## Demo

- **Live Deployed App**: [StudyCraft on Google Cloud](https://ais-pre-nkxdbv4tf5ts56gybyb56k-974150620489.asia-east1.run.app)
- **Alternate Dev URL**: [Development Preview](https://ais-dev-nkxdbv4tf5ts56gybyb56k-974150620489.asia-east1.run.app)

### Key Workflows
1. **Explore Curated Starter Decks**: Jump straight into pre-built decks (*Cell Biology & Organelles*, *World History & Revolutions*, or *Computer Science Essentials*).
2. **Build or Import in Seconds**: Click **New Study Set**, type terms individually or open **Quick Batch Import** to paste lecture notes, and hit **Auto-Generate Quiz from Cards**.
3. **Launch Pomodoro Flow**: Start the 25-minute focus clock. Switch tabs to Flashcards or Practice Quiz—the timer keeps ticking quietly in the navbar with instant pause/play controls.
4. **Master Active Recall**: Review cards with smooth 3D flip animation, rate your confidence, and celebrate deck completion with confetti and a targeted breakdown of cards that need practice.

---

## Code

The project is built as a modern, high-performance React + TypeScript SPA styled with Tailwind CSS:

- **Frontend Framework**: React 19 + TypeScript
- **Styling & Design System**: Tailwind CSS v4 with bespoke typography pairing (Fraunces serif headings, Plus Jakarta Sans body, and JetBrains Mono tabular numerals)
- **Audio Synthesizer**: Pure Web Audio API oscillator synthesis for pleasant, offline-ready bell chimes and feedback (no bulky external MP3 dependencies)
- **Visuals & Delight**: 3D CSS perspective card flips and `canvas-confetti` celebrations upon quiz completion and deck mastery

You can view the full repository files in the project workspace:
- `/src/App.tsx` — Main application controller and background Pomodoro ticker
- `/src/components/PomodoroTimer.tsx` — Radial progress countdown, presets, and fullscreen focus mode
- `/src/components/FlashcardStudy.tsx` — 3D interactive flashcard engine with keyboard shortcuts and TTS
- `/src/components/QuizView.tsx` — Dynamic multiple-choice exam interface with instant explanations
- `/src/components/StudySetBuilder.tsx` — Deck manager with batch paste parser and auto-distractor generator
- `/src/components/Dashboard.tsx` — Study streak counter, deck library, and metrics overview
- `/src/utils/audio.ts` — Web Audio API harmonic chime synthesizer
- `/src/utils/storage.ts` — LocalStorage state synchronization and import/export utilities

---

## How I Built It

To develop StudyCraft rapidly and maintain an uncompromising standard of code quality and aesthetic polish, I built this application using the **Google AI Studio Agent** harness with **Gemini 2.5/Gemini Pro** models.

The agent session followed an execute-first, design-conscious methodology:
1. **Domain-Native Architecture**: Instead of defaulting to generic AI card templates or purple gradients, we followed strict UI/UX constitutions: warm stone background palettes, unboxed metadata separated by typographic dots (`·`), single-elevation cards, and accessible touch targets.
2. **Automated Distractor Synthesis Engine**: Built a pure TypeScript algorithmic generator in `src/utils/storage.ts` that dynamically transforms any flashcard set into balanced multiple-choice questions with randomized distractors from neighboring concepts.
3. **Resilient Offline Audio**: Rather than relying on third-party audio CDNs that fail in restricted school or university Wi-Fi networks, we implemented custom sine/triangle oscillator chains using the browser's native `AudioContext`.
4. **Instant Build Verification**: Validated the entire project with automated TypeScript typechecks (`tsc --noEmit`) and Vite compilation tools to ensure zero runtime regressions.

---

## Why Does Open Innovation Matter?

Open innovation and open-source tooling fundamentally democratize learning:
1. **Empowering the Learner, Not the Algorithm**: Closed, commercial study apps are engineered around ad impressions, daily active user traps, and artificial subscription paywalls. Open innovation allows developers to build software that respects the user's attention, giving students like Maya an ad-free, clutter-free utility that exists purely to help them learn.
2. **Local-First Data Ownership**: In closed platforms, if a service changes its pricing tier or shuts down, a student's months of carefully written study decks disappear. With open standards and simple JSON schemas, students own their data permanently. They can back it up, migrate it, or print it anytime.
3. **Extensibility & Accessibility**: Using open web technologies (Web Audio API, SpeechSynthesis, CSS 3D transforms) proves that production-grade educational software can run anywhere—on a Chromebook, an old tablet, or a phone—without demanding high-end hardware or expensive software licenses.

---

## My Agent Session

- **Tooling**: Built and verified with Google AI Studio Agent Session
- **Applet ID**: `72c8cfcf-6a3e-41a8-9b31-38ef16510684`
- **Environment**: Linux Vite + React 19 + TypeScript Runtime

---

## Prize Categories

- **Primary**: Hacktoberfest Weekend Challenge: Build for a Friend
- **Tags**: `#webdev`, `#react`, `#productivity`, `#opensource`, `#education`
