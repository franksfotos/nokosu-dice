# Codex task — test and refine the live WebP prototype

Repository: `franksfotos/nokosu-dice`. First inspect root `index.html`, `AGENTS.md`, `assets/README.md` and the design/UX/rules notes in `docs/`.

**What is already done (29 Oct 2026):**
- GitHub Pages entry point: `index.html`.
- All **40 image-generated WebP card fronts** and one WebP card back are checked in under `assets/cards/`.
- **29 WebP dice** under `assets/dice/`; `yellow-4.svg` is used as a deliberate fallback because its WebP was empty.
- Cards/dice are now referenced as actual image assets in the fan, selection zoom, trick and opponents' displays. Old SVG variations remain in the repository but aren't the preferred card visuals.
- No full game engine or multiplayer is implemented; opponent turns are simulated.

**Next task — improve and verify, do NOT rewrite:**
1. Run the current site locally and visually inspect it at 320/375/390px portrait and 768/1024px landscape.
2. Ensure 10 overlapping, almost-square WebP cards remain **readable and easy to select**. Fix fan geometry only when needed, preserving the already appreciated touch behaviour.
3. Confirm opponent card fronts never leak, up to 5 dice are visible per player, and tap selection/confirmation/undo/zoom works.
4. Produce a real, nonempty `assets/dice/yellow-4.webp` from the existing SVG, then switch `dieAsset()` back to a uniform WebP path.
5. Confirm the selected die is visually distinguishable at small sizes, with CSS glow and accessible labels.
6. Keep layout safe from iOS browser back gestures and not dependent on hover.
7. Optionally explore a true small glTF/GLB 3D die with six correct 1–6 faces, but keep a fast 2D fallback. Absolutely **no ornamentation or fold tabs** on dice.
8. Commit tested changes and summarize deviations and remaining UX issues.

Do not add an unnecessary framework/backend or claim full Nokosu Dice gameplay. Retain GitHub Pages deployment through root `index.html`.
