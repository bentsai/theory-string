# Theory String - Project Context

## What This Is
Online multiplayer cooperative party game. Players get secret numbers (1-100), discuss vaguely via external voice chat, arrange face-down cards in ascending order, then reveal to see if they got it right.

## Current State: MVP shipped

The core game is implemented, running, deployed. It has been used in the wild a few times.

## Tech Stack
- **Backend**: Node.js + Express + Socket.io
- **Frontend**: Vanilla HTML/CSS/JS (single-page app)
- **State**: In-memory (no database)

## File Structure
```
server/
  index.js    - Express + Socket.io server, all event handlers
  game.js     - Game state management (create, join, place, move, reveal)
  utils.js    - Code generation, shuffle

public/
  index.html  - Single HTML file with 4 screens
  css/style.css
  js/app.js   - All frontend logic + Socket.io client
```

## Game Flow
1. Landing: Enter name → Create Game or Join Game (with 4-char code)
2. Lobby: See players, host clicks "Start Round"
3. Playing: See your number, click to place card, drag to reorder any card
4. Reveal: Click "Reveal Next" to flip cards one by one
5. Result: Win/Lose screen, host can click "Play Again"

## To Run
```bash
npm start
# Open http://localhost:3000
```

## Known Issues / To Test
- [ ] Test host disconnect (should transfer host role)
- [ ] Mobile responsiveness

## Design Doc
Full design spec at: `docs/plans/2026-01-21-theory-string-mvp-design.md`

## Next Steps (if MVP works)
- Add theme/clue prompts for describing numbers
- Add multiple rounds with scoring
