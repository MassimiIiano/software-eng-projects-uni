# Software Engineering

## Team Mitglieder
- [Dan Dumbrava](mailto:dan.dumbrava@student.unibz.it)
- [Nicolas Bonet](mailto:nicolas.bonet@student.unibz.it)
- [Massimiliano Mola](mailto:massimiliano.mola@student.unibz.it)

## Projekt 1

### Anwendungsfallmodell

![Anwendungsfallmodell](./sw-eng-01.drawio.svg)

### Anwendungsfallmodell mit Server

![Anwendungsfallmodell mit Server](./sw-eng-02.drawio.svg)

#### Erklärung

- Aufgabe 1: Das Anwendungsfalldiagramm zeigt das Autovermietungssystem, aus der Sicht des Kunden. Die angezeigte Anwendungsfälle beschreiben die Interaktionen zwischen den Kunden und dem System, durch Datenaustausch und deren Anforderungen. Die Eintrittspunkte des Systems für den Kunden sind die Buchungen und die angezeigten Angebote. Jeder Anwendungsfall ist erforderlich für ein funktionelles, komplettes Autovermietungssystem.

- Aufgabe 2: Das Anwendungsfalldiagramm zeigt Anwendungsfälle des Autovermietungssystems. Die meisten Fälle werden aus der Perspektive des Servers beschrieben. Nur der Anwendungsfall "Buchung" ist direkt mit dem Kunden verbunden.
Eingeschlossene Anwendungsfälle (Buchung, Buchungsinformationen und Alter, Persönliche Daten, Zahlungsdaten, usw.) sind notwendig, um Basis-Anwendungsfälle korrekt zu funktionieren (Bestätigungs-E-Mail Erstellung, Kostenvoranschläge Bereitstellung, Buchung in Datenbank Speicherung, usw.).

### Klassendiagramm (Einfach)
![Klassendiagramm (Einfach)](./sw-eng-03.drawio.svg)

#### Erklärung

Der Benutzer enthält persönliche Daten und kann mit vielen Zahlungsdaten verbunden sein. Dem echten Kunden (nicht dem Objekt) werden Buchungsvorschläge gemacht, die auf dem Fahrzeug und der Buchungsdauer basieren. Ein Buchungsvorschlag wird als Vorlage genommen, um eine Buchung zu erstellen.
Dem echten Kunde (nicht das Objekt) werden Buchunsvorschlage gemacht, die basierend auf das fahrzeug und die Buchungsdauer sind.
Ein Buchungsvorschlag wird as template genommen um eine Buchung zu erstellen.

### Klassendiagramm (Erweitert)
![Klassendiagramm (Erweitert)](./sw-eng-04.drawio.svg)

#### Erklärung

Ein Benutzer könnte die Kreditkarte einer anderen Person nutzen, daher gibt es keine Aggregation zwischen der Karte und dem Nutzer. Jede Buchung basiert auf einem Buchungsvorschlag, daher ist der Vorschlag ein wichtiger Teil der Buchung. Die Rückgabe-/Abgabedaten und -orte sind Teil des Buchungsvorschlags, da sie als Parameter für die Vermittlungssuche verwendet werden. Das Attribut "Reduzierung" in den Buchungen enthält Informationen wie Aktionen oder Reduzierungen der Selbstbeteiligung gegen eine zusätzliche Gebühr. Da die Vorschläge können auch bei E-Mail angeboten sein, es besteht eine viele-zu-viele-Assoziation zwischen Buchungsvorschlägen und E-Mails, da ein Kunde mehrere E-Mails für einen Vorschlag senden und erhalten kann.

### Sequenzdiagramm
![Sequenzdiagramm](./sw-eng-05.drawio.svg)

#### Erklärung
Das Sequenzdiagramm zeigt, wie ein Kunde Mietvorschläge basierend auf Alter und Anforderungen anfordert (*Kostenvoranschläge Bereitstellung* Anwendungsfall).
Der Suchvorgang startet in der Präsentationsschicht, durchläuft den Server, der Autos filtert, und greift auf die Autodatenbank zu. Gefilterte Autos werden als Mietvorschläge zurückgegeben und dem Kunden angezeigt.
Das Diagramm zeigt keine Fehlerbehandlung. P_SuchVorschlag kümmert sich um das GUI, um die Vorschläge dem Kunden anzuzeigen.

### Klassendiagramm mit funktionen
![Klassendiagramm mit Funktionen](./sw-eng-06.drawio.svg)

#### Erklärung
<!-- TODO -->
