# Nokosu Dice — Projektbriefing

## Ziel
Ein hochwertiger, browserbasierter **Mobile-first-Prototyp** des Stichspiels Nokosu Dice für Smartphone (Hochformat) und iPad (Querformat), getestet über GitHub Pages.

## Stand (29.10.2026)
- Repo: https://github.com/franksfotos/nokosu-dice
- Root-`index.html`: Ocean-Edition-Klickdummy mit externen WebP-Bildressourcen.
- **40 Karten-WebPs** (0–7 in fünf Farben) + **1 WebP-Rückseite** sind im Repo; bereits in Kartenfächer, Stichfeld, vergrößerter Auswahl und verdeckten Gegnerkarten integriert.
- **29 Würfel-WebPs** (fünf Farben, Augenwerte 1–6) integriert; der gelbe Vierer verwendet vorübergehend das vorhandene SVG als Fallback. Kein leeres WebP mehr im Repo.
- Die bisherigen simplen SVG-Grafiken bleiben als Alternativen verfügbar, sie sind nicht mehr die primären Kartenassets.
- Interaktion: Antippen, Selektion, Ausspielen, Undo, 3/4/5-Spieler-Wechsel und vergrößerte Auswahl.
- Gegnerzug-Logik simuliert; **keine** vollständige Spielregel-Engine, kein Multiplayer.
- Browser-Sichtprüfung auf realen iPhones/iPads nach diesem Assetwechsel noch ausstehend.

## Produktanforderungen
- 3 bis 5 Spieler insgesamt, darunter lokaler Spieler.
- Eigene Hand: bis zu 10 sichtbare Karten, fünf Farben, Zahlen 0–7.
- Eigene Würfel: bis zu 5 sichtbar, jeweils Farbe + Augenwert.
- Bis zu 4 Gegner: Würfel offen, Karten **nur als Anzahl/verdeckte Symbole** sichtbar.
- Mitte: laufender Stich, Trumpf-Anzeiger und klare Zug-/Phaseninformation.
- Pro Zug **Karte ODER Würfel**, bestätigen und im UX-Dummy zurücknehmen.
- Stabile, zugängliche Bedienung ohne versehentliche iOS-Back-Gesten.

## Designentscheidungen
**Karten:** dekorativer Ocean-/Muschel-Stil ist erwünscht; Zahlen und Farbe müssen insbesondere im Fächer eindeutig lesbar sein. Die gelieferten Bildassets sind fast quadratisch und werden nicht verzerrt.
**Würfel:** keine Muscheln, Ranken, orientierten Aufdrucke oder Klebelaschen. Einheitliche, abgerundete, leicht plastische Würfel mit gewöhnlichen Augen. Rotationsneutral gestaltete Flächen.
**Interaktion:** Optik darf die bewährte Touch-Bedienung nicht verschlechtern.

## Nicht im aktuellen Scope
Backend, Accounts, Lobby, Persistenz, Multiplayer-Synchronisation, vollständige Stichauswertung und vollständige Regellogik.
