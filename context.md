# Project Context

## What this repo does
This repository contains a browser-based Memory (Concentration) card game built with plain HTML, CSS, and JavaScript. The game lets a user flip cards, match pairs, track moves, measure elapsed time, rate performance, and save best scores in local storage.

The app supports two board sizes:
- 4x4 grid
- 6x6 grid

It is designed to run directly in a browser with no external dependencies or framework setup.

## What the project stands for
The name `memory-game-GHCP` appears to be a repo naming pattern rather than a formal product acronym. In this context, `GHCP` most likely refers to GitHub Copilot-related usage or a GitHub Copilot practice environment, while the actual product is simply a memory game.

## Key files
- `memory-game.html` — main application file containing HTML, CSS, and JavaScript for the game
- `README.md` — overview and usage instructions
- `context.md` — project context summary

## How it works
The game:
- shuffles a set of emoji symbols
- creates a grid of face-down cards
- tracks player moves and timer
- detects matching pairs
- updates the star rating based on performance
- announces a win and stores high scores locally in the browser

## Technical stack
- HTML for structure
- CSS for styling and responsive layout
- JavaScript for game logic and DOM behavior
- Browser localStorage for persistent best scores

## How to run it
Open `memory-game.html` directly in a browser, or serve the project locally with:

```bash
python -m http.server 8000
```

Then visit:

```text
http://localhost:8000/memory-game.html
```

## Short summary
This repo is a small, self-contained web game for matching pairs of cards, meant to be easy to run, easy to understand, and useful as a sample front-end project.
