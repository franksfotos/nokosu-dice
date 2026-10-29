# Nokosu Dice — WebP assets (current state)

The Ocean Edition prototype in root `index.html` now uses the **original cropped card designs**, rather than the simplified replacement SVG visuals.

## Available assets
- `assets/cards/{blue,red,yellow,purple,green}-{0..7}.webp`: **40 image-generated card faces**.
- `assets/cards/back.webp`: the card-back artwork.
- `assets/dice/{color}-{1..6}.webp`: **29 clean dice images**; yellow-4 is the one exception.
- `assets/dice/yellow-4.svg`: working fallback for the yellow die with four pips. Its original WebP export was empty/corrupt and was deliberately removed.
- Existing SVG card and dice assets are retained as a lightweight fallback/alternative set.

## Integration
- Hand-card fan, trick cards, magnified picker and opponents' card backs load the WebP assets.
- Dice load WebP except the yellow four, which loads SVG.
- Source card art is roughly square; it must not be stretched vertically. Cards are displayed at their natural proportions with `object-fit: contain`.
- CSS controls selection highlights, touch targets and stacking; no decoration is baked into the dice.

## Follow-up
1. Verify on iPhone and iPad that ten overlapped cards remain legible and individually tappable.
2. Render a **valid** `assets/dice/yellow-4.webp` from the existing `yellow-4.svg` (the source SVG is present), then remove the special case in `dieAsset()`.
3. Optionally reduce duplicated fallback assets after final mobile testing.
4. Keep all current selection, undo, enlarged picker and 3/4/5-player functions.

This is an interaction prototype with simulated opponent turns, not a rules-complete game.
