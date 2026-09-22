### 1. Altersverifikation

**Testentwurfsverfahren:** Grenzwertanalyse (BVA), Äquivalenzklassenbildung (EP), Error Guessing

**TC-01 – Genau 18 Jahre**

* **Eingabe:** Nutzer ist am heutigen Tag genau 18 Jahre alt.
* **Erwartetes Ergebnis:** Altersverifikation erfolgreich; alkoholische Produkte können gekauft werden.
* **Testentwurf:** Grenzwertanalyse

**TC-02 – Knapp unter 18 Jahre**

* **Eingabe:** Nutzer ist 17 Jahre und 364 Tage alt.
* **Erwartetes Ergebnis:** Altersverifikation wird abgelehnt; alkoholische Produkte können nicht gekauft werden.
* **Testentwurf:** Grenzwertanalyse

**TC-03 – Knapp über 18 Jahre**

* **Eingabe:** Nutzer ist 18 Jahre und 1 Tag alt.
* **Erwartetes Ergebnis:** Altersverifikation erfolgreich; alkoholische Produkte können gekauft werden.
* **Testentwurf:** Grenzwertanalyse

**TC-04 – Leere Eingabe**

* **Eingabe:** Das Feld für das Geburtsdatum bleibt leer.
* **Erwartetes Ergebnis:** Das System akzeptiert die Eingabe nicht und zeigt eine Fehlermeldung an.
* **Testentwurf:** Error Guessing

## 2. Bewertungssystem für Produkte

**Voraussetzung:** Der Nutzer ist eingeloggt und hat das zu bewertende Produkt nachweislich gekauft.

**Testentwurfsverfahren:** Grenzwertanalyse (BVA), Äquivalenzklassenbildung (EP), Error Guessing

### TC-01 – Bewertung mit 1 Stern

* **Eingabe:** Nutzer gibt genau 1 Stern ab.
* **Erwartetes Ergebnis:** Die Bewertung wird akzeptiert und gespeichert.
* **Testentwurf:** Grenzwertanalyse

### TC-02 – Bewertung mit 5 Sternen

* **Eingabe:** Nutzer gibt genau 5 Sterne ab.
* **Erwartetes Ergebnis:** Die Bewertung wird akzeptiert und gespeichert.
* **Testentwurf:** Grenzwertanalyse

### TC-03 – Bewertung mit 0 Sternen

* **Eingabe:** Nutzer versucht, 0 Sterne abzugeben.
* **Erwartetes Ergebnis:** Eine Bewertung mit 0 Sternen wird nicht akzeptiert. Das System fordert eine gültige Bewertung zwischen 1 und 5 Sternen.
* **Testentwurf:** Grenzwertanalyse / Error Guessing

### TC-04 – Bewertung mit zusätzlichem Text

* **Eingabe:** Nutzer wählt eine Bewertung zwischen 1 und 5 Sternen und fügt einen Text hinzu.
* **Erwartetes Ergebnis:** Sternebewertung und Text werden gemeinsam akzeptiert und gespeichert.
* **Testentwurf:** Anwendungsfalltest

## 3. Anpassung der Versandkosten

**Voraussetzung:** Der Nutzer hat Produkte im Warenkorb und kann den Einkaufswert verändern.

**Testentwurfsverfahren:** Grenzwertanalyse (BVA), Anwendungsfalltest

### TC-01 – Einkaufswert knapp unter 20 €

* **Eingabe:** Einkaufswert beträgt z. B. 19,99 €.
* **Erwartetes Ergebnis:** Versandkosten werden berechnet.
* **Testentwurf:** Grenzwertanalyse

### TC-02 – Einkaufswert genau 20 €

* **Eingabe:** Einkaufswert beträgt genau 20,00 €.
* **Erwartetes Ergebnis:** Keine Versandkosten werden berechnet.
* **Testentwurf:** Grenzwertanalyse

### TC-03 – Einkaufswert über 20 €

* **Eingabe:** Einkaufswert beträgt z. B. 20,01 €.
* **Erwartetes Ergebnis:** Keine Versandkosten werden berechnet.
* **Testentwurf:** Grenzwertanalyse

### TC-04 – Einkaufswert fällt durch Entfernen eines Produkts unter 20 €

* **Eingabe:** Der Einkaufswert liegt zunächst über 20 €. Anschließend wird ein Produkt entfernt, sodass der Einkaufswert unter 20 € fällt.
* **Erwartetes Ergebnis:** Die Versandkosten werden automatisch neu berechnet und wieder hinzugefügt.
* **Testentwurf:** Anwendungsfalltest

## Automatisierung der Testfälle

Die meisten der entworfenen Testfälle eignen sich grundsätzlich für eine Automatisierung, da sie klare Eingaben und erwartete Ergebnisse besitzen und wiederholt ausgeführt werden können.

Automatisiert werden sollen insbesondere:

* **Altersverifikation:** Tests für genau 18 Jahre, unter 18 und über 18 sowie ungültige und leere Eingaben.
* **Bewertungssystem:** Bewertungen mit 1 und 5 Sternen, ungültige Bewertungen, Bewertungen mit Text und die Prüfung, ob nicht gekaufte Produkte bewertet werden können.
* **Versandkosten:** Einkaufswerte unter, genau bei und über 20 € sowie die automatische Neuberechnung nach Änderungen des Warenkorbs.

Die Automatisierung reduziert den manuellen Aufwand bei wiederholten Tests, insbesondere bei Regressionstests. Gleichzeitig verursacht die Erstellung und Wartung automatisierter Tests zusätzlichen Aufwand. Daher sollten vor allem häufig wiederholbare und stabile Testfälle automatisiert werden.
