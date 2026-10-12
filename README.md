# Browser Games

A collection of lightweight, self-contained games made with HTML, CSS, and JavaScript. No build tools, packages, or external assets are required.

## Games

### Memory Game

Match pairs of cards on a 4x4 or 6x6 board. The game includes a timer, move counter, star rating, keyboard controls, and saved best scores.

- Play: [memory-game.html](memory-game.html)
- Requirements: [PRD_dark_theme.md](PRD_dark_theme.md)

### Snake

Guide the snake to eat fruit and grow without hitting the walls or itself. Choose a speed, track your score and best score, and pause or restart whenever you like.

- Play: [snake-game.html](snake-game.html)
- Requirements: [PRD_snake_game.md](PRD_snake_game.md)

**Controls:** Arrow keys or WASD to move; Space or P to pause/resume. On mobile, swipe on the board or use the on-screen direction buttons.

## Run a game

Open either HTML file directly in a modern web browser. Alternatively, serve the repository locally:

```bash
python -m http.server 8000
```

Then open:

- `http://localhost:8000/memory-game.html`
- `http://localhost:8000/snake-game.html`

## Technology

- Plain HTML, CSS, and JavaScript
- No external dependencies or network access required
- Responsive layouts and browser local storage for supported high scores
