# NULLRELAY Tactics game design

## First weekly build

Vale, a lone station intrusion tech, enters NULLRELAY_091 after security personnel have been Reclaimed. Clear the four hostiles and keep Vale alive. The prototype reuses the 16×16 deck layout from [hello-world-game](https://github.com/4rg43n/hello-world-game).

The top-down view shows the floor plan and a subtle tile grid. The minimap mirrors the deck and current contacts. Hostile contacts appear when Vale has line of sight. The station panel shows hostiles killed and remaining. The operator panel shows integrity, equipped weapon, and armor. Comms reports combat and crew dialogue.

## Turn rules

1. Vale moves one cardinal tile, bumps an adjacent character, shoots a valid target, or passes. A crew bump gives a short bark. A hostile bump deals melee damage. Both spend the turn and leave Vale in place.
2. Crew stay on their tiles. Each living Reclaimed checks for melee first and then a legal shot if armed. If neither is available, it moves one cardinal tile along a shortest walk toward Vale and checks for attacks again. If it cannot move or attack, it passes.
3. Vale acts again unless the deck is clear or Vale is down. Restart restores the starting state.

Shots require a living hostile, Manhattan range, and a clear line between tile centers. Bulkheads, including their corners, block fire. Actors block movement. Bumping a wall or attempting an invalid shot leaves the turn available.

## Loadout and scope

Vale starts with 24 integrity, a six-tile arc pistol that deals four damage, a three-damage melee strike, and a mesh jacket that absorbs one damage per hit. The deck has two stationary crew, two melee Reclaimed, and two Reclaimed armed with four-tile carbines.

The first build is a single authored encounter with fixed equipment and a restart. Loot, inventory, hacking actions, progression, and additional decks are outside this milestone.
