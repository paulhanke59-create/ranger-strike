# Ranger Strike

Eigenes Top-Down-Kommandospiel im C64-Look: ein Einzelkämpfer hinter den feindlichen Linien. Inspiriert vom Spielprinzip alter 8-Bit-Klassiker, aber komplett eigener Code, eigene Grafik und eigene Sounds (alles wird im Code erzeugt, keine fremden Assets).

## Spielen (Browser / GitHub Pages)

Das Spiel ist eine einzelne Datei: `docs/index.html`.

GitHub Pages aktivieren: Repository → Settings → Pages → Branch `main`, Ordner `/docs`.

Lokal testen: `docs/index.html` einfach im Browser öffnen.

## Steuerung

| Aktion | Tastatur | Touch |
|---|---|---|
| Laufen | Pfeile / WASD | Steuerkreis rechts unten (Daumen darin ziehen) |
| Feuer | Leertaste | FEUER |
| Handgranate | G | GRN |
| Aktion (Ladung legen, befreien, Dokumente) | E | AKT |
| Rennen (kostet Kraft) | Shift | RENN (umschalten) |
| Schleichen (schwerer zu entdecken) | C | – |
| Pause / Minimap | P / M | – |
| Mission abbrechen | Esc | roter Knopf oben rechts |
| Musik an/aus | N | Lautsprecher-Knopf oben rechts |

## Spielablauf

Das Spiel besteht aus 12 Levels, die nacheinander gespielt werden. Jedes Level startet mit voller Energie und Munition. Wer stirbt, startet das Level neu. Nach jedem geschafften Level wird der Fortschritt automatisch gespeichert (Menü: „Weiter").

Das Menü bietet: 1 Neue Mission (Kampagne ab Level 1), 2 Letzte Mission fortsetzen (Speicherstand im Browser) und 3 Einzelmission starten (ohne Speicherstand). Vor dem Start wählst du die Schwierigkeit, danach (je nach Stufe) einen Skill:

| Schwierigkeit | Gegner | Skills |
|---|---|---|
| Einfach | weniger | 4 zur Auswahl |
| Nicht ganz einfach | etwas weniger | 2 zufällig ausgewählte zur Auswahl |
| Normal | normal | keiner |
| Schwer | mehr | keiner |
| Rambo | viel mehr | keiner, dafür viel Munition und mehr Erste-Hilfe-Kästen |

Skills:

| Skill | Wirkung |
|---|---|
| Treffsicherheit | Zielhilfe, keine Streuung, schnelleres Feuer, mehr Munition |
| Tarnung | Gegner sehen dich nur aus der Nähe, leisere Schüsse, schnelleres Schleichen |
| Sprengmeister | Mehr Granaten, größerer Radius, kurze Zündschnur, weniger Selbstschaden |
| Resilienz | 150 statt 100 Leben, 15 % weniger Schaden, Kraft erholt sich schneller, Medikits heilen mehr |

Levels:

1. **Funkenflug** – 3 Munitionsdepots sprengen (Ladung legen mit E und wegrennen, oder Granate werfen)
2. **Freiheit** – Gefangene aus 3 Lagern befreien
3. **Schattenakte** – Dokumente aus 2 Kommandoposten stehlen
4. **Großer Schlag** – gemischter Einsatz
5. **Brückenschlag** – 2 Brücken über den Fluss sprengen (nicht auf der Brücke stehen bleiben!)
6. **Funkstille** – 3 Funkmasten zerstören; je weniger Masten stehen, desto weniger Verstärkung kommt
7. **Offizier** – den General (goldene Markierung, mehrere Treffer nötig) mit seinen Leibwächtern ausschalten
8. **Geiselrettung** – Geisel befreien und lebend zur Landezone bringen; sie folgt dir, kann aber getroffen werden
9. **Geisterflug** – 3 Dokumente holen, ohne dass dich ein Gegner bemerkt (keine Verstärkung, jede Entdeckung beendet den Einsatz)
10. **Nachteinsatz** – dunkle Karte, sichtbar sind nur du und die Lichtkegel der Wachen
11. **Fahrzeugjagd** – 3 geparkte Fahrzeuge (Jeep, Lkw, Panzer) sprengen
12. **Sumpfflucht** – Akte holen und durch den langsamen Sumpf vor den Verfolgern zur Landezone fliehen

In der Einzelmission-Auswahl blätterst du mit den Pfeil-Knöpfen (Tastatur: Pfeil links/rechts).

Gegner sehen dich, rufen „Enemy!" und holen Verstärkung. Auch Schüsse und Explosionen locken neue Gegner an. Verlierst du sie, ziehen sich die Verstärkungen wieder zurück. Die Gegner laufen Patrouille. Auf der Minimap siehst du nur die Gegner, die gerade im Bild sind (gelb = alarmiert).

Nach allen Zielen: zurück zur Landezone (weißes H), dann ist das Level geschafft.

## Android-App (Capacitor)

Voraussetzung: Node.js und Android Studio.

```bash
npm install
npx cap add android
npx cap sync android
npx cap open android
```

Tipps:

- In `android/app/src/main/AndroidManifest.xml` bei der Activity `android:screenOrientation="sensorLandscape"` setzen, damit das Spiel im Querformat läuft.
- Nach jeder Änderung an `docs/index.html` einmal `npx cap sync android` ausführen.

## Ideen für die nächsten Schritte

- Weitere Missionstypen (Brücke sprengen, Offizier ausschalten)
- Fahrzeuge und Minen als Gegner
- Highscore-Liste (localStorage)
- Mehr Waffen und Missionsbriefing vor dem Start

## Musik

Die Musik besteht aus eigenen Chiptune-Stücken, die live per WebAudio erzeugt werden (heroisches Menü-Thema im 80er-Action-Stil mit Synth-Bläsern, düsteres Einsatz-Thema, treibendes Action-Thema bei Alarm, kurze Fanfaren für Sieg und Niederlage). Es sind keine Melodien aus anderen Spielen.
