# Quiz CLI

> An interactive command-line quiz game for learning JavaScript, Node.js, and general programming concepts.

## Project Overview

Quiz CLI is a lightweight terminal-based quiz application built with modern Node.js and ES modules. When you start the app, it loads questions from a local JSON file, lets you choose a quiz category and question count, then walks you through each question with immediate feedback and a final score summary.

This project is designed as both a fun learning tool and a compact example of common Node.js patterns, including:

- ES module imports/exports
- async/await and Promises
- file system access
- interactive terminal input using `readline`
- classes and basic OOP design
- JSON-driven application data

## Features

- **Interactive terminal quiz** with numbered multiple-choice answers.
- **Category selection** for different topics.
- **Question count selection** with support for all questions or a smaller subset.
- **Shuffled questions** so each run feels slightly different.
- **Immediate answer validation** with correct/incorrect feedback.
- **Explanations after questions** to reinforce learning.
- **Progress display** during the quiz.
- **Final results summary** with performance-based messaging.
- **No external dependencies** required.
- **ANSI color output** for a more polished CLI experience.

## Tech Stack

- **Runtime:** Node.js 18+
- **Language:** JavaScript (ES Modules)
- **Built-in APIs:**
  - `node:fs/promises`
  - `node:path`
  - `node:url`
  - `node:readline`
- **Data Format:** JSON

## Project Structure

```text
.
├── .gitignore
├── data/
│   └── questions.json
├── index.js
├── package.json
└── src/
    ├── colors.js
    ├── input.js
    └── quiz.js
```

### File Responsibilities

- **`index.js`**
  - Application entry point.
  - Loads questions from `data/questions.json`.
  - Handles the main game loop, category selection, and replay prompts.

- **`src/quiz.js`**
  - Contains the `Quiz` class.
  - Handles question shuffling, scoring, progress tracking, answer checks, and result rendering.

- **`src/input.js`**
  - Wraps Node's `readline` module.
  - Provides helpers for prompting, selecting options, confirming actions, and waiting for Enter.

- **`src/colors.js`**
  - Centralized ANSI color helper utilities.
  - Used to make terminal output more readable and visually distinct.

- **`data/questions.json`**
  - Quiz content organized by category.
  - Includes question text, answer options, the correct answer index, and optional explanations.

- **`package.json`**
  - Project metadata and scripts.
  - Defines the `start` and `test` commands.

## Getting Started

### Prerequisites

- Node.js **18.0.0 or later**
- npm (bundled with Node.js)

### Installation

```bash
git clone https://github.com/Pri1me/test_app.git
cd test_app
npm install
```

> There are no runtime dependencies, so `npm install` is optional, but it is still a good habit to keep the project workflow consistent.

### Run the Quiz

```bash
npm start
```

or run directly:

```bash
node index.js
```

## Usage Example

A typical session looks like this:

1. Launch the app.
2. Choose a category.
3. Choose how many questions to answer.
4. Answer each multiple-choice question by entering the option number.
5. Review your score and explanations at the end.
6. Decide whether to play again.

### Example Interaction

```text
Choose a category:

  1. JavaScript Basics
  2. Node.js Fundamentals
  3. General Programming

Your choice (enter number): 1

How many questions?

  1. All questions
  2. 3 questions
  3. 5 questions

Your choice (enter number): 2
```

## How It Works

- The app reads quiz data from `data/questions.json` at runtime.
- Categories are dynamically derived from the JSON file.
- Questions are shuffled before each quiz session.
- User input is handled through a promise-based `readline` wrapper.
- Results are calculated after all questions are answered and then displayed with a summary and review section for missed questions.

## Scripts

From `package.json`:

- **`npm start`** — Runs the quiz app.
- **`npm test`** — Runs Node's built-in test runner (`node --test`).

## Development Notes

- The project uses `type: "module"`, so all imports/exports use ES module syntax.
- The quiz content is entirely data-driven, which makes it easy to add or edit questions without changing application logic.
- The terminal UI relies on ANSI escape codes and should work in most modern terminals.

## Extending the Project

Here are a few natural ways to extend Quiz CLI:

- Add more quiz categories to `data/questions.json`
- Randomize answer option order as well as question order
- Persist high scores between runs
- Add timers for each question
- Track quiz history or difficulty levels
- Support free-text questions in addition to multiple choice

## License

This project is licensed under the **MIT License** as declared in `package.json`.
