# Copy/paste this into a fresh Codex task

You are working in the existing repository `franksfotos/nokosu-dice`.

First inspect `index.html` and read `AGENTS.md` plus every file in `docs/`. The live project is a working mobile-first HTML/CSS/JS interaction prototype, not a rules-complete game. Preserve its layout and tested touch feel.

**Current task:** prepare the visual asset pipeline and integrate the approved underwater-themed card design while improving dice presentation.

Requirements:
1. The local player's cards are face-up: values 0–7 across blue, red, yellow, purple and green, with up to 10 in a readable fan. Opponents show *only* their visible dice and a face-down card count; 3–5 players total. Up to five dice per player.
2. Cards can keep seashell/underwater ornamentation; big readable numbers. Keep the selected-card lift and the zoomed selection view on small phones.
3. Dice are DIFFERENT: no underwater ornaments, no seashells, no glue tabs, no oriented decorations. Use a clean uniform rounded die, correct pips for faces 1–6, correct opposite pairs (1/6, 2/5, 3/4), and a clear chosen/top-face value. It should read naturally at any rotation. State glow is a CSS/WebGL effect, not part of the texture.
4. Keep one-card-OR-one-die selection and confirm; normally the final die stays. No accidental browser-back gesture conflicts.
5. Use optimized reusable assets, not huge inline bitmaps or duplicated decorative elements. Prefer SVG/WebP 2D fallback; optional lightweight GLB for big interactive views. Support users with reduced motion and narrow screens.
6. Keep GitHub Pages working via root `index.html`. Don't introduce framework/build complexity unless justified.
7. Do not pretend opponent turns, following-suit or scoring are rule-complete. They are simulated until a separate rules-engine phase.

**Deliverables:** a concise implementation plan, actual maintainable code and assets, screenshots at 320/390 px phone and 1024 px tablet, tested selection/undo flows, and a short summary of remaining gaps. Start with a small, verifiable implementation slice rather than rewriting the app.

Reference art was generated during the ChatGPT design conversation. If the `assets/raw/` image files aren't present, do NOT invent them or scrape copyrighted game artwork: use the design brief and create original scalable graphics or ask for the supplied reference files. Asset filenames/paths are specified in `docs/ASSET_SPEC.md`.
