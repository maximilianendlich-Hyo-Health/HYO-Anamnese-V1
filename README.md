# HYO Health – Ersttermin-Anamnese (Demo)

Schlanke Web-App für den logopädischen Ersttermin: gekürzter allgemeiner Teil (1 Verordnungsdaten der Verwaltung, 2 Medizinische Vorgeschichte, 3 Lebenssituation – Stand 02.11.2026) plus spezifisches Assessment je Diagnosegruppe. Spezifische Assessments gibt es für **Sprechapraxie (SP6, Behandlungsfeld SPAX)**: Anamnese aus der Aphasie, HWL kompakt mit Prozentwerten und Plausibilitätsprüfung, ergänzender Befund, Abschluss (bei Begleitaphasie gemeinsam mit der Aphasie) und Zwischenbewertung; für **KKS (Block MoCA, interne Abgrenzung)**: bei Behandlungsfeld KKS oder Begleitsymptomatik KKS in der Aphasie, Gesamtwert und Bewertung berechnet, Empfehlung neuropsychologische Abklärung; für **Fazialisparese (SP6/SC ab 18, Behandlungsfeld FAZ)**: Anamnese mit Kontraindikationen und Red Flags, Sunnybrook mit berechneten Scores, Funktionen, FaCE mit berechneten Subskalen, Abschluss und Zwischenbewertung; für **SC bei Kindern unter 18 (kindliche Dysphagie und Fütterstörung)**: Anamnese mit Ernährung, Gedeihen und Red Flags, korrigiertes Alter, Kö.Be.S. Kids bzw. Ruhe- und Mahlzeitbeobachtung, p-FOIS, Einordnung (Dysphagie/Fütterstörung), Abschluss und Zwischenbewertung; für **ST1–ST4/SF (Dysphonie, Stand 31.10.)**: Anamnese mit ärztlichem Befund, Notfall- und Warnzeichen getrennt, psychischer Vorerkrankung; Befund mit Atemmuster, Tonus, Aphonie-Prüfung, RBH, VOXplot (AVQI/ABI), Messwerte, VHI-12, Einordnung mit Abgleich zur Diagnosegruppe, Abschluss und Zwischenbewertung; für **SP6 (Dysarthrie)**: Anamnese, Abgrenzung, BoDyS, Verständlichkeit/VOXplot/CPIB-10, Abschluss und Zwischenbewertung; für **OFZ/SPZ/SCZ/SP3 (Myofunktion, Stand 31.10.)**: Anamnese inkl. Stillen/Flaschengabe bei Kindern, Befund mit automatisch berechnetem Kernwert, Einordnung mit Abgleich zur Diagnosegruppe, Abschluss und Zwischenbewertung; für **SP5 (Aphasie)**: Aphasie-Anamnese, BIAS A&R (Rohwert, T-Wert, Prozentrang, Einstufung je Untertest), Vermerk ergänzende Diagnostik (HWL/MoCA), CPIB-10/CETI, Abschluss und Zwischenbewertung, sowie für **SC (Kau- und Schluckstörungen)**, Stand v3 vom 31.10.: Dysphagie- und TK-Anamnese inkl. Kopf-Hals-Tumor (Phase nach Strahlentherapie und FEES-Hinweis berechnet), KSU, Trachealkanülen-Befund, GUSS mit Abbruchregel und Auswertung, Kostform-Empfehlung, Abschluss und – wenn durchgeführt – der FEES-Befund (Block 8) mit PAS, Yale, Murray, FEDSS und Kostform-Vorschlag aus der FEDSS, sowie die Zwischenbewertung (Block 9).

Eine einzige HTML-Datei, kein Server, keine Abhängigkeiten im Browser. Eingaben bleiben im Browser und werden weder gespeichert noch übertragen.

## Funktionen

- Diagnosegruppe oben wählen; das Behandlungsfeld (MV-06) wird nach Diagnosegruppe (bei „abweichend“ MV-28) und Alter gefiltert und vorbelegt – Regeln im Excel-Blatt „Behandlungsfelder“; weitere über „Zusätzliches Behandlungsfeld“ (MV-33, max. 3) (SC → Dysphagie, bei Kindern unter 18 laut Geburtsdatum → kindliche Dysphagie, SP5 → Aphasie, SP6 → Dysarthrie, OFZ/SPZ/SCZ → Myofunktion, ST1–ST4 → Dysphonie). Mehrere Module können gleichzeitig aktiv sein (Spalte „Modul“ im Excel)
- Untersuchung (VO-25), oben im Formular umschaltbar: **Erstuntersuchung**, **Zwischenuntersuchung** (Ende der Verordnung) oder **Abschlussuntersuchung** (Therapieende). Bei Zwischen- und Abschlussuntersuchung zeigt das Formular den allgemeinen Teil und die Zwischen- bzw. Abschlussbewertung je Modul; die Abschnitte der Erstuntersuchung sind ausgeblendet (über „Erstuntersuchung einblenden“ sichtbar, Werte bleiben erhalten, z. B. nach „JSON laden“). Bei der Abschlussuntersuchung ist die Entscheidung mit „Abschluss“ vorbelegt; Langdock schreibt dann einen Abschlussbericht.
- Alle Anzeige-Bedingungen aus dem Excel (z. B. TK-Felder nur bei DA-08 = JA, GUSS-Teile nur bis zum Abbruch)
- Berechnete Felder: GUSS-Teilsummen, Gesamtwert, Schweregrad, BODS-Summe; Kostform-Vorschlag aus der GUSS-Auswertung
- Screening-Ergebnisse (GUSS, EAT-10, BIAS, BoDyS, RBH, p-FOIS …) werden automatisch aus den Modulen übernommen und mit exportiert; ein eigener Screening-Block entfällt
- Pflichtfeld- und Formatprüfung (Regex, Wertebereiche); Normwerte bzw. Orientierung neben dem Feld (Spalte „Normwert / Orientierung“)
- Export als JSON mit den technischen Schlüsseln; „JSON laden“ stellt einen früheren Stand wieder her (z. B. für eine spätere FEES)
- „An Langdock senden“: schickt die Daten an den Webhook des Workflows „Ersttermin“ für alle Module (Einrichtung über ⚙; tinana-ID und Kürzel der Therapeut:in im Sende-Dialog; Name und Geburtsdatum optional weggelassen)
- Beispielfall für die gewählte Diagnosegruppe (Werte aus der Spalte „Beispielwert“; bei SC abwechselnd Erwachsene und Kind), Druckansicht, Hell/Dunkel-Modus

## Aufbau

```
data/HYO_Anamnese_Datenfelder.xlsx   Quelle: Felder, Wertelisten, Module, GUSS-Auswertung
tools/template.html                  Oberfläche und Logik
tools/build.py                       erzeugt index.html aus Excel + Template
index.html                           fertige App (generiert)
dist/demo/index.html                 Demo für GitHub Pages: Banner „DEMO“, ohne Senden und Langdock-Einstellungen
dist/praxis/index.html               Praxisversion für die Raum-Laptops (lokale Datei): ohne Senden, ohne Beispielfall
langdock/                            Bausteine für den Langdock-Workflow „Ersttermin“ (Code-Knoten, Agent-Anweisung, Schema)
langdock/testfaelle/                 vierzehn Testfälle (Abschlussuntersuchung Dysarthrie neu; je Modul ein Ersttermin, Dysphagie mit Kopf-Hals-Tumor, Zwischenbewertungen Dysarthrie, kindliche Dysphagie und Dysphagie)
langdock/beispiele/                  Beispiel-PDFs (Erst-/Zwischenbericht, Arztrückmeldung)
OFFENE_PUNKTE.md                     was noch fehlt (aus tools/offene_punkte.py)
brand/                               Logo und Quicksand-Schrift (von hyo-health.de) für das Branding-PDF
tools/pdf_node_template.js           Layout von Erstbericht und Arztrückmeldung
tools/build_pdf_node.py              erzeugt langdock/4_code_pdf.js mit eingebetteter Schrift und Logo
.github/workflows/pages.yml          baut und veröffentlicht bei jedem Push auf main
```

Felder ändern = Excel bearbeiten, dann neu bauen. Das Build-Skript bricht ab, wenn eine Bedingung nicht lesbar ist oder eine Werteliste fehlt.

```bash
pip install openpyxl
python3 tools/build.py
```

Lokal ansehen: `index.html` direkt im Browser öffnen.

## Offene Punkte

Alles, was vor dem Go-live noch fehlt, steht in [OFFENE_PUNKTE.md](OFFENE_PUNKTE.md) und im Excel auf dem Blatt „Offene Punkte“ (rot = vor Go-live). Gepflegt wird die Liste in `tools/offene_punkte.py`; danach `python3 tools/offene_punkte.py` ausführen.

## Upload bei GitHub (Zip)

1. Zip entpacken. Der Inhalt liegt direkt auf oberster Ebene (kein Unterordner).
2. Auf github.com ein neues **privates** Repository anlegen → „uploading an existing file“.
3. Den gesamten Inhalt des entpackten Ordners ins Fenster ziehen – **inklusive des versteckten Ordners `.github`** (macOS: im Finder Cmd+Shift+. blendet versteckte Dateien ein). Klappt der Ordner beim Drag & Drop nicht, `.github/workflows/pages.yml` über „Add file → Create new file“ mit genau diesem Pfad anlegen und den Inhalt hineinkopieren.
4. „Commit changes“ auf `main`.

Alternativ per Terminal: `git init && git add . && git commit -m "HYO Anamnese" && git branch -M main && git remote add origin <URL> && git push -u origin main`.

## Auf GitHub Pages veröffentlichen

1. Repository wie oben anlegen (oder `git init`, `git add .`, `git commit`, `git push`).
2. Im Repository: **Settings → Pages → Build and deployment → Source: GitHub Actions**.
3. Auf `main` pushen. Der Workflow baut `index.html` aus dem Excel und veröffentlicht sie; die URL steht danach unter Settings → Pages.

Ohne Actions geht es auch: Source „Deploy from a branch“, Branch `main`, Ordner `/ (root)`. Dann wird die eingecheckte `index.html` ausgeliefert – nach Änderungen am Excel lokal neu bauen und mit pushen.

## Datenschutz

GitHub-Pages-Seiten sind öffentlich erreichbar. Die App selbst enthält keine Patientendaten und sendet nichts, trotzdem gilt: Demo – keine echten Patientendaten eingeben. GitHub Pages ist auch bei privaten Repositories (je nach Tarif) öffentlich erreichbar. Für den Praxisbetrieb gehört die Erfassung in die Therapy Engine bzw. das PVS.
