# Software Engineering

## Team Mitglieder
- [Dan Dumbrava](mailto:dan.dumbrava@student.unibz.it)
- [Nicolas Bonet](mailto:nicolas.bonet@student.unibz.it)
- [Massimiliano Mola](mailto:massimiliano.mola@student.unibz.it)

## Projekt 1

### A1: Anwendungsfallmodell

![Anwendungsfallmodell](./sw-eng-01.drawio.svg)

#### Erklärung

Das Anwendungsfalldiagramm zeigt das Autovermietungssystem, aus der Sicht des Kunden. Die angezeigte Anwendungsfälle beschreiben die Interaktionen zwischen den Kunden und dem System, durch Datenaustausch und deren Anforderungen. Die Eintrittspunkte des Systems für den Kunden sind die Buchungen und die angezeigten Angebote. Jeder Anwendungsfall ist erforderlich für ein funktionelles, komplettes Autovermietungssystem.

### A2: Anwendungsfallmodell mit Server

![Anwendungsfallmodell mit Server](./sw-eng-02.drawio.svg)

#### Erklärung

Das Anwendungsfalldiagramm zeigt Anwendungsfälle des Autovermietungssystems. Die meisten Fälle werden aus der Perspektive des Servers beschrieben. Nur der Anwendungsfall "Buchung" ist direkt mit dem Kunden verbunden. Eingeschlossene Anwendungsfälle (Buchung, Buchungsinformationen und Alter, Persönliche Daten, Zahlungsdaten, usw.) sind notwendig, um Basis-Anwendungsfälle korrekt zu funktionieren (Buchungabschluss, Kostenvoranschläge Bereitstellung, Datenüberprüfung).

### A3: Klassendiagramm (Einfach)
![Klassendiagramm (Einfach)](./sw-eng-03.drawio.svg)

#### Erklärung

Das Klassendiagramm enthält die grundlegenden Entitäten des Systems: Jeder Kunde kann mehrere Kreditkarten und Buchungen haben, die mit E-Mails, Buchungsvorschlägen und Extras verbunden sind. Zudem ist ein Buchungsvorschlag mit E-Mails verknüpft, da ein Kunde die Informationen zum Vorschlag per E-Mail anfordern kann. Es gibt außerdem ein Fahrzeug, das mit Buchungsvorschlägen verknüpft ist.

### A4: Klassendiagramm (Erweitert)
![Klassendiagramm (Erweitert)](./sw-eng-04.drawio.svg)

#### Erklärung

Ein Benutzer könnte die Kreditkarte einer anderen Person nutzen, daher gibt es keine Aggregation zwischen der Karte und dem Nutzer. Jede Buchung basiert auf einem Buchungsvorschlag, daher ist der Vorschlag ein wichtiger Teil der Buchung. Die Rückgabe-/Abgabedaten und -orte sind Teil des Buchungsvorschlags, da sie als Parameter für die Vermittlungssuche verwendet werden. Das Attribut "Reduzierung" in den Buchungen enthält Informationen wie Aktionen oder Reduzierungen der Selbstbeteiligung gegen eine zusätzliche Gebühr. Da die Vorschläge können auch bei E-Mail angeboten sein, es besteht eine viele-zu-viele-Assoziation zwischen Buchungsvorschlägen und E-Mails, da ein Kunde mehrere E-Mails für einen Vorschlag senden und erhalten kann.

### A5: Sequenzdiagramm
![Sequenzdiagramm](./sw-eng-05.drawio.svg)

#### Erklärung
Das Sequenzdiagramm zeigt, wie ein Kunde Mietvorschläge basierend auf Alter und Anforderungen anfordert (*Kostenvoranschläge Bereitstellung* Anwendungsfall).
Der Suchvorgang startet in der Präsentationsschicht, durchläuft den Server, der Fahrzeuge filtert, und greift auf die Fahrzeugsdatenbank zu. Gefilterte Fahrzeuge werden als Mietvorschläge zurückgegeben und dem Kunden angezeigt.
Das Diagramm zeigt keine Fehlerbehandlung. P_SuchVorschlag kümmert sich um das GUI, um die Vorschläge dem Kunden anzuzeigen.

### A6: Klassendiagramm mit funktionen
![Klassendiagramm mit Funktionen](./sw-eng-06.drawio.svg)

#### Erklärung
Das Diagramm beschreibt die Klassen, deren Methoden und die Abhängigkeiten zueinander, um eine Liste von Leihvorschlägen für den Kunden zu liefern. Der Kunde gibt auf der Seite SearchProposals sein Alter und seine Anforderungen an. Diese Informationen werden an den Server gesendet, der den SearchController verwendet, um eine Liste von Fahrzeugen zu erhalten, die den Anforderungen des Kunden entsprechen. Der C_Server übergibt anschließend die Liste der Fahrzeuge an die C_Proposal-Komponente und erhält eine Liste von Vorschlägen zurück. Diese werden dann an P_SearchProposal gesendet, das die Liste der Vorschläge dem Kunden grafisch anzeigt.

### A7: Schichtenarchitektur
![Klassendiagramm mit Funktionen](./sw-eng-07.drawio.svg)

#### Erklärung
Dieses diagramm folgt den data flow. Die Presentation componente zeigen die Suchergebnisse, Buchungsvorshläge und Buchungsvorgänge ab. diese daten kriegen sie vom controll layer der auf einem eigenen server leuft. dieser ist dafür zuständig die korrekten informationen vom database zu holen. Wichtig zu bemerken dass die einzige Entität die nich in ein database gespeicehrt wird die EVorschlag Entität ist. dieese wird dinamisch von CVorschlag anhand von den verfügbaren EAutos berechnet. Falls ein buchungsvorschlag ausgewählt wird wird ein Buchungsobjekt anhand von diesen EVorschlag gemacht, der dan von CBuchung im database abgespeihert wird.


### A8: Zustandsdiagramm
![Klassendiagramm mit Funktionen](./sw-eng-08.drawio.svg)

#### Erklärung

Das Zustandsdiagramm beschreibt die Zustände der Entitäten die in den vorherige Diagrammen geschrieben sind. Das Diagramm beginnt mit der Verifizierung der Daten für die Generation der Buchung und der Erfüllung der Zahlungsdaten. Wenn die Zahlung fehlschlägt, kann der Kunde die Zahlung mehrmals wiederholen bis sie erfolgreich ist. Wenn der Kunde seine Buchung stornieren möchte, wird eine Absage-Email gesendet; ansonsten bleibt die Buchung aktiv.

### A9: Komponentendiagramm
![Klassendiagramm mit Funktionen](./sw-eng-09.drawio.svg)



#### Erklärung

### A10: Bereitstellungsdiagramm
![Klassendiagramm mit Funktionen](./sw-eng-10.drawio.svg)

#### Komponenten-Interaktionen

* $\mathtt{*.jar} \xrightarrow{\text{Deploy}} \mathtt{Webserver}$
* $\mathtt{*.html} \xrightarrow{\text{Display}} \mathtt{Nutzersgerät}$
* $\mathtt{*.ddl} \xrightarrow{\text{Serve data}} \mathtt{J2EEServer}$
* $\mathtt{Webserver} \xrightarrow{\text{Serve over HTTP}} \mathtt{Nutzersgerät}$
* $\mathtt{Nutzersgerät} \xrightarrow{\text{Serve for processing}} \mathtt{Browser}$

#### Erklärung

Das Bereitstellungsdiagramm erzeugt die wichtigen Software-Komponenten des AV-Systems und ihre Interaktionen zwischen ihnen. Jede Komponente enthält Files die erforderlich sind für die Arbeit der Komponente. Der Text unterhalb des Diagramms beschreibt die Rolle des Datenaustauschs zwischen den Komponenten.
