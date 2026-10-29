# Codex instructions — Nokosu Dice

Read docs/PROJECT_BRIEF.md, docs/UX_DECISIONS.md, docs/ASSET_SPEC.md, docs/RULES_AND_SCOPE.md and docs/IMPLEMENTATION_PLAN.md before making changes.

## Non-negotiable
- Preserve the currently working mobile-first prototype in root `index.html`. Refactor incrementally; don't replace it with an unrelated framework or redesign.
- The main goal right now is interaction and asset quality, **not** a finished multiplayer/game-rules implementation.
- 3–5 players; the local player can see their own 0–7 card values (up to 10) and up to 5 open dice. Opponents reveal only their dice and remaining card counts, never card faces.
- A trick action is **one card OR one die**, not both.
- Keep the fan-shaped hand usable on small portrait screens; provide a full-size selection fallback. Avoid browser-back-swipe areas and use iOS safe-area insets.
- All 3D dice faces should be orientation-neutral: clean uniform material and conventional pips, **no artwork, seashells, edge ornaments, glue tabs or per-face 'up' direction**. A real die has different values on different faces; show the assigned value on the top/front-facing readable face.
- One die normally must remain unplayed (exceptions to be implemented with zero-trick-declaration rules).
- Respect accessibility, keyboard focus, reduced motion and legibility independent of colour.
- Don't claim the UX dummy is rules-complete. Mark simulated opponent turns and game logic clearly.
- Do not change GitHub Pages settings, deploy configuration, or unrelated repositories without a specific reason and authorization.

## Workflow
1. Inspect the current `index.html` and preserve working card/die selection, confirm, undo, 3/4/5-player switching and zoomed hand.
2. Make small, testable commits; prefer maintainable source/assets, keeping `index.html` as GitHub Pages entry.
3. Test at 320, 375, 390 px portrait and 768/1024 px tablet widths, plus iPad landscape.
4. Summarize changes, trade-offs, limitations, and steps to reproduce.
