# Testdurchführung – GroceryMate

## 1. Übersicht

### Ziel

Ziel der Testdurchführung ist es, die in der vorherigen Testentwurfsphase definierten Testfälle der Anwendung MarketMate auszuführen. Dabei werden die tatsächlichen Ergebnisse mit den erwarteten Ergebnissen verglichen.

Bei Abweichungen zwischen erwartetem und tatsächlichem Ergebnis wird ein Fehler dokumentiert und als GitHub Issue erfasst.

### Testobjekt

**Anwendung:** MarketMate
**URL:** https://grocerymate.masterschool.com/

### Testzeitraum

[22.09.2026]

### Testerin

[Aylin X, Tester ID 0065]

### Testumgebung

* **Browser:** [Google Chrome Version 153.0.8010.47 Inkognito-Modus/Standardmodus, Firefox Version 155.0.1]
* **Betriebssystem:** [Linux/Ubuntu Version 24.04.5 LTS]
* **Gerät:** [Laptop]
* **Anwendung:** MarketMate
* **URL:** https://grocerymate.masterschool.com/

---

# 2. Testfälle und Testdurchführung

## 2.1 Altersverifikation

### TC-AGE-01 – Genau 18 Jahre

**Testentwurfsverfahren:** Grenzwertanalyse (BVA)

**Eingabe:**
Nutzer ist am heutigen Tag genau 18 Jahre alt.

**Vorbedingung:**
Die Altersverifikation ist erreichbar.

**Testschritte:**

1. Altersverifikation öffnen.
2. Geburtsdatum einer Person eingeben, die am aktuellen Tag genau 18 Jahre alt wird.
3. Eingabe bestätigen.
4. Ergebnis der Altersverifikation überprüfen.

**Erwartetes Ergebnis:**
(gültig für alle Umgebungen)
Die Altersverifikation ist erfolgreich. Alkoholische Produkte können gekauft werden.

**Tatsächliches Ergebnis:**

[Chrome Standardmodus: Verifikation erfolgreich, pop-up Meldung korrekt, alkoholische Getränke sind zum Kauf freigeschaltet
Chrome Inkognito-Modus: Verifikation erfolgreich, pop-up Meldung korrekt, alkoholische Getränke sind zum Kauf freigeschaltet, meldung: 'item added to cart' korrekt
Firefox: wie Chrome Incognito-Modus]
**Status:**
[Chrome Standard: PASSED/ Issues occured see below
Chrome Inkognito PASS
Firefox: PASS]

**Bug**
[Chrome Standardmodus: Fehlermeldung 'Failed to add item to cart' aber das Produkt wurde in den Einkaufswagen hinzugefügt
]

---

### TC-AGE-02 – Knapp unter 18 Jahre

**Testentwurfsverfahren:** Grenzwertanalyse (BVA)

**Eingabe:**
Nutzer ist 17 Jahre und 364 Tage alt. (input 24-09-2008)

**Vorbedingung:**
Die Altersverifikation ist erreichbar.

**Testschritte:**

1. Altersverifikation öffnen.
2. Geburtsdatum einer Person eingeben, die 17 Jahre und 364 Tage alt ist.
3. Eingabe bestätigen.
4. Ergebnis der Altersverifikation überprüfen.

**Erwartetes Ergebnis:**
Die Altersverifikation wird abgelehnt. Alkoholische Produkte können nicht gekauft werden.

**Tatsächliches Ergebnis:**
[Chrome Standard:Meldung:'You are underage. You can still browse the site, but you will not be able to view alcohol products.', Zugriff auf alkoholische Getränke verweigert 'Sorry, no products found!']

**Status:**
[Chrome Standard: PASS 
Chrome Inkognito: PASS
Firefox: PASS]

**Bug**
[Keine Abweichung]

---

### TC-AGE-03 – Knapp über 18 Jahre

**Testentwurfsverfahren:** Grenzwertanalyse

**Eingabe:**
Nutzer ist 18 Jahre und 1 Tag alt.(21-09-2008)

**Vorbedingung:**
Die Altersverifikation ist erreichbar.

**Testschritte:**

1. Altersverifikation öffnen.
2. Geburtsdatum einer Person eingeben, die 18 Jahre und 1 Tag alt ist.
3. Eingabe bestätigen.
4. Ergebnis der Altersverifikation überprüfen.

**Erwartetes Ergebnis:**
Die Altersverifikation ist erfolgreich. Alkoholische Produkte können gekauft werden.

**Tatsächliches Ergebnis:**
[Chrome Standardmodus: Verifikation erfolgreich, pop-up Meldung korrekt, alkoholische Getränke sind zum Kauf freigeschaltet
Chrome Inkognito-Modus: Verifikation erfolgreich, pop-up Meldung korrekt, alkoholische Getränke sind zum Kauf freigeschaltet, meldung: 'item added to cart' korrekt
Firefox: wie Chrome Incognito-Modus]

**Status:**
[PASS / FAIL]

**Bug**
[gleiche Abweichung wie TC 1, 
Chrome Standardmodus: Fehlermeldung 'Failed to add item to cart' aber das Produkt wurde in den Einkaufswagen hinzugefügt
]

---

### TC-AGE-04 – Leere Eingabe

**Testentwurfsverfahren:** Error Guessing

**Eingabe:**
Das Feld für das Geburtsdatum bleibt leer.

**Vorbedingung:**
Die Altersverifikation ist erreichbar.

**Testschritte:**

1. Altersverifikation öffnen.
2. Das Geburtsdatumfeld leer lassen.
3. Eingabe bzw. Formular absenden.
4. Angezeigte Reaktion überprüfen.

**Erwartetes Ergebnis:**
Das System akzeptiert die leere Eingabe nicht und zeigt eine, zum Problem passende Fehlermeldung an.

**Tatsächliches Ergebnis:**
[Chrome Standard, Chrome Inkognito, Firefox : 
Meldung:'You are underage. You can still browse the site, but you will not be able to view alcohol products.', Zugriff auf alkoholische Getränke verweigert 'Sorry, no products found!']


**Status:**
[FAIL]

**Bug**
[Fehlermeldung sollte passend zum Problem sein ('Feld darf nicht freigelassen werde/ field must not be blank')]

---

# 2.2 Bewertungssystem für Produkte

**Voraussetzung für alle Testfälle:**
Der Nutzer ist eingeloggt und hat das zu bewertende Produkt nachweislich gekauft.

### TC-RAT-01 – Bewertung mit 1 Stern

**Testentwurfsverfahren:** Grenzwertanalyse (BVA)

**Eingabe:**
Nutzer gibt genau 1 Stern ab.

**Testschritte:**

1. Einloggen.
2. Ein bereits gekauftes Produkt öffnen.
3. Bewertungsfunktion öffnen.
4. Genau 1 Stern auswählen.
5. Bewertung absenden.
6. Prüfen, ob die Bewertung gespeichert wurde. 
7. Prüfen, ob eine neue Bewertung des gleichen Produkts möglich ist
8. Prüfen, ob die alte Bewertung bearbeitet werden kann
9. Prüfen, ob die Bewertung gelöscht werden kann

**Erwartetes Ergebnis:**
Die Bewertung mit 1 Stern wird akzeptiert und gespeichert. Eine weitere Bearbeitung ist nicht möglich ('You have already reviewed this product'), Bearbeitung ist möglich, Bewertung wird erfolgreich gelöscht

**Tatsächliches Ergebnis:**
[Chrome Standard, Firefox: Das die Zahlfunktion nicht funktioniert, kann auch die Bewertung nicht getestet werden
Chrome Inkognito: Bewertung mit einem Stern erfolgreich, Bewertung wird gespeichert und kann gesehen werden, eine zweite eigentständige Bewertung ist nicht möglich, aber die vorherige kann bearbeitet werden, Bewertung kann gelöscht werden]

**Status:**
[Chrome Standard und Firefox: FAIL
Chrome Inkognito: PASS]

**Bug**
[Die Vorbedingung zur Bewertung (Checkout/Kauf) ist nicht erfüllt, um diesen Test zu testen. Bezahlfunktion funktioniert nicht in Chrome Standard und Firefox]

---

### TC-RAT-02 – Bewertung mit 5 Sternen

**Testentwurfsverfahren:** Grenzwertanalyse

**Eingabe:**
Nutzer gibt genau 5 Sterne ab.

**Testschritte:**

1. Einloggen.
2. Ein bereits gekauftes Produkt öffnen.
3. Bewertungsfunktion öffnen.
4. Genau 5 Sterne auswählen.
5. Bewertung absenden.
6. Prüfen, ob die Bewertung gespeichert wurde.
7. Prüfen, ob eine neue Bewertung des gleichen Produkts möglich ist
8. Prüfen, ob die alte Bewertung bearbeitet werden kann
9. Prüfen, ob die Bewertung gelöscht werden kann

**Erwartetes Ergebnis:**
Die Bewertung mit 5 Sternen wird akzeptiert und gespeichert. Eine weitere Bearbeitung ist nicht möglich ('You have already reviewed this product'), Bearbeitung ist möglich, löschen ist möglich

**Tatsächliches Ergebnis:**
[Chrome Standard, Firefox: Da die Zahlfunktion nicht funktioniert, kann auch die Bewertung nicht getestet werden
Chrome Inkognito: Bewertung mit einem Stern erfolgreich, Bewertung wird gespeichert und kann gesehen werden, eine zweite eigentständige Bewertung ist nicht möglich, aber die vorherige kann bearbeitet werden, Bewertung erfolgreich gelöscht]

**Status:**
[Chrome Standard und Firefox: FAIL
Chrome Inkognito: PASS]

**Bug**
[Die Vorbedingung zur Bewertung (Checkout/Kauf) ist nicht erfüllt, um diesen Test zu testen. Bezahlfunktion funktioniert nicht in Chrome Standard und Firefox]


---

### TC-RAT-03 – Bewertung mit 0 Sternen

**Testentwurfsverfahren:** Grenzwertanalyse / Error Guessing

**Eingabe:**
Nutzer versucht, 0 Sterne abzugeben.

**Testschritte:**

1. Einloggen.
2. Ein bereits gekauftes Produkt öffnen.
3. Bewertungsfunktion öffnen.
4. Versuchen, keine Sterne auszuwählen und die Bewertung abzusenden.
5. Reaktion des Systems überprüfen.

**Erwartetes Ergebnis:**
Eine Bewertung ohne Sterne wird nicht akzeptiert. Das System fordert eine gültige Bewertung zwischen 1 und 5 Sternen. Fehlermeldung 'Invalid input for the field 'Rating'. Please check your input.
' erscheint

**Tatsächliches Ergebnis:**
[Chrome Standard, Firefox: Da die Zahlfunktion nicht funktioniert, kann auch die Bewertung nicht getestet werden
Chrome Inkoknito: Bewertung mit 0 Sternen nicht möglich, Fehlermeldung ist korrekt]

**Status:**
[Chrome Standard, Firefox:FAIL,
Chrome Inkognito: PASS]

**Bug**
[Die Vorbedingung zur Bewertung (Checkout/Kauf) ist nicht erfüllt, um diesen Test zu testen. Bezahlfunktion funktioniert nicht in Chrome Standard und Firefox]


---

### TC-RAT-04 – Bewertung mit zusätzlichem Text

**Testentwurfsverfahren:** Anwendungsfalltest

**Eingabe:**
Nutzer wählt eine Bewertung zwischen 1 und 5 Sternen und fügt einen Text hinzu.

**Testschritte:**

1. Einloggen.
2. Ein bereits gekauftes Produkt öffnen.
3. Bewertungsfunktion öffnen.
4. Eine Bewertung zwischen 1 und 5 Sternen auswählen.
5. Einen Bewertungstext eingeben.
6. Bewertung absenden.
7. Prüfen, ob Sternebewertung und Text gespeichert wurden.
8. Prüfen, ob der Text bearbeitet werden kann und gespiechert wird

**Erwartetes Ergebnis:**
Sternebewertung und Text werden gemeinsam akzeptiert und gespeichert. Bewertung und Text können bearbeitet werden.

**Tatsächliches Ergebnis:**
[Chrome Standard, Firefox: Da die Zahlfunktion nicht funktioniert, kann auch die Bewertung nicht getestet werden
Chrome Inkoknito: Bewertung mit Text wird abgesendet, Bewertung wird gespeichert, Text wird nicht gespeichert. Wenn die Bewertungbearbeutet wird, öffnet sihc ein Feld mit dem Rating und dort, wo der Text sein sollte. der Text ist nicht gespeichert. Wird ein Text dort eingefügt, wird dieser erfolgreichgespeichert und ist sichtbar]

**Status:**
[Chrome Standard, Firefox,
Chrome Inkognito: FAIL ]

**Bug**
[Chrome Standard, Firefox: Da die Zahlfunktion nicht funktioniert, kann auch die Bewertung nicht getestet werden
Chrome Inkognito: Bewertungstext wird bei der ersten Eintragung nicht gespeichert, erscheint erst nachdem die Bewertung bearbeitet und gespeichert wurde]

---

# 2.3 Anpassung der Versandkosten

**Voraussetzung:**
Der Nutzer hat Produkte im Warenkorb und kann den Einkaufswert verändern.

### TC-SHP-01 – Einkaufswert knapp unter 20 €

**Testentwurfsverfahren:** Grenzwertanalyse

**Eingabe:**
Einkaufswert beträgt beispielsweise 19,99 €.

**Testschritte:**

1. Produkte in den Warenkorb legen.
2. Einkaufswert auf 19,99 € einstellen.
3. Warenkorb bzw. Bestellübersicht öffnen.
4. Versandkosten überprüfen.

**Erwartetes Ergebnis:**
Versandkosten werden berechnet.

**Tatsächliches Ergebnis:**
[Chrome Standard/Inkognito, Firefox: Versandkosten werden korrekt berechnet]

**Status:**
[PASS]

**Bug**
[Checkout kann nicht durchgeführt werden, Formular lässt ungültige Datentypen zu: (Adress, City: Erwartete Eingabe: nur Straßennamen und Hausnummern, die existieren, begrenzte Anzahl an Zeichen, keine Sonderzeichen oder ausschließlich Zahlen/Eingabe beginnend mit Zahl, leere Eingab nicht möglich; Feld akzeptiert Zahlen, Sonderzeichen und exterm ggf unendlich lange Eingabe'  ]

---

### TC-SHP-02 – Einkaufswert genau 20 €

**Testentwurfsverfahren:** Grenzwertanalyse (BVA)

**Eingabe:**
Einkaufswert beträgt genau 20,00 €.

**Testschritte:**

1. Produkte in den Warenkorb legen.
2. Einkaufswert auf genau 20,00 € einstellen.
3. Warenkorb bzw. Bestellübersicht öffnen.
4. Versandkosten überprüfen.

**Erwartetes Ergebnis:**
Es werden keine Versandkosten berechnet.

**Tatsächliches Ergebnis:**
[Der Rechnungsbetrag ist korrekt ohne Versandkosten berechnet worden]

**Status:**
[PASS]

**Bug**
[Checkout nicht möglich, Formular erlaubt unpassende Datentypen, Zeichenlängen wie in allen TC]

---

### TC-SHP-03 – Einkaufswert über 20 €

**Testentwurfsverfahren:** Grenzwertanalyse (BVA)

**Eingabe:**
Einkaufswert beträgt beispielsweise 20,01 €.

**Testschritte:**

1. Produkte in den Warenkorb legen.
2. Einkaufswert auf 20,01 € einstellen.
3. Warenkorb bzw. Bestellübersicht öffnen.
4. Versandkosten überprüfen.

**Erwartetes Ergebnis:**
Es werden keine Versandkosten berechnet.

**Tatsächliches Ergebnis:**
[Der Rechnungsbetrag ist korrekt ohne Versandkosten berechnet worden]

**Status:**
[PASS]

**Bug**
[Checkout nicht möglich, Formular erlaubt unpassende Datentypen, Zeichenlängen wie in allen TC]


---

### TC-SHP-04 – Einkaufswert fällt durch Entfernen eines Produkts unter 20 €

**Testentwurfsverfahren:** Anwendungsfalltest

**Eingabe:**
Der Einkaufswert liegt zunächst über 20 €. Durch das Entfernen eines Produkts fällt der Einkaufswert unter 20 €.

**Testschritte:**

1. Produkte in den Warenkorb legen, sodass der Einkaufswert über 20 € liegt.
2. Versandkosten überprüfen.
3. Ein Produkt aus dem Warenkorb entfernen.
4. Prüfen, ob der Einkaufswert unter 20 € fällt.
5. Versandkosten erneut überprüfen.

**Erwartetes Ergebnis:**
Die Versandkosten werden automatisch neu berechnet und wieder hinzugefügt.

**Tatsächliches Ergebnis:**
[Die Versandkosten werden nach Entfernen von Produkten zu einem Einkaufswert unter 20 Euro nicht wieder hinzugefügt]

**Status:**
[FAIL]

**Bug**
[Checkout nicht möglich, Formular erlaubt unpassende Datentypen, Zeichenlängen wie in allen TC
Die Versandkosten werden nicht korrekt hinzugefügt]


---

