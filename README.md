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

*Aufgabe 2:* Das Anwendungsfalldiagramm zeigt Anwendungsfälle des Autovermietungssystems. Die meisten Fälle werden aus der Perspektive des Servers beschrieben. Nur der Anwendungsfall "Buchung" ist direkt mit dem Kunden verbunden.
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
<!-- TODO -->

### Sequenzdiagramm
![Sequenzdiagramm](./sw-eng-05.drawio.svg)

#### Erklärung
<!-- TODO -->

### Klassendiagramm mit funktionen
![Klassendiagramm mit Funktionen](./sw-eng-06.drawio.svg)

#### Erklärung
<!-- TODO -->