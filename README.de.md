# Scope Pulse

[English](README.md) · **Deutsch**

### Was bleibt hängen?

Bei Social-Media-Auswertungen wollte ich die Beiträge hinter einer Kennzahl sehen: Was wurde gespeichert, wie kommt die Rate zustande, und lassen sich die Ergebnisse überhaupt sinnvoll vergleichen?

Scope Pulse ist eine funktionierende lokale Anwendung für den Import von Beitragskennzahlen, die Auswertung von Kampagnen und die Erstellung eines Berichts. Ein lokales Sprachmodell schlägt auf Basis berechneter Befunde weitere Versuche vor. Die Texte bleiben bis zur Prüfung bearbeitbar.

![Scope Pulse mit Beitragskarten, Kennzahlenauswahl und Berechnung des gewählten Beitrags](assets/pulse-studio.jpg)

*Die Screenshots verwenden ein erfundenes Studio, illustrative Titelgrafiken und erfundene Kennzahlen. Zu sehen ist die lokal laufende Anwendung.*

[Bildschirmaufnahme ansehen](assets/pulse-walkthrough.mp4) · [Beispielbericht öffnen](assets/sample-report.pdf) · [Prüfungen nachlesen](docs/VERIFICATION.md#deutsch)

## Von der CSV zum nächsten Versuch

**Beim einzelnen Beitrag anfangen.** Zwischen Interaktionsrate, Speicherungen, Impressionen und Klickrate wechseln. Rechts stehen die Ausgangswerte, der Messzeitpunkt und der Import, aus dem der ausgewählte Beitrag stammt.

**Vergleiche nachvollziehbar halten.** Fehlende Werte bleiben fehlend. Ein späterer kumulativer Messstand ersetzt für die Auswertung den früheren; beide werden nie addiert. Zeiträume sind gleich lang, Plattformen werden getrennt betrachtet und das Alter der Messwerte bleibt sichtbar.

**Aus einer Beobachtung einen Versuch machen.** Qwen3 4B wählt aus berechneten Befunden und formuliert Vorschläge auf demselben Mac. Die faktischen Aussagen gibt die Anwendung vor. Die Vorschläge lassen sich überarbeiten. In einen Bericht gelangt nur ein geprüfter Entwurf, der zum aktuellen Datenstand passt.

**Den Bericht als Momentaufnahme behalten.** PDF und CSV halten die Auswahl, die Berechnungsgrundlage und den geprüften Text fest. Spätere Importe verändern einen vorhandenen Bericht nicht.

![Aufnahme der funktionierenden Anwendung](assets/pulse-preview.gif)

*27 Sekunden mit Beitragsauswahl, Vergleich, Importprüfung und Berichtserstellung. Die geprüften Vorschläge wurden während des Tests redaktionell überarbeitet.*

## Eine eigene Gestaltung

Petrol, Koralle und helles Salbeigrün geben Pulse den Charakter eines kleinen Redaktionsstudios. Große Beitragskarten bestimmen die Seite. Archivo trägt die Überschriften, Space Mono hebt Messwerte und Zeitpunkte hervor. Dazu kommen eine helle Darstellung und ein Layout für schmale Bildschirme.

![Vergleich gleich langer Zeiträume mit Datenabdeckung und Formaten](assets/pulse-comparison.jpg)

## Was bereits funktioniert

CSV-Spaltenzuordnung, Vorschau und Prüfung; Erkennung von Dubletten und Widersprüchen; Kampagnenzuordnung; Account- und Datumsfilter; kumulative Messstände in SQLite; beschreibende Kennzahlen; lokale KI-Entwürfe; geprüfte PDF- und CSV-Exporte.

Die private Anwendung nutzt Python, SQLite, JavaScript, ReportLab, Ollama und Qwen3 4B. Ich habe sie mit Codex entwickelt. Besonders wichtig waren mir der Arbeitsablauf, die Gestaltung und eine nachvollziehbare Einordnung der Zahlen. [Entscheidungen zur Umsetzung und mein Anteil →](docs/CASE_STUDY.de.md)

**Lokal geprüft am 20. Oktober 2026:** 37 automatisierte Tests bestanden. Der Browserablauf wurde mit 36 erfundenen Beiträgen und 37 Messständen durchgespielt. Die abschließenden Modelltests umfassen Instagram und LinkedIn; alle fünf Seiten des Beispielberichts wurden gerendert und visuell geprüft. [Nachweise und Grenzen →](docs/VERIFICATION.md#deutsch)

Diese Version importiert CSV-Dateien. Sie verbindet sich nicht mit Social-Media-APIs, veröffentlicht keine Beiträge und prognostiziert keine Kampagnenleistung. Die dokumentierten Kennzahlendefinitionen gehören zur Anwendung und können von einem Plattformbericht abweichen.

**Dieses Repository enthält ausschließlich die Präsentation.** Quellcode, Datenbank, Modelle, ursprüngliche Importdateien und rohe Modellantworten bleiben privat. Das PDF ist ein ausgewähltes Präsentationsergebnis mit erfundenen Daten. Für das eigene Portfolio-Material wird keine Open-Source-Lizenz erteilt. [Rechte](RIGHTS.md) · [Hinweise zu Drittbestandteilen](THIRD_PARTY_NOTICES.md)
