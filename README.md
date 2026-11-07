# WGU D426 Study Kit

Everything I used to study for **WGU D426: Data Management – Foundations**, built for short, focused bursts.

### [Open the study app →](https://unkwncokonut.github.io/wgu-d426-study-guide/)

Learn mode, flashcards, a practice test, and a cram sheet. Works on your phone. Progress saves automatically.

---

## Start here: how much time do you have?

| Time | Do this |
| --- | --- |
| **3 min** | Read the [cram sheet](guide/00-cram-sheet.md) |
| **15 min** | Start a 15-min focus sprint in the [app](https://unkwncokonut.github.io/wgu-d426-study-guide/), pick **one** topic, run **Learn** |
| **30 min** | One [guide module](guide/README.md) → Learn on that topic → practice test on that topic |
| **90 min** | The night-before plan below |

## What's inside

| | What | Where |
| --- | --- | --- |
| **App** | Learn · Flashcards · Practice test · Cram sheet | [`index.html`](index.html) ([live](https://unkwncokonut.github.io/wgu-d426-study-guide/)) |
| **Guide** | 10 short modules, 3 to 6 minutes each | [`guide/`](guide/README.md) |
| **Cards** | 148 terms + 55 practice questions | [`data/cards.json`](data/cards.json) |
| **Exports** | Quizlet, Anki, and spreadsheet versions | [`flashcards/`](flashcards/) |

## How Learn mode works

It works like Quizlet's Learn:

1. You get a **round of 7** cards (change it to 5 or 10 in Options).
2. New cards are **multiple choice**. Get one right and it becomes **Familiar**.
3. Familiar cards come back as **type the answer**. Get it right and it's **Mastered**.
4. Miss one and it comes back **later in the same round**.
5. Typos are forgiven, and if the grader is wrong you can press **I was right**.

The green bar fills as you master cards. Pick one topic chip to keep the bar small and winnable.

## Built for ADHD brains

- **One thing on screen at a time.** Topic chips hide while you're mid-round.
- **Short rounds** with a summary after each, so you get a finish line every few minutes.
- **Instant feedback** with a one-line "why" on every practice question.
- **Focus timer** (10, 15, or 25 minutes) that tells you to take a break when it ends.
- **Streak counter** for momentum.
- **Keyboard first:** `1`–`4` to answer, `Enter` to continue, `Space` to flip.
- **Guide modules all have the same shape:** TL;DR → details → exam traps → 3-question self-check.
- Readable font (Atkinson Hyperlegible), dark mode, and reduced motion if your device asks for it.

## Night-before plan (90 minutes)

| Sprint | Minutes | Do |
| --- | --- | --- |
| 1 | 15 | Learn: **Writing queries** + **Joins & views** |
| | 5 | Break: stand up, water |
| 2 | 15 | Learn: **Keys & constraints** + **Normalization** |
| | 5 | Break |
| 3 | 15 | Learn: **ER modeling** + **Physical design** |
| | 5 | Break |
| 4 | 20 | Practice test, all 55. Retry the misses |
| 5 | 10 | [Cram sheet](guide/00-cram-sheet.md). Then sleep. |

## Use the cards somewhere else

- **Quizlet:** Create a set → *Import* → paste [`flashcards/quizlet-import.txt`](flashcards/quizlet-import.txt). Keep "Between term and definition" set to **Tab**.
- **Anki:** *File → Import* → [`flashcards/anki-import.csv`](flashcards/anki-import.csv). Topics come in as tags.
- **Spreadsheet:** [`flashcards/practice-questions.csv`](flashcards/practice-questions.csv) has all 55 questions with answers.

## Run it offline

Download the repo and double-click `index.html`. No install, no server.

## Edit or add cards

1. Edit [`data/cards.json`](data/cards.json).
2. Run `python3 tools/build.py`.
3. That regenerates `data/cards.js` (used by the app) and everything in `flashcards/`.

---

Personal study notes, written in my own words. Not affiliated with or endorsed by WGU or zyBooks. Always check the official course material.
