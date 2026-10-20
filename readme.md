# Ham Radio License Flashcards (vibe coded with Gemini)

A lightweight, zero-dependency, single-file web application for studying FCC Amateur Radio License question pools (**Technician**, **General**, and **Amateur Extra**). Built for responsive mobile and desktop use, it features local browser storage, interactive card flipping, keyboard/touch navigation, custom question pool importing, and progress export/restore capabilities.


<img width="624" height="1105" alt="hamflash1" src="https://github.com/user-attachments/assets/602c4664-5e7e-49ef-9eb1-326467db1497" />

---

## Features

* ⚡ **Zero External Dependencies**: Standard HTML5, CSS3, and ES6 JavaScript wrapped into a standalone file. Operates completely offline without external APIs or web frameworks.
* 📱 **Mobile & Desktop Optimized**: Responsive dark-mode interface with card flip animations and touch-swipe gestures for mobile study.
* 📥 **Universal Question Importer**: Automatically parses official NCVEC text pool files as well as multiple standard JSON schema formats.
* 💾 **Persistent Browser Storage**: Automatically saves imported question pools, mastery stats, and card review states to browser `localStorage`.
* 📦 **Multi-Device Backup & Sync**: Export complete progress and pool state to a JSON backup file to transfer study data seamlessly across devices.
* ⌨️ **Keyboard Navigation**: Designed for rapid desktop flashcard repetition.

---

## Getting Started

### Option 1: Direct File Usage
1. Clone or download this repository.
2. Open `index.html` directly in any web browser (Safari, Chrome, Firefox, Edge).

### Option 2: Host via GitHub Pages
1. Push `index.html` to the `main` branch of your repository.
2. Enable **GitHub Pages** under **Repository Settings > Pages**.
3. Access your study app from any mobile or desktop browser via the generated URL.

---

## Keyboard Shortcuts

| Key | Action |
| --- | --- |
| `Space` | Flip card (Toggle Question / Answer) |
| `→` (Right Arrow) | Advance to Next Card |
| `←` (Left Arrow) | Go to Previous Card |
| `1` or `M` | Mark Card as **Right / Mastered** |
| `2` or `R` | Mark Card as **Wrong / Needs Review** |

---

## Question Pool Formats & Importing

Click **Import Pool** inside the app to load official NCVEC text files or JSON arrays for your desired license class. The importer automatically resolves correct answer letters (`A`, `B`, `C`, `D` or `0`, `1`, `2`, `3`) to display the explicit answer text on the back of the flashcard.

### Supported JSON Schemas

The parser natively handles all common amateur radio JSON schemas, including:

#### Format A: Explicit Answer Array

works well with the question pool published by @russolsen   https://github.com/russolsen/ham_radio_question_pool/tree/main
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
