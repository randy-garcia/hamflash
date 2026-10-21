

<center><img width="624" height="1105" alt="hamflash1" src="https://github.com/user-attachments/assets/602c4664-5e7e-49ef-9eb1-326467db1497" /></center>

# Ham Radio License Flashcards & Quiz Engine

A lightweight, zero-dependency, single-file web application for studying FCC Amateur Radio License question pools (**Technician**, **General**, and **Amateur Extra**). Built for responsive mobile and desktop use, it features persistent browser storage, dual study modes (Flashcards & Quiz), full option context display, custom pool importing, and multi-device backup sync.

---

## Features

* 📇 **Flashcard Mode**: Fast card-flipping study mode. Shows the correct answer prominently on flip, with the full set of choices (distractors) displayed by default for complete context.
* 📝 **Interactive Quiz Mode**: Test mode with 4-option multiple-choice questions, instant visual feedback (correct/incorrect highlighting), live streak counter, and automatic score/mastery updates.
* ⚡ **Zero External Dependencies**: Plain HTML5, CSS3, and ES6 JavaScript inside a single standalone file. Works completely offline without external frameworks or APIs.
* 📱 **Mobile & Desktop Optimized**: Dark-mode UI with smooth 3D card flip animations, touch controls, and keyboard navigation.
* 📥 **Universal Question Importer**: Auto-parses standard NCVEC text files and multiple JSON schema formats, resolving correct answer keys (`A-D` / `0-3`) into plain text.
* 💾 **Persistent Local Storage**: Saves imported question pools, mastery stats, and card review states directly in your browser.
* 📦 **Multi-Device Backup & Restore**: Export your progress and question pools into a portable `.json` backup file to sync across machines.
* 🗑️ **Question Pool Management**: Reset study progress (`Mastered` / `Needs Review`) or wipe individual class pools independently.

---

## Getting Started

### Option 1: Direct File Usage
1. Clone or download this repository.
2. Open `index.html` in any web browser (Chrome, Safari, Firefox, Edge).

### Option 2: Host via GitHub Pages
1. Push `index.html` to the `main` branch of your GitHub repository.
2. Navigate to **Repository Settings > Pages**.
3. Select `main` branch as the source and save.
4. Access your study app from any device via the generated GitHub Pages URL.

---

## Study Modes

### 📇 Flashcard Mode
* Tap or press `Space` to flip between the question and the answer.
* The correct answer appears in blue at the top of the card back.
* The full list of choices is expanded below it (correct answer highlighted in green; wrong options dimmed).
* Click **🙈 Hide Options** / **👁️ Show All Options** on the back of any card to toggle choice visibility.
* Use **Right** / **Wrong** buttons or hotkeys to track your mastery.

### 📝 Quiz Mode
* Switch to **Quiz Mode** using the top header toggle.
* Renders questions with interactive choice buttons ($A, B, C, D$).
* Click an option to lock in your answer:
  * **Correct**: Highlighted in green, increments your current streak, marks the card as **Mastered**.
  * **Incorrect**: Highlighted in red, reveals the correct option in green, resets streak to `0`, marks the card as **Needs Review**.

---

## Keyboard Shortcuts

| Key | Action |
| --- | --- |
| `Space` | Flip card (Flashcard Mode) |
| `→` (Right Arrow) | Next Card / Question |
| `←` (Left Arrow) | Previous Card / Question |
| `1` or `M` | Mark as **Right / Mastered** (Flashcard Mode) |
| `2` or `R` | Mark as **Wrong / Needs Review** (Flashcard Mode) |

---

## Question Pool Formats & Importing

Click **Import Pool** inside the app to load pool files for the active license class (`Technician`, `General`, or `Extra`). You can drag and drop `.json` or `.txt` files or paste text directly into the import dialog.

### Supported JSON Schemas

The import engine handles all common ham radio question formats:

#### Format A: Explicit Answer Array
```json
[
  {
    "id": "T1A01",
    "correct": 2,
    "refs": "[97.1]",
    "question": "Which of the following is part of the Basis and Purpose of the Amateur Radio Service?",
    "answers": [
      "Providing personal radio communications for as many citizens as possible",
      "Providing communications for international contesting",
      "Advancing skills in the technical and communication phases of the radio art",
      "All these choices are correct"
    ],
    "correct_letter": "C"
  }
]
