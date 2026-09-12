# Vancrone Startseite & Funktionsübersicht

> Dieses Dokument ist das offizielle Benutzerhandbuch, das die Architektur der Startseite, den Garantie-Tracking-Mechanismus und die Sicherheitsfunktionen von Vancrone erläutert. Letzte Aktualisierung: 12. September 2026.

---

## 1. Übersicht & Offline-First-Architektur

Vancrone ist ein unabhängiges digitales Inventar- und Tresorwerkzeug zur sicheren Erfassung von Garantiefristen, Rechnungen, Seriennummern und Eigentumsnachweisen für Ihre gekauften Produkte.

- **Vollständig offline & lokale Speicherung:** Vancrone überträgt Ihre persönlichen Daten niemals an externe Server oder Cloud-Datenbanken. Abhängigkeiten von externen Cloud-APIs (einschließlich Google Drive API) wurden vollständig entfernt.
- **Verschlüsselter lokaler Tresor:** Alle Produktdaten, Rechnungsfotos und Anhänge werden ausschließlich auf Ihrem Gerät mit Room SQLCipher verschlüsselt gespeichert.
- **Verantwortung des Nutzers & Datensicherung:** Da alle Daten ausschließlich lokal auf Ihrem Gerät liegen, sind Sie selbst für regelmäßige Sicherungen verantwortlich. Bei Geräteverlust, Zurücksetzen auf Werkseinstellungen oder Beschädigung kann der Entwickler keine Daten wiederherstellen. Nutzen Sie **Einstellungen > Datensicherheit & Backup**, um regelmäßig eine verschlüsselte `.vcb`-Sicherungsdatei auf externen Speicher oder USB-Sticks zu exportieren.

---

## 2. Obere Menüleiste & Schnellnavigation

Die Vancrone-Top-Bar am oberen Bildschirmrand bietet optimierte Navigation und Stapelverwaltungsfunktionen:

- **App-Titel & Abo-Status:** Ein Tippen scrollt die Liste sanft nach ganz oben. Zeigt dynamisch den aktiven Tarif (PRO / BUSINESS) an.
- **Kalenderansicht:** Über das Kalendersymbol oben rechts behalten Sie alle bevorstehenden Garantieabläufe in einer Monatsübersicht im Blick.
- **Häufig gestellte Fragen (FAQ):** Das Fragezeichen-Symbol führt direkt zu integrierten Leitfäden, Tipps und Anleitungen.
- **Mehrfachauswahl-Modus:** Durch langes Drücken auf eine beliebige Garantiekarte wird der Auswahlmodus aktiviert. Wählen Sie mehrere Artikel aus und verschieben Sie diese mit einem Klick in den Papierkorb.

---

## 3. Mehrwährungs-Vermögens- & Garantiewert-Karte

Diese dynamische Farbverlaufskarte am Kopf der Liste gibt Ihnen sofortigen Überblick über den Gesamtwert Ihrer geschützten Gegenstände:

- **Hauptwährungs-Berechnung:** Berechnet den aktuellen Gesamtwert aller aktiven Garantien basierend auf Ihrer ausgewählten Standardwährung (z. B. €, $, ₺, ¥).
- **Mehrwährungs-Aufschlüsselung:** Ein Tippen auf die Karte öffnet eine Übersicht über Ausgaben, die in anderen Währungen (EUR, USD, GBP, CHF usw.) erfasst wurden.
- **Sicherheits-Badge:** Symbolisiert den lokalen Schutz Ihres Tresors durch moderne Geräteverschlüsselung.

---

## 4. Suche, Filter & Dynamische Sortierung

Finden Sie jeden Gegenstand in Sekundenschnelle mit durchdachten Verwaltungswerkzeugen:

- **Echtzeit-Suchleiste:** Filtert die Liste bereits während des Tippens nach Produktnamen, Händlern oder Seriennummern. Mit Ein-Klick-Löschtaste.
- **Sortier-Chips:**
  - **Hinzugefügt am:** Chronologische Sortierung nach Erfassungsdatum (aufsteigend oder absteigend).
  - **Ablaufdatum:** Zeigt bald ablaufende Garantien ganz oben an, damit Sie Garantieansprüche und Rückgabefristen rechtzeitig wahrnehmen können.
  - **Name:** Alphabetische Reihenfolge von A bis Z oder Z bis A.
- **Währungsfilter:** Ein Dropdown-Filter zur Anzeige von Produkten einer bestimmten Währung.

---

## 5. Intelligente Garantie- & Inventarkarten

Jede Produktkarte liefert die wichtigsten Daten auf einen Blick:

- **Visuelle Kennzeichnung:** Hochauflösendes Produktfoto oder anpassbares Kategoriesymbol.
- **Produktinformationen:** Artikelname, Kategorie (Elektronik, Kleidung, Haushalt & Wohnen, Kfz, Körperpflege, Sonstiges) und Kaufpreis.
- **Intelligenter Countdown-Badge (Farblich kodiert):**
  - **Grün / Akzentfarbe:** Sicherer Status mit mehr als 30 verbleibenden Tagen.
  - **Orange:** Aufmerksamkeit erforderlich; weniger als 30 Tage Restzeit.
  - **Rot (Warnung):** Kritische Frist (< 3 Tage). Am letzten Tag aktiviert sich ein Live-Countdown mit Stunden, Minuten und Sekunden.
  - **Dunkelrot:** Abgelaufene Garantien.
- **Direkte Interaktionen:** Ein kurzes Antippen öffnet die Detailansicht (Originalrechnungen, Seriennummer, Barcode, Garantiebedingungen). Langes Drücken aktiviert die Mehrfachauswahl.

---

## 6. Schwebender Aktions-Button (FAB)

Über das ausklappbare `+`-Symbol unten rechts erfassen Sie neue Einträge:

- **Manuell hinzufügen:** Ein detailliertes Formular für Produktbezeichnung, Kategorie, Kaufdatum, Garantiedauer, Zusatzgarantie, Rückgaberecht, Seriennummern, Rechnungsfotos und PDF-Dokumente.
- **Beleg-Retter (Fiş Kurtarıcı):** Ein spezielles Fotorestaurierungs-Tool mit Bildfiltern, um verblassende Thermopapier-Kassenbons zu beschneiden, zu schärfen und lesbar zu machen.
- **Nach oben scrollen:** Ein praktischer Schnellbutton, der beim Herunterscrollen erscheint und Sie sofort an den Listenanfang zurückbringt.

---

## 7. Moderne Schwebende Navigationsleiste (Unten)

Wechseln Sie mühelos zwischen den Hauptbereichen der App:

- **Garantien (Startseite):** Ihre zentrale Inventarübersicht und das Kontrollzentrum.
- **Analyse:** Ausgabenverteilung, Kategoriestatistiken und ein interaktives Liniendiagramm für monatliche Garantie-Einträge.
- **Werkzeuge:** QR-/Barcode-Scanner, P2P-Garantietransfer zwischen Geräten, Video-Inventartour und Papierkorb.
- **Einstellungen:** Farbthemen, Währungsauswahl, Benachrichtigungen sowie verschlüsselte Sicherung und Wiederherstellung (`.vcb`) über Android SAF.

---

## 8. Kundendienst & Feedback

Wenn Sie eine Frage haben, einen Fehler melden möchten oder einen Verbesserungsvorschlag einbringen wollen:

- Öffnen Sie die App unter **Einstellungen > Über > Fehler melden & Feedback**.
- Das integrierte Formular übermittelt Ihre Rückmeldung direkt und sicher an das Entwicklerteam.
- Sie können den Entwickler auch über den verifizierten Eintrag im Google Play Store kontaktieren.
- *Zum Schutz vor Spam-Bots und automatisierten Crawlern werden E-Mail-Adressen in den Dokumenten bewusst nicht als Klartext veröffentlicht.*
