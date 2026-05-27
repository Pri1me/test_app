# Quiz CLI

A terminal-based interactive quiz game for learning JavaScript, Node.js, and general programming concepts.  
Built with **Node.js** and **ES modules**, with **no external runtime dependencies**.

## Features

- Interactive command-line quiz experience
- Category selection from a local question bank
- Question count selection
- Shuffled multiple-choice questions
- Immediate correct/incorrect feedback
- Explanations for answers
- Progress tracking during the quiz
- Final score summary with performance messaging
- Review of incorrect answers
- Replay support
- ANSI-colored terminal output for a cleaner CLI experience

## Project Structure

```text
.
├── .gitignore
├── README.md
├── package.json
├── index.js
├── data/
│   └── questions.json
└── src/
    ├── colors.js
    ├── input.js
    └── quiz.js
```

### Key Files

- **`index.js`**  
  Main entry point. Loads quiz data, handles category and question count selection, and runs the quiz loop.

- **`src/quiz.js`**  
  Core quiz logic, including shuffling, scoring, progress, feedback, and results display.

- **`src/input.js`**  
  Readline-based helpers for prompts, selections, confirmations, and pause handling.

- **`src/colors.js`**  
  ANSI color utilities used to format terminal output.

- **`data/questions.json`**  
  Quiz content organized by category.

- **`package.json`**  
  Project metadata and scripts.

## Prerequisites

- **Node.js 18 or later**
- **npm** (bundled with Node.js)

## Getting Started / Installation

Clone the repository:

```bash
git clone https://github.com/Pri1me/test_app.git
cd test_app
```

Install dependencies:

```bash
npm install
```

> `npm install` is optional here because the project has no runtime dependencies, and you can skip it if you only want to run the app.

## Usage

Start the quiz:

```bash
npm start
```

Or run the entry file directly:

```bash
node index.js
```

### Available Scripts

From `package.json`:

```bash
npm start
```

Runs the quiz application:

```bash
node index.js
```

```bash
npm test
```

Runs Node’s built-in test runner (`node --test`).  
Note: this repository summary does not confirm the presence of test files, so this script may be a placeholder unless tests are added.

### Typical Flow

1. Launch the app
2. Choose a quiz category
3. Choose how many questions to answer
4. Answer each question by entering the option number
5. Review your score and any missed questions
6. Decide whether to play again

## How It Works / Data Format

The quiz reads question data from `data/questions.json` at runtime.

### Data Structure

The file is organized like this:

```json
{
  "categories": {
    "categoryId": {
      "name": "Category Name",
      "questions": [
        {
          "question": "Question text?",
          "options": ["Option A", "Option B", "Option C", "Option D"],
          "answer": 2,
          "explanation": "Optional explanation"
        }
      ]
    }
  }
}
```

### Question Fields

- **`question`** — The question text
- **`options`** — Array of multiple-choice answers
- **`answer`** — Zero-based index of the correct option
- **`explanation`** — Optional explanation shown after answering

### Runtime Behavior

- Categories are derived from the JSON data
- Questions are shuffled for each quiz session
- Answers are checked immediately
- Final results include score and a review of incorrect answers

## Extending the Quiz

This project is data-driven, so it’s easy to extend without changing the quiz logic.

### Add a New Category

1. Open `data/questions.json`
2. Add a new category under `categories`
3. Provide a `name` and `questions` array

### Add More Questions

- Add more question objects to an existing category
- Make sure each question includes:
  - `question`
  - `options`
  - `answer`
  - optional `explanation`

### Possible Enhancements

- Randomize answer option order
- Add timers for each question
- Track high scores
- Save quiz history
- Add difficulty levels
- Support free-text questions

## License

This project is licensed under the **MIT License**.
