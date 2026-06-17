# 🏋️ 21 Days Fitness Challenge 2.0

A gamified internal wellness platform with cognitive mini-games, a live leaderboard, and a 21-day progression system — built to drive team engagement and friendly competition.

---

## 📸 What It Does

Employees log in, pick from a set of cognitive games, play daily, and earn scores tracked on a shared leaderboard. New games unlock weekly over the 21-day challenge period, keeping participation fresh.

---

## ✨ Features

- 🔐 **Login screen** — name + team/department selection
- 🎮 **Game lobby** — card grid with difficulty badges and personal best scores
- 📅 **Weekly game unlocks** — games released progressively over 3 weeks
- 🚨 **Anti-cheat system** — focus-loss overlay triggers if the user switches tabs mid-game
- 🏆 **Live leaderboard** — individual and team rankings, toggled with one click
- 🎉 **Result modal** — score summary, time taken, violations count after each game
- 🔔 **Toast notifications** — for streaks, unlocks, and milestones
- 🌑 **Dark neon design** — Syne display font, DM Mono, lime/purple accent palette
- 💾 **Progress persistence** — scores and streaks saved via Google Sheets backend

---

## 🎮 Games

| Game | Icon | Difficulty | Description |
|---|---|---|---|
| **Sudoku** | 🔢 | Medium | Classic 9×9 grid puzzle |
| **Crossword** | ✏️ | Hard | Newspaper-style clue solving |
| **Word Scramble** | 🔤 | Easy | Unscramble letters to find the hidden word |
| **Mind Game** | 🧩 | Hard | 30 cards, 40 clicks — emoji memory match |
| **Math Sprint** | ➗ | Medium | Rapid-fire arithmetic under the clock |

---

## 🛠️ Tech Stack

| Layer | Technology |
|---|---|
| Frontend | Vanilla HTML, CSS, JavaScript |
| Backend | Google Apps Script (scores + leaderboard) |
| Database | Google Sheets |
| Fonts | Syne, DM Mono, Instrument Sans (Google Fonts) |

---

## ⚙️ Setup

1. **Create a Google Sheet** with the following sheets:
   - `Users` — id, name, dept, streak
   - `Scores` — user_id, game_id, score, time, violations, timestamp
   - `Progress` — user_id, game_id, best_score

2. **Deploy a Google Apps Script** as a Web App handling these actions:
   - `login` — look up or create a user
   - `saveScore` — write a game result
   - `getProgress` — fetch a user's best scores
   - `getLeaderboard` — return ranked scores

3. **Update the Apps Script URL** in the HTML:
   ```js
   const SHEETS_URL = "https://script.google.com/macros/s/YOUR_SCRIPT_ID/exec";
   ```

4. Open `index.html` in any browser — share the link with the team.

---

## 🔒 Anti-Cheat

The platform detects tab switching and window blur during active gameplay. A full-screen overlay with a "Focus Lost!" warning appears, and the violation is recorded alongside the final score — so scores are fairly comparable across participants.

---

## 📁 File Structure

```
21-days-fitness-challenge/
└── index.html     ← entire app in one file
```

---

## 💡 Use Case

HR and culture teams use this to:
- Drive daily engagement during the 21-day challenge window
- Create friendly competition between departments via the leaderboard
- Encourage cognitive wellness — focus, memory, and quick thinking
- Track participation without any additional tooling

---

*Built for internal use · Rachit Tiwari*
