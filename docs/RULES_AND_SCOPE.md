# Rules vs. UX simulation — wichtig

## Gegenwärtiger Stand
Die `index.html` ist ein **Klickdummy**. Gegnerzüge sind simuliert; aktuelle Ausspielbarkeit, Stichgewinner, Punkte und Trumpf sind nicht vollständig regelkonform. Nicht als fertiges Spiel ausgeben.

## Für spätere echte Regellogik zu berücksichtigen
- Nokosu Dice ist ein Stichspiel für **3–5** Personen.
- Karten und Würfel derselben Farbe/Zahl haben denselben Spielwert.
- Pro Stich spielt jeder genau **eine Karte oder einen Würfel**.
- Gegnerwürfel sind offen; Karten bleiben verdeckt.
- Der zentrale Restwürfel legt Trumpffarbe und Trumpfzahl fest.
- Eine Karte / ein Würfel ist Trumpf, wenn **Farbe oder Zahl** zum Trumpf-Indikator passt. Trümpfe bilden ihre eigene Farbe bezüglich Bedienpflicht. Genaue Rangfolge und Gleichstand siehe Originalregeln.
- Der letzte reguläre Würfel verbleibt normalerweise bei jedem Spieler als Vorhersage der gewonnenen Stiche; Sonderregel für die `zero-trick`-Ansage separat modellieren.
- Eine volle Standardrunde umfasst abhängig von der Edition/Konfiguration bis zu zehn Karten und mehrere offene Würfel pro Spieler; 3/4/5-Spieler-Aufbau jeweils aus der offiziellen Regel übernehmen, nicht aus den momentan festen Demodaten.
- Bei einer tatsächlichen Implementierung zuerst `GameState`, `legalMoves()`, `resolveTrick()`, `scoreRound()` und deterministische Tests bauen. Spezialfälle der Edition dokumentieren.

## Quellen zur Prüfung der späteren Engine
- Engames-Spielvorstellung (Herausgeber, 2023): https://note.com/engames/n/nd55c36b342ff?hl=en
- Englischsprachiges Regel-PDF: https://tesera.ru/images/items/2364266/NokosuDice_rules_EN.pdf
- BoardGameGeek-Verweis auf offizielles Regelblatt: https://boardgamegeek.com/filepage/192096/nokosu-dice-rule-sheet-english

**Bitte Regelvarianten/Editionen vor einer produktiven Engine gegen die tatsächlich benutzte Ausgabe validieren.** Diese Datei ersetzt keine offizielle Regel.
