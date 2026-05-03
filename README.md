# ♠ Hand & Foot Score Keeper

A mobile-first Progressive Web App (PWA) for scoring **Progressive Hand and Foot** — a 4-hand card game variant. No installation required; runs entirely in the browser and can be added to your home screen.

---

## Features

- **4-hand progressive rules** — each hand has its own draw count, meld minimum, go-out bonus, and required book counts
- **All book types tracked** — Clean, Dirty, Book of 7s, and Book of Wilds/2s
- **Go-out requirement enforcement** — the Go Out button is locked until a player meets the clean & dirty book requirements for that hand
- **Live leaderboard** — running totals update after every tap
- **Round summary** after each hand with per-player deltas and running totals
- **History tab** — expandable detail per hand plus cumulative subtotals matching the paper scoring sheet
- **Rules tab** — full per-hand reference table and scoring values, always one tap away
- **Undo** — up to 60 actions undoable within a hand
- **Edit / Delete** last hand from history
- **Export** game data as JSON or CSV
- **PWA** — installable on iOS and Android home screen, works offline via Service Worker
- **2–6 players or teams**

---

## Scoring Rules

### Per-Hand Requirements

| Hand | Draw | Meld Min | Clean Req | Dirty Req | Go-Out Bonus |
|------|------|----------|-----------|-----------|-------------|
| 1st  | 3    | 90 pts   | 3         | 3         | +300        |
| 2nd  | 4    | 120 pts  | 4         | 4         | +400        |
| 3rd  | 5    | 150 pts  | 5         | 5         | +500        |
| 4th  | 6    | 180 pts  | 6         | 6         | +600        |

### Book & Card Values

| Item                  | Points       |
|-----------------------|-------------|
| Red 3                 | +100 each   |
| Dirty Book            | +300 each   |
| Clean Book            | +500 each   |
| Book of 7s            | +1,000 each |
| Book of Wilds / 2s    | +1,500 each |
| Points of all cards   | Face value  |
| Going out bonus       | Per hand (see above) |

> **Wilds** are Jokers and 2s. A **Dirty book** contains at least one wild. A **Clean book** is 7 natural cards of the same rank. A **Book of 7s** is 7 cards of the "7" rank. A **Book of Wilds** is made entirely of wild cards.

---

## Getting Started

### Play instantly in a browser

Just open `index.html` in any modern browser — no build step, no dependencies.

```bash
# Clone the repo
git clone https://github.com/your-username/hand-foot-score.git
cd hand-foot-score

# Open directly
open index.html
# or serve locally
npx serve .
```

### Install as a PWA (phone / tablet)

**iOS (Safari):** Open the app → tap the Share button → "Add to Home Screen"

**Android (Chrome):** Open the app → tap the menu (⋮) → "Add to Home Screen" / "Install App"

Once installed the app works fully offline.

---

## Project Structure

```
hand-foot-score/
├── index.html               # Entire app — single self-contained file
├── handfootscoringrules.pdf # Source scoring rules reference
├── handfootscoringsheet.pdf # Paper score sheet (4-hand layout)
└── README.md
```

The app is intentionally a **single HTML file** with no external dependencies, making it trivial to host anywhere (GitHub Pages, Netlify, a USB drive, etc.).

---

## Hosting on GitHub Pages

1. Push the repo to GitHub
2. Go to **Settings → Pages**
3. Set source to `main` branch, root `/`
4. Your app will be live at `https://your-username.github.io/hand-foot-score/`

---

## Local Development

No build tools required. Edit `index.html` directly. For a live-reload workflow:

```bash
npx serve .
# or
python3 -m http.server 8080
```

---

## Data & Privacy

All game data is stored locally in `localStorage` — nothing is sent to any server. Use the **Export JSON** or **Export CSV** buttons in the Rules tab to save a copy of your scores.

---

## License

MIT — free to use, modify, and share.
