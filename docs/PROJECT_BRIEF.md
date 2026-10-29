# Nokosu Dice — Projektbriefing

## Ziel
Ein hochwertiger, browserbasierter **Mobile-first-Prototyp** des Stichspiels Nokosu Dice, dessen Touch-Bedienung auf Smartphone (Hochformat) und iPad (Querformat) Spaß macht. GitHub Pages ist das einfache HTTPS-Testhosting.

## Stand (29.10.2026)
- Repo: https://github.com/franksfotos/nokosu-dice
- Root-`index.html`: bereits spielbarer Ocean-Edition-Klickdummy (CSS/JS in einer Datei), live auf GitHub Pages, sofern Pages für `main` `/(root)` aktiviert ist.
- Auf dem Handy funktionierende Elemente: Kartenfächer, Würfelauswahl, Hervorhebung, Ausspielen, Undo, 3/4/5-Spieler-Umschaltung und vergrößerte Kartenauswahl.
- Gegenspieler simuliert; **keine** vollständige Spielregel-Engine, kein Multiplayer.
- Visuelle Richtung: leuchtendes Unterwasser-Blau, weiche Panels, dezente Blasen, hochwertige Karten. Aktueller Kartenentwurf ausdrücklich positiv bewertet.

## Produktanforderungen
- 3 bis 5 Spieler insgesamt, darunter lokaler Spieler.
- Eigene Hand: bis zu 10 offene Karten, Farben Blau/Rot/Gelb/Lila/Grün, Zahlen 0–7.
- Eigene Würfel: bis zu 5 sichtbare Würfel, jeweils Farbe + Wert.
- Bis zu 4 Gegner: Würfel offen, Karten **nur als Anzahl/verdecktes Symbol** sichtbar.
- Mitte: laufender Stich, Trumpf-Anzeiger und klare Zug-/Phaseninformation.
- Tap auf eine Karte **oder** einen Würfel → selektiert; eindeutiger Button zum Ausspielen; rückgängig möglich.
- Stabile, zugängliche Bedienung ohne versehentliche Back-Gesten, besonders auf iOS Safari.

## Designentscheidungen
**Karten:** dekorativer Ocean-/Muschel-Stil ist erwünscht. Zahlen und Farbe sind wichtiger als Ornamentik.
**Würfel:** bewusst anders: ohne Muscheln, Ranken, orientierte Aufdrucke und ohne Klebelaschen. Einheitliche, abgerundete Würfel mit gewöhnlichen Augen und subtiler Materialwirkung. Farb-/Zahlwert aus jedem sinnvollen Blickwinkel klar identifizierbar.
**Interaktion:** Optik darf keinesfalls die bewährte Touch-Bedienung verschlechtern.

## Nicht im aktuellen Scope
Backend, Accounts, Lobby, Persistenz, echte Multiplayer-Synchronisation, vollständige Stichauswertung und vollständige Regellogik. Dafür später eigene Tickets/Meilensteine.
