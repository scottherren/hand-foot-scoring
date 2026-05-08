# ♠ Hand & Foot IndyBlue Score Keeper

A mobile-first static web app for scoring a 4-hand **Hand & Foot** game. The app runs entirely in the browser, supports installable PWA behavior, and now uses **JSON save/load** so full game state can move between devices or browsers.

## Current highlights

- 4-hand progressive rules with per-hand draw count, meld minimum, go-out bonus, and clean/dirty requirements
- Tracks:
  - Red 3s
  - Clean books
  - Dirty books
  - Book of 7s
  - Book of Wilds
  - Meld/card points
- Enforces go-out requirements before a player can be marked out
- JSON `Save Game` / `Load Game` support for full game state
- In-browser persistence with `localStorage`
- Undo within the active hand
- Hand history with expandable details and edit-hand flow
- Rules reference with book scoring and individual card values
- Light / dark mode
- Works for 2–6 players or teams

## Scoring reference

### Per-hand requirements

| Hand | Draw | Meld Min | Clean Req | Dirty Req | Go-Out Bonus |
| --- | --- | --- | --- | --- | --- |
| 1 | 3 | 90 | 3 | 3 | +300 |
| 2 | 4 | 120 | 4 | 4 | +400 |
| 3 | 5 | 150 | 5 | 5 | +500 |
| 4 | 6 | 180 | 6 | 6 | +600 |

### Books and bonuses

| Item | Points |
| --- | --- |
| Red 3 | +100 each |
| Dirty Book | +300 each |
| Clean Book | +500 each |
| Book of 7s | +1,000 each |
| Book of Wilds / 2s | +1,500 each |

### Individual card values

These count **for** you when melded and **against** you if they remain in your Hand or Foot at the end of play.

| Cards | Points |
| --- | --- |
| Jokers | 50 each |
| Twos & Aces | 20 each |
| Eight through King | 10 each |
| Four through Seven | 5 each |
| Black Threes | 5 each |

## Local testing

This is a static app, so the easiest way to test locally is to run a simple server from the repo root:

```bash
python3 -m http.server 8000
```

Then open:

```text
http://localhost:8000/public/
```

### Recommended pre-push check

- Start a new game
- Enter a few scores
- Mark a player as going out
- Save a hand
- Save Game to JSON
- Refresh the page
- Load Game from the saved JSON
- Confirm history, active hand, player names, and theme are restored correctly

## VS Code preview

If you use **Live Preview** in VS Code:

- open the repo root as the workspace
- open `public/index.html`
- run `Live Preview: Show Preview`

## Project structure

```text
hand-foot-scoring/
├── README.md
├── docs/
└── public/
    ├── index.html
    └── assets/
        └── hnf-logo.png
```

## Data and privacy

- Game data is stored locally in browser `localStorage`
- `Save Game` exports the full state as JSON
- Nothing is sent to a server

## Notes

- The app is intentionally kept as a single-file HTML/JS/CSS app under `public/index.html`
- The setup logo is loaded from `public/assets/hnf-logo.png`
- The PWA cache includes the main app route and setup logo asset

## License

MIT
