[← Startseite](index.md)

# Technik

| Teil | Womit | Aufgabe |
| --- | --- | --- |
| Karte und Oberfläche | Godot 4.7 | alles, was man sieht und antippt |
| Rechenkern | Rust | die ganze Spielwelt und alle Regeln |
| Spielstand | SQLite | eine Datei pro Partie |
| Handy | Android zuerst | iOS braucht später Xcode |

## Rechenkern

Der Rechenkern in Rust besitzt die Spielwelt allein. Die Oberfläche kennt keine Spielregeln. Sie schickt dem Kern Befehle (zum Beispiel „Quartal beenden“) und zeigt, was er zurückmeldet.

## Spielstand

Jede Partie ist eine SQLite-Datei. Der Zustand der Welt liegt darin als **ein Schnappschuss mit Versionsnummer**, wie bei Mobilspielen üblich. Tabellen gibt es nur für Verwaltungsangaben. Ändert sich das Format, werden alte Spielstände während der Entwicklung verworfen; es gibt keine Umwandlung alter Stände.

## Umbau auf Godot

Das Spiel lief zuerst in Flutter mit einer Webkarte. Am 23. November 2026 wurde der Umzug auf Godot entschieden. Der Rust-Kern bleibt. Die alte Flutter-App und die Webkarte sind seither gelöscht. Der Umbau läuft in Etappen:

1. Fundament: Godot-Projekt, Brücke zum Kern, Weltkarte, Android-Bau (fertig)
2. Grundgerüst: Start, Reichswahl, Spiel, Produktion, Markt (fertig)
3. Karte im Look der EU5-Karte (fertig)
4. Übrige Seiten: Hof, Haus, Rat, Militär
5. Alte Flutter-App und Webkarte löschen (fertig)
6. 3D-Köpfe

Auf Android zeichnet Godot vorerst mit OpenGL ES 3, weil der Emulator das Bild der Vulkan-Variante nicht zeigen kann.
