“Mundo Animal” Veterinary Management System 
Week: (April 20–29)

**Roll the Data Modeler (Alejandra Porras).

This week, the work focused on cleaning up the “pets” collection within the MongoDB Atlas cluster. The main objective was to maintain the owner and pet records, ensuring that contact and health information was properly linked. 2. Log of Questions and Technical Challenges During the process, key obstacles arose that required an in-depth analysis of the database architecture:
Monday, April 20 – Tuesday, April 21: Interface Confusion (Query vs. Command)
Question: Why was the platform flagging syntax errors (red borders) when attempting to execute update statements? Finding: It was determined that work was being performed in the Query Bar, which is read-only. To make structural or data changes via code, the use of Mongosh or external administration tools is essential.
Wednesday, 22nd – Thursday, 23rd: Identifying Field Paths (Dot Notation)
Problem: Die Suchfilter lieferten keine Ergebnisse, selbst wenn die richtige ID eingegeben wurde. Erkenntnis: Nach Überprüfung der JSON-Dokumente stellte sich heraus, dass die Informationen nicht „flach“ sind. Die Daten sind in verschachtelten Objekten organisiert. So befindet sich beispielsweise die ID des Eigentümers nicht an der Wurzel, sondern in einem Unterobjekt namens „owner“. Dies machte es erforderlich, die Art und Weise, wie auf die Informationen zugegriffen wird, neu zu überdenken.
Freitag, 24.: Syntaxfehler im Terminal
Problem: Das System lehnte Befehle ab, obwohl die Logik korrekt war. Erkenntnis: Es wurde eine extreme Empfindlichkeit gegenüber unsichtbaren Zeichen (Leerzeichen am Zeilenende) sowie Fehler bei der Trennung von Blöcken durch Kommas festgestellt. Es wurde ein Protokoll für die einzeilige Eingabe festgelegt, um Unterbrechungen bei der Ausführung im Terminal zu vermeiden.
Angewandte Lösung Um die Probleme mit der Sichtbarkeit des Terminals im Browser zu beheben und die technischen Anforderungen zu erfüllen, entschied man sich für: Validierung der Feldhierarchie: Sicherstellung, dass jeder Pfad mit dem Schema (Objekt.Feld) übereinstimmt. Einsatz von MongoDB Compass: Es wurde empfohlen, die Desktop-Anwendung zu verwenden, um einen stabilen Zugriff auf die Befehlskonsole zu gewährleisten, falls die Weboberfläche Einschränkungen bei der Darstellung aufweisen sollte.
Zwischenstand der Woche Die Datenbank ist korrekt strukturiert. Es wurde ein tiefgreifendes Verständnis für die Navigation durch komplexe Dokumente erreicht und die Kommunikationsbarrieren mit der MongoDB-Suchmaschine wurden beseitigt.

** Roll als Query Developer (Tammy Nashely)

Zusammenfassung der Aktivitäten: In dieser Woche lag der Schwerpunkt auf der Implementierung fortgeschrittener logischer Operatoren, um die Informationssuche zu verfeinern und die Genauigkeit der Tiergesundheitsberichte zu verbessern. Die Abfragen wurden optimiert, um mehrere Filter und spezifische Ausschlüsse zu ermöglichen.
Implementierung logischer Operatoren Nachfolgend sind die unter Verwendung der Syntax der MongoDB Query Language (MQL) entwickelten Abfragen aufgeführt: A. Verwendung des Operators $or Dieser Operator wurde verwendet, um Datensätze zu identifizieren, die mindestens eine der angegebenen Bedingungen erfüllen. Er eignet sich ideal für die gleichzeitige Suche nach mehreren Tierarten oder Symptomen. • Anwendungsfall: Filtern von Patienten, die Vögel oder Reptilien sind. • Abfrage: db.pacientes.find({ $or: [ { especie: „Kanarienvogel“ }, { especie: „Schildkröte“ } ] })
B. Verwendung des Operators $and Er wurde für Abfragen implementiert, bei denen alle Bedingungen strikt erfüllt sein müssen. Obwohl MongoDB in vielen Fällen ein implizites $and anwendet, ist dessen explizite Verwendung erforderlich, wenn derselbe Schlüssel mit verschiedenen Operatoren wiederholt wird. • Anwendungsfall: Filtern von Haustieren einer bestimmten Art, die in einem bestimmten Datumsbereich behandelt wurden. • Abfrage: db.consultas.find({ $and: [ { especie: „Hamster“ }, { visit_date: { $regex: /2026-04/ } } ] }) db.queries.find({ $and: [ { species: „Hamster“ }, { visit_date: { $regex: /2026-04/ } } ] })

C. Verwendung des Operators $not Dieser Operator wurde eingesetzt, um die Wirkung anderer Operatoren umzukehren und so bestimmte Ergebnisse auszuschließen, die einem technischen oder gesundheitlichen Kriterium nicht entsprechen. • Anwendungsfall: Identifizierung von Patienten, die nicht als „stabil“ markiert wurden. • Abfrage: db.pacientes.find({ estado_salud: { $not: { $eq: „Estable“ } } }) 3. Ergebnisse und Validierungen • Filtergenauigkeit: Es wurde eine tiefere Segmentierung der Sammlung registro_medico erreicht. • Optimierung: Die Abfragen wurden in MongoDB Compass getestet, um sicherzustellen, dass die Antwortzeiten optimal sind, bevor sie in das Backend in Node.js integriert wurden. • Konsistenz: Es wurde überprüft, dass die Ergebnisse mit den vom Team geforderten Anforderungen an die Datenanalyse übereinstimmen.

**Roll Datenverarbeiterin/QA (Ximena Rosas)

Erstellung von „Seeds“ (Datensätzen) Du hast drei miteinander verbundene Sammlungen nach der Chaostheorie erstellt: Sammlung „Haustiere“: Du hast nicht nur Namen von Hunden eingegeben. Du hast recherchiert und Daten mit Variabilität generiert: Angewandtes Chaos: Du hast Haustiere mit extremen Altersangaben (0 oder 25 Jahre) und seltenen Arten eingegeben, um die Suchfilter zu testen. Sammlung „Medicine“: Hier kommt die Genauigkeit ins Spiel. Angewandtes Chaos: Medikamente mit abgelaufenem Verfallsdatum, Nullbeständen und Preisen mit komplexen Dezimalstellen, um die Operatoren $lt (kleiner als) und $lte zu testen. Sammlung „sales“: Die Transaktionshistorie. Angewandtes Chaos: Verkäufe ohne zugehörige Haustier-ID oder mit negativen Beträgen, um zu sehen, ob das QA-System die mangelnde Integrität erkennt.

**Roll Integrationsspezialist (Brayan Hernandez)

Tätigkeitsbericht – Verbindung zu MongoDB Durchgeführte Tätigkeit: Heute habe ich über das Terminal eine Verbindung zur MongoDB-Datenbank hergestellt und dabei Figma als Design-Tool genutzt, um die Projektstruktur zu visualisieren.

Beschreibung des Prozesses: Zunächst habe ich Figma, eine Design-Anwendung, verwendet, um das Projekt visuell zu organisieren und zu strukturieren. Auf der Grundlage dieses Entwurfs habe ich alles in einem einzigen Ordner bearbeitet, wodurch die Dateien übersichtlich blieben und die Integration zwischen Design und Technik erleichtert wurde. Anschließend habe ich im Terminal daran gearbeitet, die Verbindung zu MongoDB herzustellen. Ich habe die erforderlichen Parameter konfiguriert und die entsprechenden Befehle ausgeführt, um die Kommunikation zwischen der Anwendung und der Datenbank herzustellen, sodass das Terminal die Daten korrekt an MongoDB senden konnte.

Aufgetretene Schwierigkeiten: Während des Prozesses traten beim Herstellen der Verbindung einige Probleme auf, die wahrscheinlich mit der Konfiguration oder der Ausführung von Befehlen im Terminal zusammenhingen. Diese Probleme konnten jedoch schnell behoben werden, nachdem ich die Fehler überprüft und die Konfiguration angepasst hatte.
Endergebnis: Es gelang, die Verbindung zu MongoDB erfolgreich herzustellen, sodass Daten vom Terminal an die Datenbank gesendet werden konnten. Der Einsatz von Figma erleichterte die vorläufige Organisation des Projekts, und die Verwaltung aller Elemente in einem einzigen Ordner trug dazu bei, die Entwicklung besser im Blick zu behalten.

**Roll des Scrum Masters (Annel Ricaño)

Die Abfragen wurden optimiert, um mehrere Filter und spezifische Ausschlüsse zu ermöglichen. A. Implementierung logischer Operatoren Im Folgenden werden die unter Verwendung der Syntax der MongoDB Query Language (MQL) entwickelten Abfragen detailliert beschrieben: Derzeit wird ein Dokumentationsordner erstellt, um die Filter zu erweitern.





