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

Der User enthelt Persoenliche Daten und kann mit vielen Bezahlungsdaten verbunden sein.
Dem echten Kunde (nicht das Objekt) werden Buchunsvor
