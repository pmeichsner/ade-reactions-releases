# ADE Reactions

Automatischer Reaction-Schnitt für Adobe Premiere Pro auf Windows. Die große Facecam wird bei zusammenhängenden Kommentaren eingeblendet; kurze Ausrufe bleiben klein. Der TV-Ton wird während Sprache weich um 12 dB abgesenkt. Die Lautstärkekeyframes sind direkt auf A1 sichtbar.

## Download und Installation

Die aktuelle vollständige Installationsdatei findet ihr unter [Releases](https://github.com/pmeichsner/ade-reactions-releases/releases/latest). Nur die Datei **ADE-Reactions-1.1.2-Setup-x64.exe** herunterladen. Die anderen Release-Dateien werden vom automatischen Updater verwendet und müssen nicht manuell heruntergeladen werden.

1. Premiere-Projekte speichern und Premiere schließen. Eine im UXP Developer Tool geladene Entwicklungsversion vorher entladen.
2. Das vollständige Setup starten.
3. Premiere öffnen: **Fenster → UXP Plugins → ADE Reactions**.

Voraussetzungen: Windows x64, Adobe Premiere Pro 27.0 und Creative Cloud Desktop mit Adobe Plugin Installer. Eine macOS-Version ist noch nicht verfügbar. Das Setup enthält die lokale Engine, Sprachmodelle und CPU-/NVIDIA-CUDA-Laufzeiten. ADE Captions und ADE Podcast werden nicht benötigt. Für die Nutzung auf weiteren Schnittrechnern ist kein GitHub-Konto nötig.

## Fester Spuraufbau

| Spur | Inhalt |
|---|---|
| V1 | TV-Bild |
| V2 | Kleine Facecam mit Rahmen |
| V3 | Große Facecam mit vorbereitetem Hintergrund |
| A1 | TV-Ton |
| A2 | Eure Stimmen |

Material vorher synchronisieren und TV-Pausen bereits schneiden. Sprache ist immer Deutsch, Facecam-Nachlauf immer 0,25 Sekunden. Die Bildwechsel-Erkennung bietet drei Stufen. Auf V3 wird die längste Verschachtelung als Facecam-Quelle erkannt; andere Quellen wie Übergangsgrafiken bleiben erhalten. Jede Verarbeitung erzeugt eine neue Sequenzkopie. Für einen neuen Lauf die Ausgangssequenz öffnen, damit sich Absenkungen nicht aufaddieren.

## Automatische Updates

Die Quelle **pmeichsner/ade-reactions-releases** ist ab Version 1.1.2 voreingestellt. Diese Version einmal installieren; danach prüft der Hintergrund-Updater automatisch auf neue Releases. Neue Komponenten werden geladen, aktiviert werden sie erst bei geschlossenem Premiere. Bereits vorhandene, unveränderte Laufzeiten und Modelle werden wiederverwendet. Release-Metadaten werden per RSA-Signatur, Dateien per SHA-256 geprüft. Bei einem fehlgeschlagenen Update wird die vorherige Version wiederhergestellt. Ohne Internet bleibt die installierte Version nutzbar.

Die Startmenü-Einträge **ADE Reactions Updates** und **ADE Reactions Jetzt aktualisieren** erlauben Quellenwahl und manuelle Prüfung. Eine leere Quelle deaktiviert Downloads. Bei Versionen vor 1.1.2 ist noch keine öffentliche Quelle voreingestellt: entweder den neuen vollständigen Installer verwenden oder diese Repository-Quelle einmal im Update-Dialog eintragen.

## Lokale Verarbeitung

Die Audioanalyse bleibt auf dem Rechner. Temporäre Exporte und Transkripte werden lokal unter `%LOCALAPPDATA%\Programs\ADE Reactions\managed\data\jobs` gespeichert. Modelle, Engine und Updates werden aus diesem öffentlichen Repository geladen; Projektmedien werden dabei nicht hochgeladen.

Der automatische Schnitt bleibt ein bearbeitbarer Rohschnitt. Musik, TV-Ton auf der Mikrofonspur, überlappende Stimmen und Erkennungsfehler können Entscheidungen beeinflussen. Während Export und Schnitt die aktive Sequenz nicht wechseln und die Timeline nicht bearbeiten.

Dieses Repository enthält veröffentlichte Installations- und Updatepakete sowie diese Anleitung. Quellcode, Projektdateien und private Signierschlüssel sind nicht enthalten. Lizenzhinweise der mitgelieferten Komponenten befinden sich im Installationspaket.
