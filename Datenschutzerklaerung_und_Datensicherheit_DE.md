# Datenschutzerklärung & Datensicherheit

> Dieses Dokument ist die vollständige deutsche Erklärung zu den Datenverarbeitungsgrundsätzen, Sicherheitsmaßnahmen und Datenschutzstandards der Anwendung Vancrone. Letzte Aktualisierung: 15. Oktober 2026.

## 1. Einleitung

Diese Datenschutzerklärung beschreibt den Umgang mit Informationen im Zusammenhang mit der Android-Anwendung Vancrone. Wir haben diese Erklärung auf einem zentralen Grundsatz aufgebaut: Wir, der Entwickler, sehen, erfassen oder speichern Ihre persönlichen Inventardaten, Garantien, Rechnungen oder Fotos zu keinem Zeitpunkt. Diese Erklärung erläutert die technischen Details und beschreibt die begrenzten technischen Daten, die über die in die App eingebundenen Google-Dienste erhoben werden, sowie die Angaben, die Sie selbst über das Feedback-Formular senden.

Verantwortlicher: Vancrone wird von einem unabhängigen Einzelentwickler entwickelt und veröffentlicht (im Folgenden „Entwickler“). Der Entwickler ist unter vancrone.app@gmail.com erreichbar; verifizierte Angaben zum Herausgeber sind im Google Play Store einsehbar. Da Ihre Garantieeinträge, Rechnungsbelege und Fotos ausschließlich im lokalen Speicher Ihres eigenen Geräts verbleiben, empfängt der Entwickler diese Daten niemals und agiert nicht als Verantwortlicher hierfür. Der Entwickler ist ausschließlich für die in den Abschnitten 6, 7 und 14 beschriebenen begrenzten Daten verantwortlich: Absturzberichte, Nachrichten, die Sie über das Feedback-Formular senden, sowie – falls In-App-Käufe eingeführt werden – von Google Play bereitgestellte Kaufdaten.

## 2. Unser Ansatz: Konsequente Offline-First-Architektur

Vancrone basiert auf dem Prinzip „Offline-First“. Es existiert kein zentraler Vancrone-Server, der Produktinformationen, Preise, Termine, Notizen, Rechnungsfotos oder Videobeweise speichert, indexiert oder verarbeitet. Dies ist eine bewusste architektonische Entscheidung („Privacy by Design“).

## 3. Daten, die wir nicht erfassen

Wir erfassen, übertragen, verkaufen, vermieten oder verarbeiten unter keinen Umständen:

- Ihre Bestands- und Garantiedaten (Namen, Preise, Fristen, Rückgabefristen, Serviceeinträge, Notizen);
- Ihre Rechnungsfotos oder Tresor-Videobeweise;
- Von der App lokal berechnete Finanz- und Risikoübersichten.

Diese Daten werden ausschließlich von Ihnen lokal generiert und verbleiben auf Ihrem Endgerät, bis Sie diese eigenhändig exportieren oder teilen.

## 4. Lokal auf Ihrem Gerät gespeicherte Daten

Ihre Einträge (Produktnamen, Preise, Termine, Rückgabefristen, Serviceeinträge und Notizen zum Aufbewahrungsort von Papierdokumenten) werden in einer lokalen Datenbank auf Ihrem Gerät gespeichert und mit SQLCipher per AES-256 verschlüsselt. Der Datenbankschlüssel wird auf Ihrem Gerät erzeugt und in EncryptedSharedPreferences abgelegt, geschützt durch einen Schlüssel im Android Keystore (auf unterstützten Geräten hardwaregestützt). Rechnungsfotos, Produktbilder und Videobeweise werden im privaten Speicherbereich der App abgelegt, den Android von anderen Apps abschottet und mit der geräteeigenen Speicherverschlüsselung schützt; Vancrone verschlüsselt diese Mediendateien nicht zusätzlich. Auf gerooteten Geräten können andere Apps diese Schutzmaßnahmen möglicherweise umgehen.

## 5. Verschlüsselte manuelle Sicherung über das Storage Access Framework (SAF)

Vancrone enthält keine Google Drive API-Synchronisation und nutzt keine Cloud-Server. Stattdessen wird eine lokale Sicherungsfunktion über Androids Storage Access Framework (SAF) bereitgestellt:

- Manuelle verschlüsselte Sicherung: Wenn Sie in den Einstellungen eine Sicherung erstellen, werden Ihre Datenbank, Ihre Garantie-Medien (Rechnungsfotos, Produktbilder, Videobeweise) und mit dem Thermobeleg-Retter gespeicherte Bilder in einer einzelnen Archivdatei zusammengefasst und mittels AES-256-GCM verschlüsselt (.vcb).
- Optionales Sicherungspasswort: Wenn Sie ein Sicherungspasswort festlegen, wird der Schlüssel aus diesem Passwort abgeleitet (PBKDF2-HMAC-SHA256, 600.000 Iterationen), und die Datei lässt sich ohne das Passwort nicht öffnen. Der Entwickler kann ein vergessenes Passwort nicht wiederherstellen. Ohne Passwort wird die Datei mit einem in die App eingebauten Schlüssel verschlüsselt: Sie können sie weiterhin auf jedem Gerät wiederherstellen, aber jeder, der sowohl die Datei als auch die Vancrone-App besitzt, kann sie ebenfalls öffnen. Wir empfehlen ein Passwort, insbesondere wenn Sie die Sicherung an einem geteilten Ort oder in einem Cloud-Speicher aufbewahren.
- Vollständige Kontrolle: Diese Datei wird ausschließlich an dem Speicherort abgelegt, den Sie über die SAF-Dateiauswahl bestimmen (z. B. Gerätespeicher, SD-Karte, USB-Stick oder PC).
- Kein Serverzugriff: Diese Sicherungsdatei wird von Vancrone niemals an Server des Entwicklers oder Dritter übertragen. Die Aufbewahrung, Sicherung und der Schutz dieses Archivs obliegen ausschließlich dem Benutzer.

## 6. Von Vancrone genutzte Dienste Dritter

Für den ordnungsgemäßen Betrieb bindet Vancrone ausgewählte Standard-SDKs von Google ein. Soweit diese SDKs Daten übermitteln, verarbeitet Google sie im Auftrag des Entwicklers gemäß den Datenverarbeitungsbedingungen von Google.

- Google Firebase Crashlytics — Absturzberichte: Wenn die App abstürzt oder ein abgefangener Fehler auftritt (z. B. ein fehlgeschlagener PDF- oder CSV-Export), sendet Crashlytics einen Bericht mit Stacktrace, Gerätemodell, Android-Version, App-Version, einer zufälligen Crashlytics-Installationskennung und dem Zeitpunkt des Ereignisses. Die Berichte enthalten keine Einträge, Rechnungen oder Fotos und werden nicht mit Ihrem Namen oder Ihrer E-Mail-Adresse verknüpft. Sie dienen nur der Fehlerbehebung und werden von Crashlytics 90 Tage lang gespeichert.
- Google AdMob — Werbeeinblendungen (geplant): Die aktuelle Version von Vancrone zeigt keine Werbung an und enthält das Google Mobile Ads (AdMob) SDK nicht. Falls in einer künftigen Version Werbung für die kostenlose Version eingeführt wird, wird diese Erklärung vor dieser Veröffentlichung aktualisiert, und personalisierte Werbung wird nur mit Ihrer Einwilligung angezeigt, wo das Gesetz dies verlangt.
- Google ML Kit — Texterkennung auf dem Gerät (OCR) und Dokumentenscanner: Die Belegerkennung nutzt die geräteinterne Texterkennung von ML Kit und den Dokumentenscanner der Google Play-Dienste. Bilddateien und extrahierte Texte werden auf Ihrem Gerät verarbeitet und nicht an Google übertragen. ML Kit kann Google kontaktieren, um Modellaktualisierungen herunterzuladen und begrenzte Messwerte zur Leistung der API selbst zu senden; diese enthalten weder Ihre Bilder noch Ihre Texte.
- Google Play-Abrechnung — Digitale Käufe: Die aktuelle Version von Vancrone bietet keine In-App-Käufe an und verbindet sich nicht mit der Google Play-Abrechnung. Werden optionale Pro- oder Business-Upgrades eingeführt, werden sie vollständig über Google Play abgewickelt: Zahlungsdaten verbleiben ausschließlich bei Google, der Entwickler erhält nur die von Google Play bereitgestellten Bestellinformationen (z. B. Bestellnummer, Produkt, Kaufdatum und Land), und die App liest Ihren Kaufstatus auf dem Gerät über die Google Play Billing Library aus. Diese Erklärung wird vorher aktualisiert.

## 7. Keine serverseitige Infrastruktur; Feedback-Formular

Vancrone betreibt keine eigenen Server. Der Entwickler unterhält kein Backend, keine Benutzerkonten und keine Remote-Datenbank für Ihre Einträge. Abgesehen von den in Abschnitt 6 genannten Google-Diensten verlassen Daten Ihr Gerät nur, wenn Sie dies selbst veranlassen:

- Feedback: Wenn Sie unter Einstellungen > „Fehler melden & Feedback“ auf Senden tippen, überträgt die App selbst nichts; sie öffnet Ihre eigene E-Mail-App mit einer vorbereiteten E-Mail an vancrone.app@gmail.com, die Ihre Nachricht, Gerätehersteller und -modell, Android-Version und App-Version enthält. Sie können die E-Mail vor dem Senden prüfen und bearbeiten; sie erreicht das Gmail-Postfach (Google) des Entwicklers zusammen mit Ihrer E-Mail-Adresse nur, wenn Sie sie von Ihrem eigenen E-Mail-Konto senden. Diese Angaben werden nur zur Beantwortung und zur Behebung des gemeldeten Problems verwendet und nur so lange aufbewahrt, wie es dafür erforderlich ist. Bitte geben Sie in Feedback-Nachrichten keine sensiblen personenbezogenen Daten an.
- Export und Teilen: PDF-/CSV-Berichte, Sicherungen und von Ihnen geteilte Dateien gelangen nur an das von Ihnen gewählte Ziel.

## 8. Technische Sicherheitsmaßnahmen

Neben der lokalen AES-256-Verschlüsselung der Datenbank verwendet Vancrone parametrisierte Datenbankabfragen gegen SQL-Injection, dekodiert und verkleinert Bilder auf dem Gerät, bevor sie an die lokale OCR übergeben werden, prüft vor einer Wiederherstellung die Integrität der Sicherung (authentifizierte AES-GCM-Verschlüsselung und SHA-256-Prüfsummen der archivierten Dateien) und warnt Sie, wenn Anzeichen für Root-Zugriff erkannt werden. Die aktuelle Version bietet keine Käufe an; werden Käufe eingeführt, wird ihr Status über die Google Play Billing Library von Google Play gelesen, und Vancrone führt keine eigene serverseitige Prüfung der Kaufsignaturen durch. Kein Softwaresystem ist jedoch unüberwindbar; für die Sicherheit Ihres Geräts bleiben Sie selbst verantwortlich.

## 9. Datenspeicherung und Nutzerkontrolle

Da alle Daten lokal gespeichert sind, besitzen Sie die uneingeschränkte Kontrolle:

- Option „Alle Daten löschen“: Löscht alle Garantieeinträge in Ihrer lokalen verschlüsselten Datenbank samt zugehörigen Rechnungsfotos, Produktbildern und Videobeweisen dauerhaft und unwiderruflich. Ebenso werden mit dem Thermobeleg-Retter gespeicherte Bilder sowie im privaten App-Speicher verbliebene Mediendateien ohne zugehörigen Eintrag und temporäre Kameraaufnahmen gelöscht.
- Deinstallation der App: Veranlasst das Betriebssystem zur vollständigen und dauerhaften Bereinigung des App-Speichers.
- Der Entwickler besitzt keine Kopien Ihrer Einträge; eine Wiederherstellung gelöschter Einträge ist ausgeschlossen. Exportierte Sicherungsdateien verbleiben an ihrem Speicherort, bis Sie sie löschen.
- Absturzberichte und Feedback-Nachrichten werden nur für die in den Abschnitten 6 und 7 genannten Zeiträume aufbewahrt.

## 10. Schutz der Privatsphäre von Kindern

Vancrone richtet sich nicht an Kinder unter 13 Jahren; es werden wissentlich keine Daten von Kindern erhoben.

## 11. Wahlmöglichkeiten des Nutzers

- Werbung und Werbe-ID: Die aktuelle Version zeigt keine Werbung und erfasst Ihre Werbe-ID nicht.
- Absturzberichte: Sie können Crashlytics jederzeit unter Einstellungen > Über > „Absturzberichte“ abschalten. Der Schalter ist standardmäßig aktiviert. Solange er aus ist, werden keine Absturzberichte gesendet und noch auf dem Gerät wartende Berichte gelöscht; Ihre Wahl bleibt erhalten, bis Sie sie ändern. Vor dem Abschalten gesendete Berichte werden für den in Abschnitt 6 genannten Zeitraum aufbewahrt. Auch eine Deinstallation beendet jede Erfassung.
- Sicherung: Manuelle verschlüsselte Sicherungen (.vcb) können jederzeit über die Einstellungen mittels SAF exportiert, mit einem Sicherungspasswort geschützt oder wiederhergestellt werden.
- Datenlöschung: Jederzeit über Einstellungen > „Alle Daten löschen“ möglich.

## 12. Internationale Datenübermittlung

Da Google weltweit tätig ist, können die in den Abschnitten 6 und 7 beschriebenen Absturzberichte und Feedback-Nachrichten sowie – falls Käufe eingeführt werden – Bestelldaten von Google Play auch außerhalb Ihres Wohnsitzlandes (einschließlich in den USA) verarbeitet werden. Google stützt sich dabei auf seine Datenverarbeitungsbedingungen, einschließlich Standardvertragsklauseln (SCC) und, soweit anwendbar, des EU-US Data Privacy Framework.

## 13. Datenschutzrechte

Nach der DSGVO und vergleichbaren Gesetzen stehen Ihnen Rechte auf Auskunft, Berichtigung, Löschung und Widerspruch zu. Da Ihre Inventardaten den Entwickler niemals erreichen, üben Sie diese Rechte für diese Inhalte unmittelbar auf Ihrem Endgerät aus. Für Absturzberichte oder Feedback-Nachrichten wenden Sie sich an vancrone.app@gmail.com; da Absturzberichte pseudonym sind, kann der Entwickler möglicherweise nicht feststellen, welche Einträge Sie betreffen.

## 14. Regionale Bestimmungen

- EWR, Großbritannien und Schweiz: Rechtsgrundlagen sind berechtigte Interessen (Absturzdiagnose, um die App stabil zu halten; Beantwortung Ihres Feedbacks) sowie – falls In-App-Käufe eingeführt werden – die Vertragserfüllung (In-App-Käufe). Sollte personalisierte Werbung eingeführt werden, erfolgt sie auf Grundlage Ihrer Einwilligung. Sie können der Verarbeitung auf Grundlage berechtigter Interessen widersprechen und Beschwerde bei der zuständigen Aufsichtsbehörde einlegen.
- USA: Es findet kein Verkauf oder Teilen personenbezogener Daten im Sinne des CCPA statt.
- Türkei: Anfragen nach KVKK Art. 11 können an vancrone.app@gmail.com gerichtet werden.

Vancrone wird von einem unabhängigen Einzelentwickler betrieben; E-Mail-Anfragen werden im Rahmen der personellen Verfügbarkeit innerhalb angemessener Fristen bearbeitet.
