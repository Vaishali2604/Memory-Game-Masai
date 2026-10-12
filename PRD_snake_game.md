# PRD: Snake Game

## 1. Overview
This document describes a standalone Snake game for this repository. The game will be implemented in a single HTML file with embedded CSS and JavaScript, following the existing no-dependency browser game approach.

## 2. Problem Statement
The repository currently offers a memory matching game. Players looking for another familiar, quick-to-play arcade game should be able to play Snake in the browser without installing software, downloading assets, or setting up a server.

## 3. Goal
Deliver a responsive, accessible, single-file Snake game that works when opened directly in a modern browser and preserves scores locally when browser storage is available.

## 4. Target Users
- Casual players looking for a short, familiar game
- Players using desktop keyboard controls or a mobile touch screen
- Users who want a lightweight game without accounts or external dependencies

## 5. User Stories
- As a player, I can start, pause, resume, and restart a game.
- As a player, I can steer the snake with arrow keys or WASD.
- As a mobile player, I can steer with touch gestures or on-screen direction buttons.
- As a player, I can see my current score and personal best.
- As a player, I can choose a slower, normal, or faster game speed.
- As a player, I can understand the game state and controls using accessible text and keyboard navigation.

## 6. Functional Requirements
### 6.1 Gameplay
- Show a grid-based board with a snake and food.
- The snake moves continuously in the current direction while the game is running.
- Eating food grows the snake and increases the score by 10 points.
- Hitting a wall or the snake's own body ends the game.
- The player wins if the snake fills every available board cell.
- The snake cannot reverse directly into itself.

### 6.2 Game controls
- Start from a ready state using the Start button or a direction input.
- Pause or resume using the Space key, P key, or the main game button.
- Restart the game at any time using the Restart button.
- Arrow keys and WASD control direction on desktop.
- On mobile, swipe on the board or use the on-screen directional buttons.
- Speed options are Slow, Normal, and Fast; changing speed takes effect during play.

### 6.3 Score and persistence
- Display current score and best score throughout play.
- Award 10 points for each food item.
- Store the best score in browser localStorage when available.
- If browser storage is unavailable, the game remains playable and communicates that the best score will not persist.

## 7. User Experience and Accessibility
- Provide clear Ready, Paused, Game Over, and Win states.
- Ensure controls are keyboard accessible, visibly focused, and have accessible names.
- Announce score milestones and game end through a polite live region.
- Prevent page scrolling when arrow keys or Space are used as game controls.
- Keep the board responsive and square on small and large screens.
- Respect the user's reduced-motion preference.
- Use adequate text contrast and do not rely on color alone for instructions or game state.

## 8. Technical Requirements
- Deliver the game in `snake-game.html` with inline CSS and JavaScript.
- Use no external dependencies, fonts, images, or network services.
- Use Canvas for drawing the board, snake, and food, scaling for high-density displays.
- Keep game state and rendering logic within the HTML file.
- Use a dedicated localStorage key (`snakeGameBestScore`) separate from other games.
- Support opening the HTML file directly in a modern browser.

## 9. Non-Goals
- Online multiplayer, accounts, leaderboards, or cloud synchronization
- External sound, image, or font assets
- Custom board sizes, obstacles, portals, or themed skins
- Changes to the existing Memory Game

## 10. Acceptance Criteria
1. Opening `snake-game.html` starts in a clear Ready state without a build step or internet access.
2. Start, pause, resume, and restart controls behave as described.
3. Arrow keys and WASD change direction; direct reversal is ignored.
4. Touch swipe and mobile direction buttons can steer the snake.
5. Eating food grows the snake and adds 10 points.
6. Wall and self collisions end the game; filling the board produces a win state.
7. The best score is retained across reloads when localStorage is available.
8. Choosing a speed changes the movement interval without resetting the game.
9. The UI remains usable at mobile and desktop viewport sizes, including keyboard focus and status announcements.
10. The memory game and its existing files remain unchanged.

## 11. Risks and Mitigations
- **Risk: rapid inputs cause impossible reversal or inconsistent movement.** Queue one direction per simulation step and reject direct reversal.
- **Risk: browser tab throttling affects the animation loop.** Cap elapsed frame time to avoid large catch-up jumps.
- **Risk: localStorage is unavailable.** Fall back to an in-memory best score and announce that it cannot persist.
- **Risk: high-density displays blur the board.** Scale the canvas backing buffer using the device pixel ratio.

## 12. Definition of Done
- `snake-game.html` and this PRD are present in the repository.
- The game runs locally by opening the HTML file.
- The functional and acceptance requirements above are met without altering the Memory Game.
