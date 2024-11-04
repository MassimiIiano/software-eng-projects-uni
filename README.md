# Software Engineering

## Team Mitglieder
- [Dan Dumbrava](mailto:dan.dumbrava@student.unibz.it)
- [Nicolas Bonet](mailto:nicolas.bonet@student.unibz.it)
- [Massimiliano Mola](mailto:massimiliano.mola@student.unibz.it)

---

## Projekt 1

### A1: Anwendungsfallmodell

![Anwendungsfallmodell](./sw-eng-01.drawio.svg)

**Erklärung**  
Das Anwendungsfalldiagramm zeigt das Autovermietungssystem aus der Sicht des Kunden. Die dargestellten Anwendungsfälle beschreiben die Interaktionen zwischen dem Kunden und dem System durch Datenaustausch und Anforderungen. Die Haupt-Eintrittspunkte des Systems für den Kunden sind Buchungen und angezeigte Angebote. Jeder Anwendungsfall ist für ein funktionales, komplettes Autovermietungssystem erforderlich.

---

### A2: Anwendungsfallmodell mit Server

![Anwendungsfallmodell mit Server](./sw-eng-02.drawio.svg)

**Erklärung**  
Dieses Anwendungsfalldiagramm zeigt die Anwendungsfälle des Autovermietungssystems aus der Perspektive des Servers. Eingeschlossene Anwendungsfälle wie `Buchung`, `Buchungsinformationen`, `Alter`, `Persönliche Daten` und `Zahlungsdaten` sind notwendig, um die grundlegenden Funktionen wie `Buchungabschluss`, `Kostenvoranschläge Bereitstellung` und `Datenüberprüfung` korrekt auszuführen.

---

### A3: Klassendiagramm (Einfach)

![Klassendiagramm (Einfach)](./sw-eng-03.drawio.svg)

**Erklärung**  
Das Klassendiagramm enthält die grundlegenden Entitäten des Systems. Jeder Kunde kann mehrere Zahlungsmethoden und Buchungen haben, die mit Buchungsvorschlägen verbunden sind. Zudem ist jedes Fahrzeug mit den Buchungsvorschlägen verknüpft.

---

### A4: Klassendiagramm (Erweitert)

![Klassendiagramm (Erweitert)](./sw-eng-04.drawio.svg)

**Erklärung**  
In diesem erweiterten Klassendiagramm:
- Kann ein Benutzer die Zahlungsmethode einer anderen Person nutzen, daher besteht keine Aggregation zwischen Karte und Nutzer.
- Basieren alle Buchungen auf Buchungsvorschlägen, wodurch der Vorschlag ein zentraler Bestandteil der Buchung wird.
- Werden Rückgabe- und Abgabedaten sowie -orte im Buchungsvorschlag gespeichert, da sie Parameter für die Vermittlungssuche sind.
- Enthält das Attribut "Reduzierung" in den Buchungen Informationen zu Aktionen oder Selbstbeteiligungsreduzierungen gegen eine zusätzliche Gebühr.
- Besteht eine viele-zu-viele-Assoziation zwischen Buchungsvorschlägen und E-Mails, da Kunden mehrere E-Mails für einen Vorschlag senden und empfangen können.
- Muss der Kunde das im Attribut `minAlter` festgelegte Mindestalter erreichen, um ein Fahrzeug zu mieten.

---

### A5: Sequenzdiagramm

![Sequenzdiagramm](./sw-eng-05.drawio.svg)

**Erklärung**  
Das Sequenzdiagramm zeigt, wie ein Kunde Mietvorschläge basierend auf Alter und Anforderungen anfordert (Anwendungsfall: *Kostenvoranschläge Bereitstellung*). Der Suchvorgang startet in der Präsentationsschicht, durchläuft den Server, der Fahrzeuge filtert, und greift auf die Fahrzeugdatenbank zu. Die gefilterten Fahrzeuge werden als Mietvorschläge zurückgegeben und dem Kunden angezeigt. Fehlerbehandlung ist hier nicht dargestellt, und `P_SuchVorschlag` kümmert sich um die GUI, um die Vorschläge an den Kunden anzuzeigen.

---

### A6: Klassendiagramm mit Funktionen

![Klassendiagramm mit Funktionen](./sw-eng-06.drawio.svg)

**Erklärung**  
Das Diagramm beschreibt die Klassen, Methoden und Abhängigkeiten, die benötigt werden, um eine Liste von Leihvorschlägen für den Kunden zu liefern. Der Kunde gibt auf der Seite `SuchVorschlag` sein Alter und seine Anforderungen ein. Diese Informationen werden an den Server gesendet, der `SuchController` verwendet, um eine Liste von Fahrzeugen zu erhalten, die den Anforderungen des Kunden entsprechen. Der `C_Server` übergibt die Fahrzeugliste an die `C_Vorschlag`-Komponente und erhält eine Liste von Vorschlägen zurück, die dann an `P_SuchVorschlag` gesendet wird und dem Kunden grafisch angezeigt wird.

---

### A7: Schichtenarchitektur

![Schichtenarchitektur](./sw-eng-07.drawio.svg)

**Erklärung**  
Die Schichtenarchitektur trennt Präsentation, Steuerung und Entitäten, um die Klassen und Abhängigkeiten übersichtlich darzustellen:
- Der Kunde gibt seine Anforderungen auf der `PSuche`-Seite ein, die an den Server gesendet werden.
- Der `CSuche`-Controller ruft eine Liste passender Fahrzeuge ab und übergibt diese an `CVorschlag`, das daraus konkrete Buchungsvorschläge erstellt.
- Die Vorschläge werden an `PSuche` zurückgesendet und dem Kunden angezeigt.

---

### A8: Zustandsdiagramm

![Zustandsdiagramm](./sw-eng-08.drawio.svg)

**Erklärung**  
Das Zustandsdiagramm zeigt den Ablauf einer Buchung im AV-System. Nach Datenerfassung und Bestätigung wird die Zahlung eingeleitet. Bei erfolgreicher Zahlung wird die Buchung bestätigt und eine Bestätigungs-E-Mail gesendet. Der Benutzer kann die Buchung stornieren, wobei eine E-Mail versendet wird. Der Prozess endet im Zustand `Terminated`.

---

### A9: Komponentendiagramm

![Komponentendiagramm](./sw-eng-09.drawio.svg)

**Erklärung**  
Die zentralen Komponenten des Systems sind `Fahrzeug`, `Kunde`, `Vorschlag`, `Buchung`, `Extra` und `Bezahlung`. Diese sind über Schnittstellen mit den Modulen `Suche`, `Buchung`, `Vorschlag` und `Mail` verbunden. Über diese Schnittstellen fließen Daten zwischen den Komponenten, um die verschiedenen Funktionen der Anwendung bereitzustellen. Jede Verbindung zeigt, wie die Komponenten zusammenarbeiten, um das System funktionsfähig zu machen.

---

### A10: Bereitstellungsdiagramm

![Bereitstellungsdiagramm](./sw-eng-10.drawio.svg)

**Erklärung**  
Das Bereitstellungsdiagramm zeigt die Verteilung der AV-Anwendung. Die Anwendung läuft auf einem WebServer mit `J2EEServer`, auf dem `Kunde.jar`, `Buchung.jar`, `Vorschlag.jar` und `Mail.jar` ausgeführt werden. Datenbanken (`DBFahrzeug`, `DBKunde`, `DBBuchung`) speichern die benötigten Daten und kommunizieren mit dem Webserver. Nutzer greifen über ein Gerät und HTTP auf die HTML-Seiten `Vorschlag.html`, `Buchung.html` und `Suche.html` zu, die im Browser geladen werden. Diese Struktur ermöglicht den Zugang zur Anwendung auf verschiedenen Geräten.
