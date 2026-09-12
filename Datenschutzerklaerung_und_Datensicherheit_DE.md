# Datenschutzerklärung & Datensicherheit

> Dieses Dokument ist die vollständige deutsche Erklärung zu den Datenverarbeitungsgrundsätzen, Sicherheitsmaßnahmen und Datenschutzstandards der Anwendung Vancrone. Letzte Aktualisierung: 11. September 2026.

## 1. Einleitung

Diese Datenschutzerklärung beschreibt den Umgang mit Informationen im Zusammenhang mit der Android-Anwendung Vancrone. Wir haben diese Erklärung auf einem zentralen Grundsatz aufgebaut: Wir, der Entwickler, sehen, erfassen oder speichern Ihre persönlichen Inventardaten, Garantien, Rechnungen oder Fotos zu keinem Zeitpunkt. Diese Erklärung erläutert die technischen Details und beschreibt die begrenzten Daten, die von Drittanbietern verarbeitet werden.

Verantwortlicher: Vancrone wird von einem unabhängigen Einzelentwickler entwickelt und veröffentlicht (im Folgenden „Entwickler“). Der Entwickler ist unter vancrone.app@gmail.com erreichbar; verifizierte Angaben zum Herausgeber sind im Google Play Store einsehbar. Da Ihre Garantieeinträge, Rechnungsbelege und Fotos ausschließlich im lokalen Speicher Ihres eigenen Geräts verbleiben, empfängt der Entwickler diese Daten niemals und agiert nicht als Verantwortlicher hierfür. Der Entwickler ist ausschließlich für die in Abschnitt 6 und 14 beschriebenen Diagnosedaten, anonymen Absturzberichte und Kauflizenzprüfungen verantwortlich.

## 2. Unser Ansatz: Konsequente Offline-First-Architektur

Vancrone basiert auf dem Prinzip „Offline-First“. Es existiert kein zentraler Vancrone-Server, der Produktinformationen, Seriennummern, Preise, Termine, Notizen, Rechnungsfotos oder Videobeweise speichert, indexiert oder verarbeitet. Dies ist eine bewusste architektonische Entscheidung („Privacy by Design“).

## 3. Daten, die wir nicht erfassen

Wir erfassen, übertragen, verkaufen, vermieten oder verarbeiten unter keinen Umständen:

- Ihre Bestands- und Garantiedaten (Namen, Preise, Fristen, Seriennummern, Notizen);
- Ihre Rechnungsfotos oder Tresor-Videobeweise;
- Von der App lokal berechnete Finanz- und Risikoübersichten.

Diese Daten werden ausschließlich von Ihnen lokal generiert und verbleiben auf Ihrem Endgerät, bis Sie diese eigenhändig exportieren oder teilen.

## 4. Lokal auf Ihrem Gerät gespeicherte Daten

Alle Benutzerinhalte werden in einer lokalen Datenbank auf Ihrem Gerät gespeichert und mittels AES-256-Verschlüsselung geschützt (SQLCipher für relationale Datenbankstrukturen und Androids hardwaregestützte EncryptedSharedPreferences für Konfigurationsdaten). AES-256 entspricht den weltweit höchsten Sicherheitsstandards von Banken und Behörden.

## 5. Verschlüsselte manuelle Sicherung über das Storage Access Framework (SAF)

Vancrone enthält keine Google Drive API-Synchronisation und nutzt keine Cloud-Server. Stattdessen wird eine lokale, sichere Sicherungsfunktion über Androids modernes Storage Access Framework (SAF) bereitgestellt:

- Manuelle verschlüsselte Sicherung: Wenn Sie unter Einstellungen „Sichern (Exportieren)“ wählen, werden Ihre Datenbank, Kassenbelege und Bilder in einer einzelnen Archivdatei zusammengefasst und mittels AES-256-GCM verschlüsselt (.vcb).
- Vollständige Kontrolle: Diese Datei wird ausschließlich an dem Speicherort abgelegt, den Sie über die SAF-Dateiauswahl bestimmen (z. B. Gerätespeicher, SD-Karte, USB-Stick oder PC).
- Kein Serverzugriff: Diese Sicherungsdatei wird niemals an Server des Entwicklers übertragen. Die Aufbewahrung, Sicherung und der Schutz dieses Archivs obliegen ausschließlich dem Benutzer.

## 6. Von Vancrone genutzte Dienste Dritter

Für den ordnungsgemäßen Betrieb bindet Vancrone ausgewählte Standard-SDKs von Google ein:

- Google Firebase Crashlytics — Absturzberichte: Anonyme Fehlerprotokolle zur Beseitigung von Stabilitätsproblemen und Programmfehlern.
- Google AdMob — Werbeeinblendungen (kostenlose Version): Zur Bereitstellung von Bannern und belohnten Videoanzeigen in der kostenlosen Version.
- Google ML Kit — Texterkennung auf dem Gerät (OCR): Die Belegerkennung erfolgt zu 100 % lokal auf Ihrem Endgerät („On-Device“). Bilddateien und extrahierte Texte werden nicht an Google übertragen.
- Google Play-Abrechnung — Digitale Käufe: Upgrades auf Pro und Business werden vollständig über die Google Play-Abrechnung abgewickelt; Finanz- und Kartendaten verbleiben ausschließlich bei Google.

## 7. Keine serverseitige Infrastruktur

Vancrone betreibt keine eigenen Server. Der Entwickler unterhält kein Backend, keine Benutzerkonten und keine Remote-Datenbank. Außer den in Abschnitt 6 genannten Google-SDK-Diagnosen verlassen keine Daten Ihr Endgerät in Richtung des Entwicklers.

## 8. Technische Sicherheitsmaßnahmen

Neben der lokalen AES-256-Verschlüsselung implementiert Vancrone Maßnahmen zur Eingabebereinigung, Validierung vor der OCR-Verarbeitung und kryptografische Signaturprüfungen für Google Play-Kaufbestätigungen.

## 9. Datenspeicherung und Nutzerkontrolle

Da alle Daten lokal gespeichert sind, besitzen Sie die uneingeschränkte Kontrolle:

- Option „Alle Daten zurücksetzen“: Löscht Ihre lokale verschlüsselte Datenbank und alle Medien unwiderruflich.
- Deinstallation der App: Veranlasst das Betriebssystem zur vollständigen und dauerhaften Bereinigung des App-Speichers.
- Der Entwickler besitzt keine Datenkopien; eine Wiederherstellung gelöschter Daten ist ausgeschlossen.

## 10. Schutz der Privatsphäre von Kindern

Vancrone richtet sich nicht an Kinder unter 13 Jahren; es werden wissentlich keine Daten von Kindern erhoben.

## 11. Wahlmöglichkeiten des Nutzers

- Werbung: Werbepersonalisierung kann in den Android-Systemeinstellungen (Google > Werbung) deaktiviert werden. Ein Upgrade auf Pro/Business entfernt Werbung vollständig.
- Sicherung: Manuelle verschlüsselte Sicherungen (.vcb) können jederzeit über Einstellungen mittels SAF exportiert oder wiederhergestellt werden.
- Diagnosedaten: Die Erfassung von Nutzungsdaten kann in den Geräteeinstellungen eingeschränkt werden.
- Datenlöschung: Jederzeit über Einstellungen > „Alle Daten zurücksetzen“ möglich.

## 12. Internationale Datenübermittlung

Soweit Diagnosedaten durch Google verarbeitet werden, kann dies auf Grundlage von Standardvertragsklauseln (SCC) auch außerhalb Ihres Wohnsitzlandes (einschließlich in den USA) geschehen.

## 13. Datenschutzrechte

Nach der DSGVO stehen Ihnen Rechte auf Auskunft, Berichtigung und Löschung zu. Da Ihre Inventardaten den Entwickler niemals erreichen, üben Sie diese Rechte unmittelbar direkt auf Ihrem Endgerät aus.

## 14. Regionale Bestimmungen

- EWR, Großbritannien und Schweiz: Verantwortlicher für technische Diagnosedaten ist der Entwickler. Beschwerden können bei den zuständigen Aufsichtsbehörden eingereicht werden.
- USA: Es findet kein Verkauf personenbezogener Daten im Sinne des CCPA statt.
- Türkei: Anfragen nach KVKK Art. 11 können an vancrone.app@gmail.com gerichtet werden.

Vancrone wird von einem unabhängigen Einzelentwickler betrieben; E-Mail-Anfragen werden im Rahmen der personellen Verfügbarkeit innerhalb angemessener Fristen bearbeitet.