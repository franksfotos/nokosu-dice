# UX-Entscheidungen und Akzeptanzkriterien

## Geräte / Responsive Design
- **Telefon:** Portrait ist primär; auch bei 320 CSS px muss die UI sinnvoll nutzbar sein. Kein Landscape-Zwang.
- **iPad:** Landscape bevorzugt, mehr Raum für Mitspieler und Tisch. Keine einfache Skalierung eines Smartphone-Screens.
- Safe areas: `env(safe-area-inset-*)` nutzen; wesentliche Drag-/Swipe-Gesten und Bedienelemente nicht unmittelbar am linken oder rechten Rand.
- Keine horizontalen Scrollbars für die Hauptansicht. Optionale Kartenauswahl kann im Overlay horizontal scrollen.

## Informationsdarstellung
- Spieler unten: eigene Karten (offen) und Würfel (offen).
- 2–4 Gegenspieler: Name/Avatar, Anzahl verdeckter Karten, maximal 5 **offene** Würfel. Niemals Kartenwerte anzeigen.
- Platz für fünf Würfel pro Spieler, auch bei kleineren Mengen; leere Positionen dürfen dezent angezeigt werden.
- Aktueller Stich maximal 5 Beiträge und der Trumpf sind unterscheidbar von den Handkarten.
- Immer klar erkennbar, wer am Zug ist, was gewählt ist und welche Aktion als nächstes möglich ist.

## Karteninteraktion
- Bis zu zehn Karten in einem **lesbaren Fächer**, nicht bloß zehn eng nebeneinanderliegende Mini-Rechtecke.
- Werte der Karten auch im überlappenden Fächer sichtbar. Karten dürfen beim Tippen angehoben werden.
- Gewählte Karte erhält visuelle Hervorhebung **nicht nur über Farbe**: Erhebung, Kontur, ggf. sanfter Glow.
- Ein erneuter Tap hebt die Wahl auf; Tap auf andere Karte/Würfel wechselt die Auswahl.
- Für enge Displays: vergrößerbare Kartenansicht mit vollständigen Karten und großen Tap-Flächen.
- Effektive Interaktionsflächen wenn möglich ~44 × 44 CSS px; bei überlappenden Karten müssen die sichtbaren Treffbereiche eindeutig sein.

## Würfelinteraktion
- Fünf Plätze je Auslage. Farbe + **Augenzahl** für Spieler und Gegner sichtbar.
- Würfelgröße ansprechend, aber nicht auf Kosten der Trefffläche.
- Selektierter Würfel: sichtbarer Ring/Anheben/leichte Animation. Kein unleserlicher Neon-Glow.
- Würfel dürfen nicht durch Animation zufällig ihren **Spielwert** zu ändern scheinen.
- Letzten regulären Würfel nicht auswählbar/spielbar machen, außer eine später implementierte Regel erlaubt dies.

## Zug / Feedback
- Nur **Karte ODER Würfel** pro Zug.
- Primär-CTA `Ausspielen` erst nach Auswahl aktiv; direktes Spielen per Tap vermeiden.
- Rückgängig im UX-Dummy möglich; später mit bestätigten Netzwerkzügen abstimmen.
- Kurzes Feedback und dezente Übergänge; `prefers-reduced-motion` unterstützen.
- Accessibility: Fokusindikatoren, semantische Buttons, sichtbarer Text und `aria-label` für Farbe + Wert.

## Manuelle Tests
1. Auf 320 und 390 px sind 10 Handkarten erreichbar und unterscheidbar.
2. Nach Auswahl einer mittleren und einer äußeren Karte bleibt deren Wert lesbar.
3. Bei 5 Spielern sind 4 Gegner mit je 5 Würfel-Plätzen darstellbar.
4. Auswahl Karte → Würfel → Karte, Ausspielen und Undo funktioniert.
5. iOS Safari: Zurück-Wischgeste wird nicht versehentlich durch Auswahl ausgelöst.
6. Landscape-iPad: keine störenden Leerflächen, kein abgeschnittenes Panel.
7. Bei fehlenden Assets bleibt der Text bzw. der CSS-Fallback sichtbar.
