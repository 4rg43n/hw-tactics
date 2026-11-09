# Architecture

## Runtime

`index.html` contains the markup, styles, and script so the game can run directly from disk. Canvas draws the tactical grid and minimap. Ordinary HTML displays controls, gear, station counters, and comms. The prototype has no dependencies or build step.

## State and rules

The deck is a row-major array of strings. Coordinates are zero-based tile positions, with x increasing rightward and y increasing downward. Zero marks floor and the remaining digits identify bulkheads. `newGame()` creates the player, crew, enemies, round number, status, and recent events.

`takeAction()` is the rules entry point. It validates the player input, applies accepted actions, and runs `finishTurn()` synchronously. Rejected actions return a message. The enemy phase runs in spawn order, skips defeated enemies, and stops if Vale falls. Enemy pursuit uses breadth-first search around bulkheads and occupied cells. Ranged attacks share the same grid traversal for line of sight.

The browser's `act()` hands controls to the rules, updates the HUD, and briefly displays attack effects. The effect timer only clears drawing data. Restart recreates state and cancels any pending effect timer. Kill counts derive from enemy health, and rendering never advances a turn.

## Verification

Open the game and check a wall bump, an empty-tile step, a crew bark, an adjacent strike, a legal shot, a blocked or out-of-range shot, and Pass. Confirm that NPCs respond only to accepted actions and that both end states disable actions until Restart. Check the HUD and minimap against the main view.
