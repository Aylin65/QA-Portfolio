1. Produktanalyse
1.1 Zielsetzung

Market Mate ist ein Online-Webshop, der es Nutzerinnen und Nutzern ermöglicht, Lebensmittel und Produkte des täglichen Bedarfs bequem online zu bestellen und nach Hause liefern zu lassen.

Das Produktsortiment umfasst unter anderem:

* frische Lebensmittel
* Tiernahrung
* Reinigungsmittel
* alkoholische Getränke

Das Ziel des Produkts ist es, den Einkauf von Produkten des täglichen Bedarfs einfacher, schneller und bequemer zu gestalten. Nutzer sollen Produkte online auswählen, in den Warenkorb legen, bestellen und die Lieferung zu ihnen nach Hause erhalten können.
Aus Sicht des Tests soll insbesondere sichergestellt werden, dass die neuen Funktionen des nächsten Releases zuverlässig funktionieren und den Bestellprozess nicht negativ beeinflussen. Dabei sollen sowohl die korrekte Funktionalität als auch die Benutzerfreundlichkeit und die Auswirkungen auf bestehende Shop-Funktionen berücksichtigt werden.

1.2 Nutzerzielgruppe
Market Mate richtet sich grundsätzlich an alle Personen, die Lebensmittel und Produkte des täglichen Bedarfs online bestellen und nach Hause liefern lassen möchten.
Eine besondere Einschränkung gilt für **alkoholische Getränke**: Diese dürfen nur von Personen ab 18 Jahren bestellt werden.

1.3 Hardware- und Software-Spezifikationen

1.3.1 Hardwareanforderungen:

* **Geräte:** PCs, Laptops, Smartphones und Tablets
* **Spezifikationen:** Standardkonfigurationen für Android- und iOS-Geräte; Desktop-PCs und Laptops mit mindestens 4 GB RAM und 2 GHz Prozessor

1.3.2 Softwareanforderungen:

* **Betriebssysteme:** Windows, Linux, macOS, Android, iOS
* **Browser:** Chrome, Firefox, Safari, Edge
* **Abhängigkeiten:** Backend-Dienste, Zahlungsschnittstellen und ggf. externe Liefer- oder Authentifizierungsdienste

1.4 Funktionalität 

Market Mate bietet grundlegende Funktionen eines Online-Lebensmittelshops, darunter:

* Registrierung und Login
* Produktsuche und Kategorisierung
* Favoritenverwaltung
* Warenkorb
* Bestellabschluss mit Versand- und Zahlungsinformationen

Für das nächste Release stehen folgende **neue Funktionen** im Fokus des Tests:

1. **Bewertungssystem für Produkte** – Nutzer können Produkte mit 1 bis 5 Sternen bewerten.
2. **Altersverifikation für alkoholische Produkte** – Vor dem Kauf alkoholischer Produkte wird das Alter des Nutzers überprüft.
3. **Anpassung der Versandkosten** – Die Versandkosten werden abhängig vom Einkaufswert berechnet. Ab einem Einkaufswert von 20 € ist die Lieferung kostenlos.

**2. Teststrategie entwerfen**

 2.1 Testumfang (Scope of Testing)

**Im Umfang enthalten**

Im Rahmen des nächsten Releases werden insbesondere die drei neuen Funktionen getestet:

**2.1.1 Bewertungssystem für Produkte**

* Abgabe einer Bewertung mit 1 bis 5 Sternen
* Prüfung, ob Bewertungen korrekt gespeichert werden
* Prüfung, ob abgegebene Bewertungen korrekt angezeigt werden
* Prüfung ungültiger bzw. fehlender Eingaben
* Prüfung, ob Bewertungen nur für geeignete Produkte bzw. durch berechtigte Nutzer abgegeben werden können

**2.1.2 Altersverifikation für alkoholische Produkte**

* Eingabe eines gültigen Geburtsdatums für volljährige Nutzer
* Eingabe eines Geburtsdatums für minderjährige Nutzer
* Prüfung des vorgegebenen Datumsformats
* Prüfung, ob minderjährige Nutzer vom Kauf alkoholischer Produkte ausgeschlossen werden
* Prüfung, ob volljährige Nutzer nach erfolgreicher Verifikation Zugriff auf alkoholische Produkte erhalten

**2.1.3 Anpassung der Versandkosten**

* Berechnung der Versandkosten bei einem Einkaufswert unter 20 €
* Prüfung des Grenzwerts von genau 20 €
* Prüfung, ob ab 20 € Einkaufswert kostenloser Versand berechnet wird
* Prüfung der korrekten Gesamtsumme aus Produktpreisen und Versandkosten
* Prüfung der Versandkosten bei Änderung der Produktmenge

**2.1.4 Nicht im Umfang enthalten**

* Vollständiger Test bereits bestehender Funktionen wie Registrierung, Login, Favoriten und Produktsuche
* Vollständige Prüfung des Zahlungssystems
* Prüfung externer Zahlungsanbieter
* Prüfung der tatsächlichen Auslieferung und Logistik

**2.2 Geplante Testarten**

Für die drei neuen Funktionen werden folgende Testarten durchgeführt:

* **Funktionale Tests:** Prüfung, ob Bewertungssystem, Altersverifikation und Versandkostenberechnung wie vorgesehen funktionieren.
* **Regressionstests:** Prüfung, ob die neuen Funktionen bestehende Funktionen des Shops, insbesondere Warenkorb und Bestellprozess, nicht negativ beeinflussen.
* **Usability-Tests:** Prüfung, ob die neuen Funktionen für Nutzer verständlich und einfach zu bedienen sind.
* **Abnahmetests (UAT):** Prüfung, ob die neuen Funktionen die fachlichen Anforderungen erfüllen und für die Nutzung freigegeben werden können.
* **Sicherheitstests:** Prüfung der Altersverifikation und der Bewertungseingaben auf mögliche unberechtigte Zugriffe oder Manipulationen.

**2.3 Risiken und Gegenmaßnahmen**

* **Fehlerhafte Altersverifikation**
  Gegenmaßnahme: Tests mit volljährigen und minderjährigen Geburtsdaten sowie Grenzfällen durchführen.

* **Fehlerhafte Versandkostenberechnung**
  Gegenmaßnahme: Verschiedene Einkaufswerte testen, insbesondere Werte unter, genau bei und über 20 €.

* **Bewertungen werden nicht korrekt gespeichert**
  Gegenmaßnahme: Bewertung abgeben und anschließend prüfen, ob sie nach einem Seitenwechsel weiterhin vorhanden ist.

* **Neue Funktionen beeinflussen bestehende Funktionen**
  Gegenmaßnahme: Regressionstests für Warenkorb und Bestellprozess durchführen.

* **Fehlende oder ungeeignete Testdaten**
  Gegenmaßnahme: Geeignete Testdaten für verschiedene Altersgruppen, Einkaufswerte und Bewertungen vorbereiten.

**2.4 Testlogistik (Testverantwortlichkeiten)**

* **Testmanager:** Verantwortlich für die Testplanung, Koordination und Überwachung des Testprozesses.
* **QA Engineer:** Verantwortlich für die Erstellung und Durchführung der funktionalen Tests und Regressionstests.
* **QA Engineer:** Verantwortlich für Usability- und Sicherheitstests.
* **Entwicklungsteam:** Verantwortlich für die Behebung von gefundenen Fehlern und die Unterstützung bei technischen Fragen.
* **Endanwender:** Durchführung des Abnahmetests und Prüfung der neuen Funktionen aus Nutzersicht.

**3. Testziele definieren**

**3.1 Ziele**

* **Bewertungssystem:** Sicherstellen, dass Nutzer Produkte mit 1 bis 5 Sternen bewerten können und die Bewertungen korrekt gespeichert und angezeigt werden.
* **Altersverifikation:** Sicherstellen, dass das Alter bei alkoholischen Produkten korrekt überprüft wird und minderjährige Nutzer keinen Zugriff auf diese Produkte erhalten.
* **Versandkosten:** Sicherstellen, dass die Versandkosten abhängig vom Einkaufswert korrekt berechnet werden und ab einem Einkaufswert von 20 € entfallen.
* **Benutzerfreundlichkeit:** Sicherstellen, dass die neuen Funktionen verständlich und einfach zu bedienen sind.
* **Regression:** Sicherstellen, dass die neuen Funktionen bestehende Funktionen des Webshops nicht negativ beeinflussen.

**3.2 Erwartete Ergebnisse**

* Bewertungen von 1 bis 5 Sternen können erfolgreich abgegeben und gespeichert werden.
* Die Altersverifikation unterscheidet korrekt zwischen volljährigen und minderjährigen Nutzern.
* Die Versandkosten werden für unterschiedliche Einkaufswerte korrekt berechnet.
* Ab einem Einkaufswert von 20 € werden keine Versandkosten berechnet.
* Die neuen Funktionen sind für Nutzer verständlich und ohne unnötige Fehler bedienbar.
* Bestehende Funktionen des Shops bleiben durch die neuen Funktionen funktionsfähig.

** 4. Testkriterien definieren**

** 4.1 Aussetzungskriterien (Suspension Criteria)**

Die Tests werden vorübergehend ausgesetzt, wenn:

* die Testumgebung nicht verfügbar ist oder technische Probleme aufweist.
* ein kritischer Fehler die Durchführung weiterer Tests verhindert.
* benötigte Testdaten oder Testkonten nicht verfügbar sind.

** 4.2 Abnahmekriterien (Exit Criteria)**

Die Tests gelten als erfolgreich abgeschlossen, wenn:

* alle geplanten Testfälle für die drei neuen Funktionen durchgeführt wurden.
* die grundlegenden Funktionen des Bewertungssystems, der Altersverifikation und der Versandkostenberechnung erfolgreich funktionieren.
* keine kritischen oder hochpriorisierten Fehler offen sind.
* die Grenzfälle der Versandkostenberechnung und Altersverifikation getestet wurden.
* die neuen Funktionen den definierten Anforderungen entsprechen.
* der Abnahmetest erfolgreich abgeschlossen wurde.

**5. Ressourcenplanung**

**5.1 Personelle Ressourcen**
* Testmanager für Planung und Koordination
* QA Engineer für funktionale Tests und Regressionstests
* QA Engineer für Usability- und Sicherheitstests
* Entwicklerteam zur Fehlerbehebung und technischen Unterstützung
* Endanwender für den Abnahmetest (UAT)

**5.2 Hardware**
* Desktop-PCs und Laptops
* Smartphones mit Android und iOS
* Tablets

**5.3 Software**
* Chrome
* Firefox
* Safari
* Edge
* Windows, Linux, macOS, Android und iOS
* Testmanagement- und Testautomatisierungswerkzeuge

**5.4 Infrastruktur**
* Testumgebung für die Webanwendung
* Stabile Internetverbindung
* Testdatenbank mit vorbereiteten Testkonten und Produkten
* Testsystem zur Durchführung der automatisierten Tests
* Tools zur Fehlererfassung und Dokumentation

**6. Testumgebung planen**

* **Testgeräte:** PCs, Laptops, Smartphones und Tablets mit unterschiedlichen Betriebssystemen und Browsern.
* **Browser:** Chrome, Firefox, Safari und Edge.
* **Betriebssysteme:** Windows, Linux, macOS, Android und iOS.
* **TEST-Umgebung:** Durchführung der funktionalen Tests, Regressionstests, Usability-Tests und Sicherheitstests.
* **ACC-Umgebung:** Durchführung des Abnahmetests.
* **PROD-Umgebung:** Wird erst nach erfolgreichem Abschluss der Tests und Freigabe verwendet.

**7 Zeitplan und Aufwandsschätzung**

**8. Testartefakte (Test-Deliverables)**

* Testplandokument
* Testfälle und Testdaten
* Testprotokolle und Fehlerberichte
* Testabschlussbericht
* UAT-Freigabe
