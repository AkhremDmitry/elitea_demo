# 📚 Quiz CLI

An interactive command-line quiz game built with **Node.js** to help developers test and reinforce their programming knowledge — no external dependencies required!

---

## Project Overview

**Quiz CLI** is a fully interactive terminal-based quiz application written in modern JavaScript (ES Modules). Players can choose from multiple quiz categories, select how many questions to answer, and receive instant feedback with explanations after each answer.

**Key highlights:**
- 🎯 Multiple quiz categories: *JavaScript Basics*, *Node.js Fundamentals*, and *General Programming*
- 🔀 Questions are shuffled on every run for a fresh experience
- 💡 Explanations provided after each answer to reinforce learning
- 📊 Detailed results summary with a review of incorrect answers
- 🎨 Colorful terminal output using raw ANSI escape codes — zero dependencies
- ♻️ Play-again loop for continuous learning sessions

---

## Setup Instructions

### 1. Prerequisites

- **Node.js** `>= 18.0.0`
- **npm** (comes bundled with Node.js)

> Verify your Node.js version:
> ```bash
> node --version
> ```

### 2. Installation

Clone the repository and navigate into the project directory:

```bash
git clone https://github.com/AkhremDmitry/elitea_demo.git
cd elitea_demo
```

Install dependencies (none are required beyond Node.js built-ins, but run this to initialise the project):

```bash
npm install
```

### 3. Configuration

No environment variables or external configuration files are needed. The quiz questions are stored locally in `data/questions.json` and can be edited to add new categories or questions.

### 4. Running the Project

Start the quiz:

```bash
npm start
```

Or run directly with Node:

```bash
node index.js
```

Run built-in tests:

```bash
npm test
```

---

## Usage Examples

### Starting the Application

```bash
$ npm start
```

You will be greeted with the welcome banner and prompted to select a category:

```
  ╔═══════════════════════════════════════════╗
  ║                                           ║
  ║   📚 QUIZ CLI                             ║
  ║   Test your programming knowledge!        ║
  ║                                           ║
  ╚═══════════════════════════════════════════╝

Choose a category:

  1. JavaScript Basics
  2. Node.js Fundamentals
  3. General Programming

Your choice (enter number): 1
```

### Answering Questions

```
How many questions?

  1. All questions
  2. 3 questions
  3. 5 questions

Your choice (enter number): 2

[░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░] 0%
Question 1 of 3

What does '===' check for?

  1. Value only
  2. Type only
  3. Value and type
  4. Reference

Your choice (enter number): 3

✓ Correct!
💡 The strict equality operator (===) checks both value and type without coercion.
```

### Viewing Results

```
══════════════════════════════════════════════════
  📊 QUIZ RESULTS
══════════════════════════════════════════════════

  Category: JavaScript Basics
  Score: 2/3 (67%)

  👍 Good effort! Keep learning!

══════════════════════════════════════════════════

📝 Review these questions:

1. What is the output of: typeof null?
   Your answer: 'null'
   Correct: 'object'
```

### Adding Custom Questions

Edit `data/questions.json` to add your own categories or questions following this structure:

```json
{
  "categories": {
    "my_category": {
      "name": "My Custom Category",
      "questions": [
        {
          "question": "Your question here?",
          "options": ["Option A", "Option B", "Option C", "Option D"],
          "answer": 0,
          "explanation": "Why this answer is correct."
        }
      ]
    }
  }
}
```

> **Note:** `"answer"` is the **zero-based index** of the correct option in the `"options"` array.

---

## File Structure

```
elitea_demo/
│
├── data/
│   └── questions.json      # Quiz questions organized by category
│
├── src/
│   ├── quiz.js             # Quiz class: game logic, scoring, progress, results
│   ├── input.js            # CLI input helpers: select, confirm, prompt, pressEnter
│   └── colors.js           # Terminal color utilities using ANSI escape codes
│
├── index.js                # Application entry point: main loop, banner, category selection
└── package.json            # Project manifest: name, version, scripts, engine requirements
```

---

## Additional Information

### Quiz Categories

| Category | # of Questions | Topics Covered |
|---|---|---|
| JavaScript Basics | 5 | Constants, arrays, equality, types, quirks |
| Node.js Fundamentals | 5 | `fs` module, event loop, npm, `process.argv`, ES modules |
| General Programming | 5 | APIs, recursion, JSON, callbacks, version control |

### JavaScript Concepts Demonstrated

This project is intentionally written to showcase modern JavaScript and Node.js features:

- **ES Modules** (`import`/`export`) — no CommonJS `require()`
- **Async/Await & Promises** — for all user input operations
- **Classes & OOP** — the `Quiz` class with getters and methods
- **Array methods** — `map`, `filter`, `forEach`, `find`
- **Destructuring** — used throughout for clean variable assignment
- **Template literals** — for all dynamic string formatting
- **Fisher-Yates shuffle** — for randomizing questions each round
- **Error handling** — `try/catch/finally` in the main loop

### Node.js Built-in Modules Used

| Module | Purpose |
|---|---|
| `node:fs/promises` | Reading the `questions.json` data file |
| `node:readline` | Capturing interactive user input from the terminal |
| `node:url` | Resolving `__dirname` equivalent in ES Modules |
| `node:path` | Building cross-platform file paths |

### Engine Requirements

| Runtime | Minimum Version |
|---|---|
| Node.js | `>= 18.0.0` |

### License

This project is licensed under the **MIT License**.

---

> 🚀 *Keep learning, keep building!*
