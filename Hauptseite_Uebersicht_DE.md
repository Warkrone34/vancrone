# Vancrone Startseiten-Leitfaden & Funktionsübersicht

> Dieses Dokument ist das offizielle Benutzerhandbuch zu Startbildschirm, Garantieverwaltung, Tools und Sicherheitsfunktionen von Vancrone. Letzte Aktualisierung: 15. Oktober 2026.

---

## 1. Überblick & Offline-First-Architektur

Vancrone ist ein unabhängiges digitales Inventar und ein Tresor, der Garantiefristen, Rückgabefristen, Rechnungen und Eigentumsnachweise für Ihre Einkäufe verwaltet. Die aktuelle Version ist kostenlos: Alle Funktionen stehen ohne Einschränkungen zur Verfügung, es gibt keine Werbung und keine In-App-Käufe.

- **Offline & lokale Speicherung:** Ihre Einträge, Rechnungen und Fotos verlassen Ihr Gerät nie; es gibt keinen Vancrone-Server, kein Benutzerkonto und keine Cloud-Datenbank. An Google Firebase Crashlytics gehen nur Absturzberichte ohne Ihre Inhalte; Sie können dies unter **Einstellungen > Über > Absturzberichte** abschalten (siehe Datenschutzerklärung).
- **Verschlüsselter lokaler Tresor:** Ihre Einträge werden in einer mit AES-256 verschlüsselten Datenbank (SQLCipher) gespeichert. Rechnungsfotos, Dokumente und Videos liegen im privaten Speicherbereich der App auf Ihrem Gerät.
- **Eigenverantwortung & Sicherungen:** Da Ihre Daten nur auf Ihrem Gerät existieren, sind Sie für regelmäßige Sicherungen verantwortlich. Geht Ihr Gerät verloren, wird es zurückgesetzt oder beschädigt, kann der Entwickler Ihre Daten nicht wiederherstellen. Speichern Sie über **Einstellungen > Datenverwaltung > Backup (Exportieren)** eine verschlüsselte `.vcb`-Datei – auf Wunsch mit Passwort – an einem Ort Ihrer Wahl und holen Sie sie mit **Wiederherstellen (Importieren)** auf dasselbe oder ein neues Telefon zurück.

---

## 2. Obere App-Leiste

- **Kalender:** Das Kalendersymbol öffnet einen Monatskalender mit den Ablaufdaten Ihrer Garantien. Tippen Sie auf einen Tag, um die an diesem Tag ablaufenden Produkte zu sehen.
- **Benutzerhandbuch & FAQ:** Das Fragezeichensymbol öffnet Antworten zu Sicherungen, Datenschutz, Scannen, Berichten und mehr.
- **Auswahlmodus:** Halten Sie eine Garantiekarte gedrückt, um die Auswahl zu starten. Die obere Leiste zeigt dann die Anzahl der ausgewählten Produkte und ermöglicht es, alle auf einmal in den Papierkorb zu verschieben oder die Auswahl abzubrechen.

---

## 3. Karte „Abgesicherte Anlagen“

Die Karte oben in der Liste zeigt den Gesamtwert Ihrer erfassten Produkte.

- **Summen je Währung:** Beträge werden für jede Währung getrennt addiert (z. B. ₺, $, €, ¥); Währungen werden nicht ineinander umgerechnet.
- **Aufschlüsselung:** Tippen Sie auf die Karte, um die Aufschlüsselung nach Währungen ein- oder auszublenden.

---

## 4. Suchen, Sortieren & Filtern

- **Suchleiste:** Filtert die Liste während der Eingabe nach Produktname oder Kategorie. Mit Schaltfläche zum schnellen Löschen.
- **Sortier-Chips:** **Hinzugefügt am**, **Ablaufdatum** und **Name**. Tippen Sie erneut auf den aktiven Chip, um die Reihenfolge umzukehren.
- **Währungsfilter:** Zeigt **Alle Produkte** oder nur die Produkte einer bestimmten Währung.

---

## 5. Garantiekarten

Jede Karte zeigt Produktbild oder Symbol, Produktname, Kategorie (Elektronik, Kleidung & Mode, Haus & Wohnen, Automobil, Körperpflege, Sonstiges), Preis und ein Countdown-Abzeichen:

- **Themenfarbe:** 30 Tage oder mehr verbleibend.
- **Orange:** weniger als 30 Tage verbleibend.
- **Rot:** weniger als 3 Tage verbleibend. In den letzten 24 Stunden zählt das Abzeichen in Stunden, Minuten und Sekunden herunter.
- **Dunkelrot:** Die Garantie ist abgelaufen.

Tippen Sie auf eine Karte, um die Produktdetails zu öffnen; halten Sie sie gedrückt, um den Auswahlmodus zu starten. Garantieenddaten enthalten auch eine per QR-Übertragung übernommene zusätzliche Garantiezeit.

---

## 6. Produkte hinzufügen (+-Schaltfläche)

Die `+`-Schaltfläche unten rechts bietet drei Optionen:

- **Manuell hinzufügen:** Ein Formular für Produktname, Symbol, Preis und Währung, Kategorie, Ablaufdatum, **Rückgaberecht** (Anzahl Tage) und **Nutzungsintensität**. Unter **Dokumente & Beweise** können Sie eine Rechnung, ein Garantiedokument (Bild oder PDF bis 25 MiB), ein Produktbild und ein Beweisvideo anhängen sowie festhalten, wo die Papierkopie aufbewahrt wird. Der **Serien-Eingabemodus** lässt das Formular nach dem Speichern geöffnet, sodass Sie mehrere Produkte nacheinander erfassen können.
- **Garantie-Scan (Beta):** Fotografieren oder wählen Sie einen Kassenbon, eine Rechnung oder ein Garantiedokument. Der Text wird auf Ihrem Gerät gelesen, und Produktname, Preis, Währung und Daten werden vorgeschlagen; nicht eindeutig angegebene Werte werden als „Geschätzt“ markiert. Gleichen Sie die Felder vor dem Speichern immer mit dem Original ab.
- **Thermobeleg-Retter:** Macht verblasste Thermobelege mit Kontrast- und Schärfefiltern besser lesbar und bewahrt die Ergebnisse in einem eigenen Archiv auf.

Beim Herunterscrollen erscheint eine Schaltfläche, die Sie an den Anfang der Liste zurückbringt.

---

## 7. Produktdetails

- **Dokumente:** Rechnung und Garantiedokument in voller Größe ansehen.
- **Mögliche Rückgabe Aktiv:** Zeigt die verbleibenden Tage der von Ihnen eingegebenen Rückgabefrist. Rückgabebedingungen variieren je nach Land und Kategorie.
- **Beweisvideo:** Das mit Zeitstempel versehene Beweisvideo abspielen oder herunterladen.
- **Serviceverlauf:** Serviceeinträge mit Titel, Beschreibung und Kosten hinzufügen.
- **Optionsmenü:** **Bearbeiten**, **Teilen / Verkaufsanzeige** (kopiert einen fertigen Verkaufstext), **PDF-Zertifikat erstellen**, **Beweisvideo teilen**, **Übertragen (Air Gap)** per QR-Code an ein anderes Telefon, **Wo ist die physische Kopie?** und **Löschen** (verschiebt das Produkt in den Papierkorb).

---

## 8. Untere Navigationsleiste

- **Garantien (Start):** Ihre Inventarliste und die Karte „Abgesicherte Anlagen“.
- **Analysen:** Gesamtanlagewert, nahende Ablaufdaten, Anzahl der Produkte, durchschnittliche Garantielebensdauer, wertvollstes Produkt, Kategorieverteilung und monatliche Garantie-Einträge der letzten 6 Monate. Alle Berechnungen erfolgen auf Ihrem Gerät.
- **Tools:**
  - **Übertragung empfangen (Air Gap):** Scannen Sie den QR-Code auf dem sendenden Telefon, um das Produkt hinzuzufügen. Der QR-Code enthält Produktname, Preis, Währung, Daten, zusätzliche Garantiezeit und Kategorie in lesbarer Form; Fotos und Dokumente werden nicht übertragen.
  - **Thermobeleg-Retter**
  - **PDF-Zertifikat:** Erstellt einen PDF-Inventarbericht über alle Ihre Produkte.
  - **Excel (CSV)-Export:** Exportiert Ihr Inventar als Tabelle.
  - **Inventarvideo** und **Design & Erscheinungsbild:** Kurze Anleitungen zur Beweisvideo-Funktion und zu den Darstellungseinstellungen.
- **Einstellungen:**
  - **Allgemein:** Design (Systemstandard, hell, dunkel), Themenakzent, animierter Hintergrund, Sprache und Benachrichtigungen.
  - **Datenverwaltung:** Backup (Exportieren), Wiederherstellen (Importieren), Papierkorb (Produkte wiederherstellen oder endgültig löschen) und Alle Daten löschen (mit doppelter Bestätigung).
  - **Über:** Fehler melden & Feedback, Absturzberichte, Rechtliche Hinweise & Datenschutz und Version.

---

## 9. Benachrichtigungen & Startbildschirm-Widget

- **Erinnerungen:** Mit Benachrichtigungsberechtigung erinnert Vancrone Sie 30, 7, 3 und 1 Tag vor Garantieende und am letzten Tag, 2 Tage vor Ende einer Rückgabefrist sowie regelmäßig an eine Sicherung. Gelegentlich kommen Tipps und saisonale Nachrichten hinzu. Die Zustellung hängt von den Akku- und Benachrichtigungseinstellungen Ihres Telefons ab.
- **Widget:** Fügen Sie das Vancrone-Widget zum Startbildschirm hinzu, um ohne Öffnen der App zu sehen, wie viele Produkte sicher, bald ablaufend oder kritisch sind.

---

## 10. Sicherheitshinweise

- **Gerootete Geräte:** Werden Anzeichen für Root-Zugriff erkannt, zeigt Vancrone eine Warnung; Sie können auf eigenes Risiko fortfahren oder die App beenden.
- **Verlorener Verschlüsselungsschlüssel:** Wird der Verschlüsselungsschlüssel des Telefons unbrauchbar, bewahrt Vancrone die nicht lesbaren Einträge in einem separaten Ordner auf und bietet an, eine Sicherung wiederherzustellen oder mit einem leeren Tresor zu beginnen.

---

## 11. Support & Feedback

- Über **Einstellungen > Über > Fehler melden & Feedback** können Sie Fehlerberichte oder Vorschläge senden (höchstens zwei pro Tag). Ihre Nachricht, die optional angegebene E-Mail-Adresse sowie grundlegende Geräte- und App-Versionsinformationen werden an den Entwickler übermittelt.
- Sie erreichen den Entwickler auch über den verifizierten Eintrag im Google Play Store.
- *Zum Schutz vor Spam-Crawlern und automatisierten Bots werden in diesem Leitfaden bewusst keine E-Mail-Adressen im Klartext veröffentlicht.*
