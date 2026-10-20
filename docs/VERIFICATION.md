# Verification record

**20 October 2026 · local macOS application · synthetic data**

[Deutsch](#deutsch) · [Project](../README.md)

## Automated checks

**37 tests passed.** Resource warnings were treated as errors. These tests ran against the private application; this presentation repository does not contain a public CI pipeline or the test source.

| Area | What was checked |
| --- | --- |
| Imports | Original-byte preservation, atomic commits, duplicate handling, conflicting measurements, commit-time revalidation, simultaneous identical imports, changed staged files, column mapping and invalid inputs |
| Calculations | Matched weighted-rate denominators, unknown versus zero, latest cumulative measurement, cutoff filtering, equally long periods, platform/account/campaign isolation, empty selections and eligible format evidence |
| Persistence | Campaign revision conflicts, original provenance, data after restart and closed database connections |
| Local model | Existing distinct facts, compatible follow-up categories, numeric tokens bound to the referenced fact, rejected responses retained privately and no accepted brief on failure |
| Review and reports | Unreviewed or stale briefs blocked, revision checks, actual PDF/CSV generation, Unicode and literal markup, spreadsheet-formula escaping and unchanged earlier reports |
| HTTP | Source/database/model paths unavailable, Host/Origin and mutation-header checks, request shape and size limits |

Two concrete arithmetic cases were checked independently of the demo:

- Posts with 80 interactions / 1,000 impressions and 100 / 9,000 produce a weighted rate of **1.8%**. The application does not average their two percentages.
- A post with cumulative measurements of 1,000 and then 2,000 impressions contributes **2,000**, not 3,000. An earlier cutoff returns the earlier measurement.

## Browser and real model runs

The browser workflow imported 36 synthetic posts. A CSV with renamed headers was mapped successfully; its two existing observations were skipped. Importing a later measurement resulted in **36 posts and 37 observations**.

Negative impressions and a capture time before publication visibly blocked import. Campaign assignment was changed, saved and restored. Filters, metric selection, source detail, model drafts, review and report creation were exercised in the running application.

Layouts were checked at viewport widths of 320, 390, 820, 1280 and 1440 pixels. Narrow layouts had no page-level horizontal overflow; wide import tables scroll within their own area. Dark and light views were inspected. No console errors or warnings were observed in the checked browser session. This was desktop viewport testing, not a physical phone or cross-browser certification.

**Final live model checks:** Qwen3 4B returned accepted drafts for one Instagram selection and one LinkedIn selection. The model was checked against its expected digest before each call. Both calls ran locally; no hosted inference service was used.

Earlier development calls produced rejected or incomplete output. The response structure was revised and the final two cases rerun. This is a small integration check, not a measured reliability rate across arbitrary datasets. Structural validation does not establish causality or guarantee a useful suggestion. The sample report's next steps were edited and reviewed.

## Presentation outputs

- A real browser recording, approximately 27 seconds, packaged as MP4 and GIF. It shows post selection, a comparison, blocked import and report generation.
- Screenshots of the running application, with all example metrics identified as synthetic demonstration data.
- A five-page [sample PDF](../assets/sample-report.pdf), generated from a stored report snapshot and visually checked on every page.
- PDF and CSV attachment responses were checked against locally stored bytes. This confirms file generation and transfer, not an operating-system download-folder test.

The PDF contains 12 synthetic Instagram posts. Ten have a complete interaction-rate basis; one lacks a required metric and one has zero impressions. The selected report uses the latest available observations up to its stated cutoff.

Sample PDF SHA-256:

`7f85157efad09a5383cc44de0cb6b16467460d13efd682c182042f0a7f77fed1`

## Limits

The application uses a documented CSV contract, not native platform API connections. No real campaign, public deployment, multiuser security, large production load or broad model evaluation was verified. Synthetic results do not demonstrate social media growth.

Only presentation files are published. Application code, SQLite database, model weights, original CSV imports and raw evaluation records remain private.

---

## Deutsch

**20. Oktober 2026 · lokale Anwendung auf macOS · erfundene Daten**

**37 automatisierte Tests bestanden.** Ressourcenwarnungen wurden als Fehler behandelt. Die Tests liefen gegen die private Anwendung. Dieses Präsentationsrepository enthält weder eine öffentliche CI-Pipeline noch den Testquellcode.

| Bereich | Geprüft wurde |
| --- | --- |
| Import | Unveränderte Originaldateien, vollständiges Speichern, Dubletten, widersprüchliche Messstände, erneute Prüfung beim Speichern, gleichzeitige identische Importe, veränderte Vorschaudateien, Spaltenzuordnung und ungültige Eingaben |
| Berechnung | Passende Nenner der gewichteten Rate, unbekannt gegenüber null, jüngster kumulativer Messstand, Stichtage, gleich lange Zeiträume, getrennte Plattformen/Accounts/Kampagnen, leere Auswahl und berechenbare Formatbelege |
| Speicherung | Versionskonflikte bei Zuordnungen, ursprüngliche Herkunft, Daten nach Neustart und geschlossene Datenbankverbindungen |
| Lokales Modell | Vorhandene unterschiedliche Befunde, passende Folgeversuche, Zahlenbezug zum jeweiligen Befund und private Aufbewahrung abgelehnter Antworten ohne akzeptierten Entwurf |
| Prüfung und Bericht | Sperre ungeprüfter oder veralteter Entwürfe, Versionsprüfung, echte PDF-/CSV-Erzeugung, Umlaute und wörtliche Auszeichnung, Schutz vor Tabellenformeln und unveränderte frühere Berichte |
| HTTP | Nicht erreichbare Quellcode-, Datenbank- und Modellpfade, Prüfung von Host/Origin und Änderungsheader sowie Grenzen für Anfrageformat und Größe |

Zwei konkrete Rechenfälle:

- 80 Interaktionen bei 1.000 Impressionen und 100 bei 9.000 ergeben gewichtet **1,8 %**. Die beiden Prozentsätze werden nicht einfach gemittelt.
- Kumulative Messstände mit 1.000 und später 2.000 Impressionen gehen mit **2.000**, nicht mit 3.000 ein. Ein früherer Stichtag liefert den älteren Messstand.

### Browser und echte Modelldurchläufe

Im Browser wurden 36 erfundene Beiträge importiert. Eine CSV mit umbenannten Spalten ließ sich zuordnen; ihre zwei bereits vorhandenen Messstände wurden übersprungen. Nach dem Import eines späteren Messzeitpunkts enthielt die Anwendung **36 Beiträge und 37 Messstände**.

Negative Impressionen und ein Erfassungszeitpunkt vor der Veröffentlichung blockierten den Import sichtbar. Eine Kampagnenzuordnung wurde geändert, gespeichert und wiederhergestellt. Filter, Kennzahlenauswahl, Datenherkunft, KI-Entwurf, Prüfung und Berichtserstellung wurden in der laufenden Anwendung bedient.

Die Darstellung wurde bei 320, 390, 820, 1280 und 1440 Pixeln Ansichtsbreite geprüft. Schmale Ansichten hatten keinen seitlichen Überlauf der gesamten Seite; breite Importtabellen scrollen in ihrem eigenen Bereich. Dunkle und helle Darstellung wurden visuell kontrolliert. In der geprüften Browsersitzung wurden keine Konsolenfehler oder Warnungen beobachtet. Das war eine Prüfung mit Desktop-Ansichtsgrößen, keine Prüfung auf einem echten Smartphone oder eine Zertifizierung für mehrere Browser.

**Abschließende echte Modelltests:** Qwen3 4B lieferte akzeptierte Entwürfe für je eine Instagram- und LinkedIn-Auswahl. Vor jedem Aufruf wurde die erwartete Modellkennung geprüft. Beide Durchläufe liefen lokal, ohne externen Inferenzdienst.

Frühere Entwicklungsdurchläufe lieferten abgelehnte oder unvollständige Antworten. Daraufhin wurde die Ausgabestruktur überarbeitet und mit den beiden abschließenden Fällen erneut geprüft. Das ist ein kleiner Integrationstest, keine ermittelte Zuverlässigkeitsquote für beliebige Daten. Strukturprüfungen belegen weder Ursachen noch die Nützlichkeit eines Vorschlags. Die nächsten Schritte im Beispielbericht wurden redaktionell überarbeitet und geprüft.

### Präsentationsergebnisse und Grenzen

Die etwa 27 Sekunden lange Aufnahme zeigt echte Browserbedienung: Beitragsauswahl, Vergleich, blockierten Import und Berichtserstellung. Screenshots stammen aus der laufenden Anwendung. Alle fünf Seiten des [Beispielberichts](../assets/sample-report.pdf) wurden aus dem gespeicherten Datenstand erzeugt, gerendert und visuell geprüft.

Die PDF- und CSV-Antworten des Download-Endpunkts wurden mit den lokal gespeicherten Bytes verglichen. Damit sind Erzeugung und Dateiübertragung geprüft; ein Test des Download-Ordners im Betriebssystem ist damit nicht behauptet.

Im PDF stehen zwölf erfundene Instagram-Beiträge. Zehn haben eine vollständige Berechnungsgrundlage; bei einem fehlt eine erforderliche Kennzahl, ein weiterer hat null Impressionen. Der Bericht verwendet die jüngsten verfügbaren Messstände bis zu seinem angegebenen Stichtag. Die SHA-256-Prüfsumme des veröffentlichten PDFs steht oben.

Geprüft wurden keine echte Kampagne, öffentliche Bereitstellung, Mehrbenutzersicherheit, große Produktivlast oder breite Modellzuverlässigkeit. Die Anwendung nutzt einen dokumentierten CSV-Vertrag und keine direkte Plattformanbindung. Aus den Beispieldaten lässt sich kein Social-Media-Wachstum ableiten.

Veröffentlicht werden ausschließlich Präsentationsdateien. Quellcode, SQLite-Datenbank, Modellgewichte, ursprüngliche CSV-Importe und rohe Prüfergebnisse bleiben privat.
