# WGU D426 Study Kit

Everything I used to study for **WGU D426: Data Management – Foundations**, built for short, focused bursts.

### [Open the website →](https://unkwncokonut.github.io/wgu-d426-study-guide/)

An interactive study site: a "what do you have time for?" start page, the competencies page, the full guide, Quizlet-style Learn mode, flashcards, a practice test with an exam simulation, a podcast, and Study Buddy for questions. Works on your phone. Progress saves automatically.

## Exam blueprint

The objective assessment is split into three competencies. Everything here follows the same split. Full breakdown: **[COMPETENCIES.md](COMPETENCIES.md)** (or the [Competencies tab](https://unkwncokonut.github.io/wgu-d426-study-guide/#competencies) on the website).

| Competency | Share of exam | zyBook | Guide | Study it |
| --- | --- | --- | --- | --- |
| **1. Explains Database Attributes and SQL Commands** | 28% | Lessons 1 & 2 | Modules 1–5 | [Learn C1](https://unkwncokonut.github.io/wgu-d426-study-guide/#learn/c1) |
| **2. Determines SQL Queries** | 30% | Lesson 3 | Modules 6–7 | [Learn C2](https://unkwncokonut.github.io/wgu-d426-study-guide/#learn/c2) |
| **3. Defines Primary Keys** | **42%** | Lessons 4 & 5 | Modules 8–10 | [Learn C3](https://unkwncokonut.github.io/wgu-d426-study-guide/#learn/c3) |

> [!IMPORTANT]
> Competency 3 is the biggest chunk, so it gets the most study time. It covers all of zyBook lessons 4 & 5: ER modeling, normalization, and physical design. Primary keys run through all of it, including how each kind of table gets its key ([module 9](guide/09-normalization.md)).

**Exam simulation:** the website's [Practice test](https://unkwncokonut.github.io/wgu-d426-study-guide/#test) has a 30-question simulation split 8 / 9 / 13 by competency, scored per competency so you see where to focus.

---

## Start here: how much time do you have?

| Time | Do this |
| --- | --- |
| **3 min** | Read the [cram sheet](guide/00-cram-sheet.md) |
| **15 min** | Focus sprint on Competency 3 (the biggest chunk): [Learn C3](https://unkwncokonut.github.io/wgu-d426-study-guide/#learn/c3) |
| **30 min** | One [guide module](guide/README.md) from C3 → Learn on it → the [exam simulation](https://unkwncokonut.github.io/wgu-d426-study-guide/#test/sim) |
| **90 min** | The plan below, weighted like the exam |

## What's inside

| | What | Where |
| --- | --- | --- |
| **Website** | Start · Competencies · Guide · Learn · Flashcards · Practice test + exam simulation · Podcast · Cram sheet, plus the **Ask** button | [`index.html`](index.html) ([live](https://unkwncokonut.github.io/wgu-d426-study-guide/)) |
| **Guide** | 10 short modules grouped by competency, 3 to 7 minutes each | [`guide/`](guide/README.md) |
| **Cards** | 153 terms + 83 practice questions | [`data/cards.json`](data/cards.json) |
| **Podcast** | 8 ready-made MP3 episodes, about an hour total | [`audio/`](audio/) |
| **Exports** | Quizlet, Anki, and spreadsheet versions | [`flashcards/`](flashcards/) |

## How Learn mode works

It works like Quizlet's Learn:

1. You get a **round of 7** cards (change it to 5 or 10 in Options).
2. New cards are **multiple choice**. Get one right and it becomes **Familiar**.
3. Familiar cards come back as **type the answer**. Get it right and it's **Mastered**.
4. Miss one and it comes back **later in the same round**.
5. Typos are forgiven, and if the grader is wrong you can press **I was right**.

The green bar fills as you master cards. Pick one competency chip (C1, C2, C3), then a topic inside it to keep the bar small and winnable.

## Study Buddy (the Ask button)

Tap **Ask** on any page. It explains terms, compares two ideas ("WHERE vs HAVING"), explains a practice question you paste in, and quizzes you ("quiz me on C3").

- **Explain** buttons in Learn, Flashcards, and the practice test send that exact card or question to Study Buddy.
- **Works with no setup:** answers come from this site's course notes (153 terms, 83 questions, 10 guide modules).
- **Optional Claude mode** for open-ended questions: in Study Buddy's Settings, paste your own [Anthropic API key](https://console.anthropic.com). It's sent only to `api.anthropic.com`, billed to your account, and forgotten when you close the tab unless you tick "Remember". Answers stay grounded in the course notes.

## Podcast

The **Podcast** tab turns the course into audio with two hosts: **Alex** explains, **Sam** asks the questions and pauses so you can answer in your head.

- **Ready-made MP3s** (keep playing with the screen off, downloadable): the exam blueprint, one episode per competency, the cram sheet, and a quiz show per competency. Each has a tap-to-jump transcript.
- **Make your own**, spoken with your device's voice: any single guide module, a 10-question quiz show, the terms you haven't mastered, your missed questions from the last practice test, or any text you paste in.
- Every guide module and competency has a **Listen** button.

## Built for ADHD brains

- **Tells you what to do next.** The Start page points you at the competency with the most exam points left to win.
- **One thing on screen at a time.** Topic chips hide while you're mid-round.
- **Short rounds** with a summary after each, so you get a finish line every few minutes.
- **Instant feedback** with a one-line "why" on every practice question.
- **Focus timer** (10, 15, or 25 minutes) that tells you to take a break when it ends.
- **Streak counter** for momentum.
- **Keyboard first:** `1`–`4` to answer, `Enter` to continue, `Space` to flip.
- **Guide modules all have the same shape:** TL;DR → details → exam traps → 3-question self-check.
- Readable font (Atkinson Hyperlegible), dark mode, and reduced motion if your device asks for it.

## 90-minute plan, weighted like the exam

Learn time is split by exam share, biggest first. On the website's Start page, tap **90 min** to get this with one-tap Go buttons.

| Sprint | Minutes | Do |
| --- | --- | --- |
| 1 | 25 | [Learn C3](https://unkwncokonut.github.io/wgu-d426-study-guide/#learn/c3) (42%): ER modeling, keys & normal forms, physical design |
| | 5 | Break: stand up, water |
| 2 | 18 | [Learn C2](https://unkwncokonut.github.io/wgu-d426-study-guide/#learn/c2) (30%): writing queries, joins & views |
| | 5 | Break |
| 3 | 17 | [Learn C1](https://unkwncokonut.github.io/wgu-d426-study-guide/#learn/c1) (28%): basics, SQL commands, keys & constraints |
| | 5 | Break |
| 4 | 15 | [Exam simulation](https://unkwncokonut.github.io/wgu-d426-study-guide/#test/sim): 30 questions split 8 / 9 / 13 |

Right before the exam: the 3-minute [cram sheet](guide/00-cram-sheet.md).

## Use the cards somewhere else

- **Quizlet:** Create a set → *Import* → paste [`flashcards/quizlet-import.txt`](flashcards/quizlet-import.txt). Keep "Between term and definition" set to **Tab**.
- **Anki:** *File → Import* → [`flashcards/anki-import.csv`](flashcards/anki-import.csv). Tags look like `D426::C3::Physical_design`.
- **Spreadsheet:** [`flashcards/practice-questions.csv`](flashcards/practice-questions.csv) has all 83 questions with answers and competency.

## Run it offline

Download the repo and double-click `index.html`. No install, no server.

## Edit cards or the guide

1. Edit [`data/cards.json`](data/cards.json) or any file in [`guide/`](guide/).
2. Once: `pip install markdown`. Then run `python3 tools/build.py`.
3. That regenerates `data/cards.js` and `data/guide.js` (used by the website), `COMPETENCIES.md`, and everything in `flashcards/`.
4. To re-record the podcast: `pip install piper-tts playwright`, then `python3 tools/podcast.py` (needs ffmpeg). Voices download once from the [Piper](https://github.com/rhasspy/piper) releases.

---

Personal study notes, written in my own words. Not affiliated with or endorsed by WGU or zyBooks. Always check the official course material.
