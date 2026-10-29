# Codex-Umsetzungsplan

## P0 — Bestehenden Klickdummy sichern
- Root-`index.html` prüfen, Smoke-Test durchführen und baseline Screenshot erzeugen.
- Bestehende Events und Selektion unverändert funktionsfähig lassen.
- Keine Big-Bang-Migration und kein neues Backend.

## P1 — Asset-Contract & Integration
- `color` + `value` als stabile IDs. Zentrale `getCardAsset(color,value)` / `getDieAsset(color,value)` Funktion.
- Ein 2D-Asset-Fallback mit CSS, wenn ein Bild fehlt oder nicht geladen wird.
- Kartenfront, Kartenrückseite, ausgewählte Karte und Würfel in allen UI-Orten konsistent darstellen.
- Bei Karten ggf. zuerst **eine** Farbe und Werte 0–7 integrieren, dann auf 40 ausweiten.

## P2 — Karten-Fächer-Qualität
- 10 Karten bei 320/375/390 px prüfen.
- Enge Überlappung → großflächiges Auswahl-Overlay und focus/hover/selected States.
- Visuelle Erweiterung nicht gegen bisher gute Touch-Bedienung austauschen.

## P3 — Würfel v1 (2D)
- Gleichmäßige einfache Würfel-Assets, ohne jegliche Dekoration und ohne Faltlaschen.
- 5 Farben × 6 Augenwerte, standardkonforme Pip-Muster.
- Auf Gegner-Auslagen (bis zu 5), eigener Auslage, Trumpf und Stichfeld testen.
- Selection-Glow unabhängig vom Asset zeichnen.

## P4 — Würfel v2 (optional 3D)
- Kleines, wiederverwendbares glTF/`GLB`-Modell mit Bevels, sechs Wertflächen und korrekten Gegenüberstellungen.
- Für konkreten Wert eine feste, lesbare Orientierung ausrichten; Drehen nur zur Interaktion, nicht zur stillschweigenden Wertänderung.
- Performance auf realem iPhone/iPad testen; 2D-Fallback obligatorisch.

## P5 — Regeln (separates Projekt)
- Datenmodell, Edition/Spielerzahl, Austeilen, Drafting, Bedienpflicht, Trumpf, Zugfolge, Stichauswertung, Stichvorhersage, Wertung, Multiplayer.
- Regeltests gegen offizielle Beispiele, dann erst UX-Demo auf Echtlogik umstellen.

## Definition of Done für die nächste Codex-Iteration
- Keine regressiven UI- oder Bedienfehler bei 3, 4 und 5 Spielern.
- 40 Karten-Farben/Werte als Schema abgedeckt und korrekt adressierbar.
- Würfeldarstellung hat **keine** Ornamente oder Klebelaschen, die Spielwerte sind klar.
- Alle aktuellen Aktionen bleiben benutzbar: Auswahl, Ausspielen, Undo, Vergrößerungs-Overlay, Neue Hand.
- Läuft lokal und als GitHub Pages Static Site ohne verpflichtende Drittservices.
- Dokumentierte Tests und klare Änderungsübersicht.
