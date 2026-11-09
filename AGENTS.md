# Working on NULLRELAY Tactics

Ship one small playable improvement per week. Use [GDD.md](GDD.md) for gameplay scope and [ARCHITECTURE.md](ARCHITECTURE.md) for code and verification notes. Update the relevant document when behavior or structure changes.

- Keep the game runnable by opening `index.html` in a browser.
- Route player input through `takeAction()`. Keep draw code separate from rules and share movement, range, and line-of-sight rules between the player and NPCs.
- Treat the original NULLRELAY_091 deck as the setting reference. Keep prototype additions small and preserve the station's visual vocabulary.
- Play the changed behavior through the actual controls and check that a full run can reach an end state and restart.
