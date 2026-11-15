# Eddie the Eagle — Ski Jump (3D-Skispringen in Ego-Perspektive)

Ein Browserspiel in einer einzigen HTML-Datei. Du siehst die Schanze durch die Augen
des Springers: Anfahrt runter, mit der Leertaste im perfekten Moment am Schanzentisch
abspringen, im Flug mit den Pfeiltasten gegen den Seitenwind stabilisieren und die
Telemark-Landung stehen.

## Starten

Option 1 — `index.html` direkt in einem modernen Browser öffnen (Chrome, Edge, Firefox).

Option 2 — lokal über einen Webserver:

```bash
cd 3d-ski-jump
python -m http.server 8000
# dann http://localhost:8000 öffnen
```

Einmalig wird eine Internetverbindung benötigt, um three.js vom CDN (jsdelivr) zu laden.

## Menü und Modi

Hauptmenü → Modus (aktuell: **TRAINING**) → Schanze wählen:

| Schanze | K-Punkt | Hill Size | Schanzenrekord | Absprungfahrt | Tischhöhe | Anlaufturm |
|---|---|---|---|---|---|---|
| Heimatschanze | 120 m | 130 m | 132,0 m | ~101 km/h | 8 m | ~49 m |
| Oberstdorf | 120 m | 137 m | 143,5 m | ~92 km/h | 3 m | ~38 m (45 m Turm) |

Bestweiten werden pro Schanze im Browser gespeichert. ESC führt jederzeit zurück ins
Hauptmenü, während der Menü-Schanzenwahl zurück zur Modus-Auswahl.

## Steuerung

| Taste | Funktion |
|---|---|
| LEERTASTE | Anfahrt starten / am Schanzentisch abspringen |
| Pfeil hoch / runter | Im Flug vorlehnen / zurücklehnen (Anstellwinkel) |
| Pfeil links / rechts | Nach links / rechts rollen, gegen den Wind stabilisieren |
| LEERTASTE | Kurz vor der Landung → Telemark-Landung (Bonus) |
| R | Neustart — ESC Hauptmenü |

## Spielablauf

- In der Anfahrt erscheint unten eine Timing-Leiste: LEERTASTE drücken, wenn der
  weiße Marker in der grünen Zone ist — nur dann gibt es volle Absprungkraft.
- In der Luft gilt: etwa 30° nose-down ist die optimale Flugposition. Der
  Lagemesser (Kreis unten) zeigt mit der Horizontlinie an, ob du zu flach
  oder zu steil liegst.
- Seitenwindböen drücken dich in die Rolle — mit links/rechts dagegen halten,
  sonst driftest du von der Piste und stürzt.
- Weich entlang des Hangs landen. Rote Linie = K-Punkt, blaue Linie = Hill Size.
- Wertung: Weitenpunkte (60 + 1,4 × Meter jenseits des K-Punkts) +
  Haltungsnoten bis 20. Die Weite wird — wie im echten Skispringen — am
  Landepunkt gemessen.

## Referenzwerte (numerisch verifiziert)

| Sprung | Heimatschanze | Oberstdorf |
|---|---|---|
| Perfekt (Timing + Fluglage) | ~132 m (Rekord-Bereich) | ~143 m (Rekord-Bereich) |
| Schwaches Timing | ~118 m | ~125 m |
| Ohne Haltungskorrektur | ~84 m | ~68 m |
