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

## Missionen

1. **Funkenflug** – 3 Munitionsdepots sprengen (Ladung legen mit E und wegrennen, oder Granate werfen)
2. **Freiheit** – Gefangene aus 3 Lagern befreien
3. **Schattenakte** – Dokumente aus 2 Kommandoposten stehlen
4. **Großer Schlag** – gemischter Einsatz

Nach allen Zielen: zurück zur Landezone (weißes H), dann ist der Einsatz geschafft.

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
