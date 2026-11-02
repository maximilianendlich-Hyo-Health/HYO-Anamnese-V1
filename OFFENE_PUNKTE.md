# Offene Punkte – HYO Anamnese & Erstbericht

Stand: 02.11.2026. Gepflegt in `tools/offene_punkte.py`; dieselbe Liste steht im Excel (Blatt „Offene Punkte“).

## Vor Go-live (29)

| Nr. | Bereich | Offener Punkt | Wo | Wer |
| --- | --- | --- | --- | --- |
| 1 | Fachlich | Fachliche Freigabe aller Datenfeld-Verzeichnisse (alle Module stehen auf ‚Entwurf zur fachlichen Freigabe‘) | Excel, alle Module | Corinna |
| 2 | Fachlich | BIAS A&R: Untertest-Zuordnung, Maximalwerte, Normtabellen (T-Wert, Prozentrang) und Einstufungsgrenzen mit dem Durchführungsbuch abgleichen | BI-07 bis BI-31 | Fachliche Leitung |
| 3 | Fachlich | BoDyS: Formel für den Gesamtschweregrad hinterlegen (Verlagssoftware nicht verfügbar) und Kürzel der Stimmskalen vom Bogen übernehmen | BD-06 bis BD-08, BD-14 | Max |
| 8 | Fachlich | Freigabe-Regel bei FEES (Teambesprechung ab PAS 5, Gegenzeichnung bei FEDSS 5–6/Strukturbefund) in Langdock abbilden | FE-53, Freigabe-Knoten | Corinna, Max |
| 9 | Fachlich | Kö.Be.S. Kids: Bogen besorgen und die Übergangsfelder KB-02 bis KB-13 durch die Ergebnisfelder je Bereich ersetzen (Kinder bis 4 Jahre) | KK-01, KB-02 bis KB-13, KIDYS-S1 | Corinna, Max |
| 10 | Fachlich | Vorgehen bei Hinweisen auf Kindeswohlgefährdung festlegen (Meldeweg, insoweit erfahrene Fachkraft nach § 4 KKG, Dokumentation) | KA-17, KZ-08 (KINDESWOHL) | Corinna, Max, Anwalt Michael |
| 11 | Fachlich | Altersgrenze bei SC bestätigen: unter 18 → kindliche Dysphagie, sonst Erwachsene (z. B. Jugendliche mit neurologischer Dysphagie) | MV-06, App-Logik | Corinna |
| 13 | Fachlich | Kindliche Dysphagie: SOP-Kind-Dysphagie-01 (v0.1) freigeben; Verweise auf SOP-Kapitel und Anhang B/C in den Hinweisen prüfen | Modul KIDYS | Corinna |
| 14 | Fachlich | Gekürzter allgemeiner Teil: Wegfall von Auskunft (wer macht Angaben), Vortherapie, Ereignisdatum, Pflegegrad, Zusatzdiagnosen und persönlichem Ziel fachlich bestätigen (Module fragen sie nicht mehr ab) – v. a. „LSVT LOUD bereits erhalten“ (Dysarthrie) und bisherige Stimmtherapie (Dysphonie) | Blatt ‚Kürzung 02.11.‘ | Corinna |
| 17 | Fachlich | SCZ ist laut Tabelle für Dysphagie und Myofunktion zulässig – vorbelegt wird Dysphagie (Reihenfolge der Tabelle). Passt das, oder bei SCZ Myofunktion zuerst? | Blatt ‚Behandlungsfelder‘ | Corinna |
| 20 | Fachlich | Dysphonie: Normwerte mit ‚[vor Freigabe prüfen]‘ absichern (Lautstärke PB-12, VHI-12-Schweregrade nach Nawka PB-16) | Spalte ‚Normwert / Orientierung‘ | Corinna |
| 21 | Fachlich | Fazialisparese: welche Kontraindikationen (FA-13) gelten für Novafon, welche für thermale Stimulation? Die App weist bisher nur hin (thermal bei gestörter Sensibilität/Kälte, sonst ‚nach SOP 6.3 prüfen‘) | FA-13, FP-04 | Corinna |
| 25 | Lizenzen | Testmaterial und Lizenzen beschaffen bzw. prüfen: BIAS (NAT-Verlag), BoDyS und Kö.Be.S. Kids (Hogrefe), HWL kompakt (© EKN) inkl. Excel-Auswertungsmaske, CPIB-10, CETI, VHI-12, SAQOL-39g, EAT-10, GUSS-Bogen; MoCA-Zertifizierung | Screening-Module | Max |
| 27 | tinana | Sandbox-Zugang: Endpunkte, Feldnamen und Authentifizierung für Patient:in und Verordnung (READ) eintragen; danach TESTMODUS = false | langdock/2_code_tinana_lesen.js (MAPPING) | tinana, Max |
| 28 | tinana | WRITE: Endpunkt, Feldnamen und Ablagekategorien (Befunde, Arztkorrespondenz) für die PDFs | HTTP-Knoten tinana_befund / tinana_arzt | tinana, Max |
| 30 | tinana | Versand der Arztrückmeldung per KIM aus tinana (Backoffice, manuell) als Ablauf festlegen | Benachrichtigung backoffice | Max |
| 31 | tinana | Block 1 (Verwaltung) im Formular aus tinana vorbelegen statt abtippen – braucht Lesezugriff aus dem Formular; bis dahin Block 1 im Formular ausfüllen, Langdock gleicht mit tinana ab | Block 1, VO-26 bis VO-28 | tinana, Max |
| 32 | Langdock | Workflow in Langdock anlegen und mit allen 13 Testfällen durchlaufen (lokal getestet, in Langdock noch nicht) | langdock/testfaelle | Max |
| 33 | Langdock | Agent-Texte fachlich prüfen – je Modul ein Testlauf, insbesondere: erfindet der Agent nichts, stimmen Scores und Empfehlungen? | 3_agent_anweisung.md | Corinna |
| 34 | Langdock | Webhook aus dem Browser (CORS) klären – sonst bleibt der Umweg mit Secret in der URL | Formular ‚An Langdock senden‘ | Langdock |
| 35 | Langdock | Aufbewahrungsdauer der Workflow-Läufe (enthalten Gesundheitsdaten) klären und kürzen | Workflow-Einstellungen | Langdock, Max |
| 37 | Langdock | tinana-API-Schlüssel sicher hinterlegen statt im Code | 2_code_tinana_lesen.js | Langdock, Max |
| 38 | Langdock | Einrichtungsanleitung (Claude-Dokument ‚Langdock-Workflow Ersttermin‘) auf den Stand 02.11. bringen: neue Module, Testfälle, Kürzel im Sende-Dialog | Claude-Dokument | Max |
| 39 | Datenschutz | AV-Verträge mit Langdock und tinana inkl. Verschwiegenheitsverpflichtung (§ 203 StGB) | – | Max, Anwalt Michael |
| 40 | Datenschutz | Verarbeitungsverzeichnis, TOMs und Datenschutz-Folgenabschätzung um Formular und Workflow ergänzen | – | Max, DSB |
| 41 | Datenschutz | Einwilligungstexte für Audio-/Video-/Fotoaufnahmen an VO-28 anpassen, bei Kindern durch die Sorgeberechtigten (VO-27); Videoaufnahme der Mahlzeit (Vertragspaket beim Anwalt) | VO-27, VO-28 | Anwalt Michael |
| 42 | Betrieb | Formular nicht über öffentliches GitHub Pages mit echten Daten nutzen: per Jamf als lokale Datei auf die Raum-Laptops verteilen oder hinter Login hosten | index.html | Max, netgeo |
| 43 | Betrieb | Langdock-Verbindung (Webhook-URL und Secret) auf jedem Raum-Laptop einrichten | Formular ⚙ | Max |
| 45 | Branding | Quicksand als CI-Schrift bestätigen, Fußzeile und Praxisangaben im PDF prüfen | tools/pdf_node_template.js | Max, Rilana |

## Laufend (1)

| Nr. | Bereich | Offener Punkt | Wo | Wer |
| --- | --- | --- | --- | --- |
| 26 | Lizenzen | Keine 1:1-Digitalisierung der Protokollbögen ohne Zustimmung der Verlage (BIAS, BoDyS) – nur Ergebniswerte erfassen | BI-, BD-Felder | Max |

## Später (17)

| Nr. | Bereich | Offener Punkt | Wo | Wer |
| --- | --- | --- | --- | --- |
| 4 | Fachlich | KommPaS: klären, ab wann nutzbar; bis dahin nur Einschätzung VT-01 | VT-02, VT-03, DYSAR-S2 | Fachliche Leitung |
| 5 | Fachlich | Kognitive Kommunikationsstörung: Verlaufsinstrument festlegen (KKS-O1 offen); MoCA nur mit Zertifizierung | Screening KKS | Fachliche Leitung |
| 6 | Fachlich | Red Flags je Störungsbild in den allgemeinen Teil übernehmen (dann entfallen MA-13 und DP-05) | MA-13, DP-05 | Max, Corinna |
| 7 | Fachlich | Aktualität des ärztlichen Kehlkopfbefunds definieren (wie alt darf DP-02 sein?) | DP-02 | Fachliche Leitung |
| 12 | Fachlich | IDDSI-Bezeichnungen praxisweit angleichen (Erwachsene: 1 ‚leicht‘, 2 ‚schwach angedickt‘; Kinder: 1 ‚sehr leicht‘, 2 ‚leicht‘) – offizielle deutsche IDDSI-Übersetzung prüfen | L_IDDSI_GE/SP, L_KOST_GE/SP, L_IDDSI_KIDYS | Corinna |
| 15 | Fachlich | Allergien ‚sonstige‘ ohne Freitext – reicht das (Details in tinana)? | MV-22, MV-24 | Corinna |
| 16 | Fachlich | KKS bisher nur Block MoCA – weitere Felder (MEC, LCQ, CPIB-10, Abschluss) nach Freigabe der SOP-KKS-01 | Blatt ‚Behandlungsfelder‘ | Corinna |
| 18 | Fachlich | Kopf-Hals-Tumor: Feld für die Mundöffnung in mm im Befund fehlt (DA-30 verweist darauf, SOP-KHT-01 6.3) – in die KSU aufnehmen? | KS-Block, DA-30 | Corinna |
| 19 | Fachlich | Dysphagie v3: ‚Zwischenbewertung angelegt‘ als Zwischen- bzw. Abschlussuntersuchung umgesetzt (Umschalter oben); weitere Anlässe (Verschlechterung, nach FEES) über SZ-02 – passt das? | SZ-01, SZ-02 | Corinna |
| 22 | Fachlich | Fazialisparese: eigene Listen Fortschritt (deutlich/gering) und Entscheidung (Fazialis-Zentrum, Rücksprache) – so lassen oder an die praxisweiten Listen angleichen? | FZ-07, FZ-08 | Corinna |
| 23 | Fachlich | Abschlussuntersuchung: nutzt dieselben Felder wie die Zwischenuntersuchung (Entscheidung mit ‚Abschluss‘ vorbelegt). Eigene Abschlussfelder je Modul nötig (z. B. Empfehlungen nach Therapieende, Eigenübungsprogramm)? | VO-25, SZ/AZ/DZ/MZ/PZ/KZ/FZ/SV | Corinna |
| 24 | Fachlich | Sprechapraxie: feste Wortliste für die Zwischenbewertung (geübte/ungeübte Wörter, SV-03/04) festlegen | SV-03, SV-04 | Corinna |
| 29 | tinana | Rohdaten (JSON) zusätzlich zu PDFs übermitteln – Voraussetzung für Verläufe (FEES später, Zwischenbewertungen, Messzeitpunkte) | Export ‚felder‘ | tinana |
| 36 | Langdock | Freigaben gezielt an Personen senden (z. B. Fachliche Leitung nur bei FEES) – Empfängerliste gilt sonst für den ganzen Workflow | Freigabe-Knoten | Langdock |
| 44 | Betrieb | Terminart für FEES an einem eigenen Termin ergänzen (bisher: Ersttermin + ‚JSON laden‘) | VO-25 | Max |
| 46 | Branding | Unterschrift im PDF mit vollem Namen statt Kürzel (Zuordnung Kürzel → Name) | Sende-Dialog (Kürzel), PDF | Max |
| 47 | Dokumentation | Älteres Google-/Claude-Dokument ‚HYO Health – Anamnesebogen‘ und der Logikbaum vom 23.10. sind veraltet – Excel ist die Quelle | Doc vom 23.10.2026 | Max |
