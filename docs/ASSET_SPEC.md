# Visuelle Assets — Produktionsspezifikation v1

## Gestaltungsprinzip
Ocean Edition: hochwertige, charmante Unterwasser-Optik mit moderaten Lichtreflexen. Fokus auf Erkennbarkeit bei ~40–90 px UI-Darstellung. Bildgenerierte Entwürfe sind **Stilreferenzen**; vor Produktiveinsatz Geometrie, Typografie, Schnittkanten und Alpha-Kanal technisch prüfen.

## Karten — genehmigte Richtung
- System: 5 Farben × Zahlenwerte 0–7 = **40 einzigartige Vorderseiten**.
- Reihenfolge / semantische Schlüssel: `blue`, `red`, `yellow`, `purple`, `green`; `0..7`.
- Individuelle Karten im Hochformat, Zielverhältnis **2:3** (z. B. Master-SVG `240×360`, WebP/PNG `240×360` und `480×720` für Retina). Nicht durch Strecken quadratischer Entwürfe erzwingen.
- Große, kontraststarke, korrekt gesetzte Ziffer. Muscheln, Perlen, Blasen, Korallen, leichte goldene Zierkante sind **bei Karten** willkommen.
- Dekoration so platzieren, dass die Zahlen im Fächer sichtbar bleiben. Auch bei gedrehter Karte klare Zahl.
- Ein einheitliches, deutlich unterscheidbares Kartenrückseitenmotiv für Gegner. Keine Gegenspieler-Vorderseiten rendern.
- Auswahl-Glow, Schatten und Erhebung **durch CSS** statt in den Basis-Assets, damit Größe, Kontrast und Animation flexibel bleiben.
- Farben laut aktuellem Prototype:
  - blue: `#187cde`
  - red: `#ec3451`
  - yellow: `#f5c021`
  - purple: `#9a48d2`
  - green: `#24ae78`
- Zusätzlich optional monochrome Farbkennzeichnung / kleine Symbole für Nutzer mit Farbsehschwäche vorsehen.
- Namensschema: `assets/cards/{color}-{value}.webp` bzw. `.svg`, `assets/cards/back.webp`.

## Würfel — NEUES, VERBINDLICHES Feedback
- **Keine Ornamentik auf Würfeln.** Keine Muscheln, Wasserpflanzen, Perlensymbole, Rahmen oder bildhafte Textur.
- **Keine Klebelaschen.** Das von einem Faltwürfel abgeleitete Netz ist nur ein geometrisches Gedankenmodell, **kein** vorgesehenes Asset.
- Einfache, abgerundete, haptisch wirkende Würfel. Einheitliche Kunststoff-/Harzoberfläche mit diffusem Licht und sanftem Glanz; Augen als kontrastreiche Vertiefungen oder Inlays.
- Sechs korrekte Flächen mit Augenwerten **1–6**. Standard-Gegenüber: `1↔6`, `2↔5`, `3↔4`.
- **Richtungsneutral:** keine face-spezifischen Motive oder aufrechte Grafik, kein 'oben/unten' in einer Textur. Pip-Muster müssen unabhängig von der Körperdrehung gut zählbar sein. Die sechs Flächen sind natürlich nicht wertgleich; beim Rendern muss die als Spielwert geltende Seite erkennbar ausgerichtet werden.
- Farbset identisch zu den Karten, aber Material darf eine jeweils dunklere Sättigung besitzen. Helle/weiße Augen, bei Gelb ggf. dunkle Augen wegen Kontrast; technisch/einheitlich entscheiden.
- Auswahleffekt in CSS/WebGL-Overlay: Ring, leichte Elevation, dezenter Glow. Nicht in den Basistexturen einbacken.
- **Empfehlung:** Performance zuerst. Für Mini-Ansichten SVG oder gerenderte PNG/WebP mit 6 korrekten Augenwerten × 5 Farben. 3D per `GLB` optional für große Ansicht/Animation, möglichst ein wiederverwendbares Mesh mit Farb-/Pip-Konfiguration.
- 3D-Texturen: nahtlos, ohne Klebelaschen, UI-Fähigkeit für WebGL; wenn echte Geometrie möglich, Eyes als Mesh/Decal statt gemalte Würfelnetze.
- Die Zahl auf einem Würfel entspricht dem Wert der gut sichtbaren, korrekt ausgerichteten Spiel-Fläche; **nicht** einfach ein künstliches Ziffernlabel über alle Seiten legen.

## Lieferung / Struktur
```
assets/
  cards/
    blue-0.webp ... green-7.webp
    back.webp
  dice/
    blue-1.webp ... green-6.webp
    # optional: cube.glb, material presets
  raw/
    # kuratierte Originalentwürfe, nur Referenz
```

## Performance / Qualität
- Kleinste Anzeige testen (24–38 px Würfel / 40–75 px Karten), Retina separat berücksichtigen.
- Transparenter Alpha-Kanal, keine Schachbrett-Hintergründe in exportierten Dateien.
- Trim transparente Ränder; optional Sprite-Atlas nur mit definiertem Manifest.
- WebP für Raster-Assets; SVG für vektorielle, gut skalierbare Designs. Kein riesiges PNG für jede Instanz laden.
- Kein verpflichtendes WebGL auf älteren Geräten; funktionsfähiger 2D-Fallback.
