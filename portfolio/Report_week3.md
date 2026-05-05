“Mundo Animal” Veterinary Management System
Week: (April 13-17)

**Roll the Data Modeler (Alejandra Porras).

 In dieser Woche lag der Schwerpunkt auf der Architektur und dem technischen Design der Datenbank in MongoDB. Es wurden die notwendigen Grundlagen geschaffen, damit das System der Tierarztpraxis skalierbar und professionell ist:
•Entitätsmodellierung: Die drei grundlegenden Sammlungen wurden definiert und strukturiert: „pets“ für die Patientenverwaltung, „medications“ für die Bestandsverwaltung und „sales“ für die Transaktionsverwaltung. •Bestandsverwaltung: Die Medikamentensammlung wurde mit eindeutigen Identifikatoren (IDs), Stückpreisen und standardisierten medizinischen Kategorien konfiguriert. •Professionelles Transaktionssystem: Es wurde eine Verkaufsstruktur entworfen, die es ermöglicht, professionelle Dienstleistungen (wie Konsultationen und Bäder) mit Apothekenprodukten in einem einzigen Buchungsvorgang zu verknüpfen.

🠠 2. Herausforderungen und Lösungen Während des Entwurfsprozesses traten erhebliche Herausforderungen auf. Zunächst wies das Verkaufsschema sprachliche Unstimmigkeiten auf, da spanische und englische Begriffe vermischt wurden; dies wurde durch eine vollständige Umstrukturierung gelöst, um das gesamte System unter globalen Standards zu vereinheitlichen. Eine weitere Herausforderung war die Geschäftslogik in der Verkaufsabwicklung; anfangs berücksichtigten die Datensätze nur Apothekenprodukte, während die Dienstleistungen und Fachkräfte, die die Grundlage einer Tierarztpraxis bilden, ausgelassen wurden. Um dies zu beheben, wurde das Verkaufs-JSON neu gestaltet, um ein Array von Artikeln einzubeziehen, das mehrere Dienstleistungen und Produkte gleichzeitig unterstützen kann. Schließlich wurde sorgfältig daran gearbeitet, sicherzustellen, dass jede Transaktion eindeutig mit den im System registrierten Besitzern verknüpft ist, um zu gewährleisten, dass die Informationen konsistent sind und keine verwaisten Datensätze existieren.

** Rol de Query Developer (Tammy Nashely)

In meiner Funktion als MQL-Entwickler (MongoDB Query Language) war ich für die Konzeption, Implementierung und Optimierung der Datenabrufschicht des Systems verantwortlich. Mein Hauptaugenmerk lag darauf, eine effiziente Kommunikation zwischen dem Node.js-Server und dem MongoDB Atlas-Cluster sicherzustellen, damit das Verwaltungsteam sofort auf wichtige Patienteninformationen zugreifen kann.
•Technische Implementierungen: Ich entwickelte eine auf Benutzerflexibilität ausgerichtete Abfragearchitektur, wobei folgende technische Meilensteine hervorzuheben sind:

Segmentierung nach Tierart: Ich implementierte logische Filter zur Klassifizierung der Patientenpopulation (Hunde, Katzen usw.), was eine übersichtliche Darstellung der klinischen Arbeitsbelastung ermöglichte.
Erweiterte chronologische Analyse: Ich entwarf Abfragen unter Verwendung regulärer Ausdrücke (Regex), um medizinische Datensätze nach bestimmten Monaten und Jahren zu filtern, was die Erstellung von Berichten über regelmäßige Besuche erleichtert.
Kontaktindexierung: Ich strukturierte direkte Suchanfragen nach der Telefonnummer des Besitzers und optimierte so die Reaktionszeiten in Notfällen oder bei Nachsorge.
Alle Abfragen wurden getestet, um die neuen Attribute der Datenbank – darunter spezifische körperliche Merkmale und Geburtsdaten der Haustiere – dynamisch zu verarbeiten und so ein skalierbares und präzises System zu gewährleisten.

**Roll Integrations specialist (Brayan Hernandez)

Aufgabenbeschreibung. In dieser Woche wurde mit Vergleichsoperatoren in MongoDB gearbeitet, insbesondere mit $gt, $lt, $in und $ne, wobei der Schwerpunkt auf erweiterten Abfragen und der Filterung von Daten innerhalb der Datenbank lag.
Das Ziel bestand darin, diese Operatoren in Abfragen anzuwenden, um spezifische Informationen aus Sammlungen zu gewinnen, insbesondere in Szenarien mit numerischen Filtern und Listen.
Durchgeführte Aktivitäten. Ich habe die Struktur von Abfragen in MongoDB (MQL) analysiert. Ich habe Beispiele für erweiterte Filterung in queries/02_filters durchgesehen. Ich habe die Verwendung von Vergleichsoperatoren verstanden:
$gt (größer als) $lt (kleiner als) $in (in Liste) $ne (ungleich)
Ich habe die in der Übung geforderte Abfragelogik vorbereitet. Festgestellte Einschränkungen Derzeit ist es mir nicht gestattet, Abfragen direkt in der Datenbank auszuführen, daher: Ich konnte die Ergebnisse der Abfrage nicht in Echtzeit überprüfen. Ich musste ausschließlich mit der theoretischen Struktur arbeiten. Ich warte darauf, dass der Zugriff auf die Datenbank freigeschaltet oder aktualisiert wird, um mit den praktischen Tests fortzufahren.
Geforderte Übung Aufgabe: „Ich muss Produkte finden, deren Preis größer als 50 ist UND deren Lagerbestand kleiner als 10 ist.“
Lösung (MQL-Abfrage)
db.products.find({ price: { $gt: 50 }, stock: { $lt: 10 } })
Erläuterung der Operatoren $gt (größer als) Filtert die Dokumente heraus, bei denen das Feld „price“ größer als 50 ist. $lt (kleiner als) Filtert die Dokumente heraus, bei denen das Feld „stock“ kleiner als 10 ist. Beide Bedingungen werden implizit mit einem AND verknüpft, da sie sich innerhalb desselben Objekts befinden. Erwartete Ergebnisse Es werden alle Produkte erwartet, die: einen Preis von mehr als 50 haben UND einen Lagerbestand von weniger als 10 Einheiten.

**Rolle der Datenverarbeiterin/QA (Ximena Rosas)

Erstellung synthetischer Daten: Erforschung, wie Millionen von Datensätzen erstellt werden können, die echt wirken, aber alle möglichen Variationen abdecken (lange Namen, nicht existierende Adressen, E-Mails mit ungewöhnlichen Formaten).
Edge-Case-Analyse (Grenzfälle): Identifizierung der Systemgrenzen. Wenn ein Feld Zahlen von 1 bis 100 akzeptiert, konzentriert sich deine Untersuchung darauf, was passiert, wenn du 0, 101, -1 oder ABC eingibst.
Wichtige Tools, die du beherrschen solltest Um in dieser Rolle ein Experte zu sein, sollte deine Recherche folgende Technologien abdecken: A. Mockaroo (Deine Hauptwaffe) Es ist das Standard-Tool zur Datengenerierung. Du solltest untersuchen:
Custom Logic: Wie man Formeln verwendet, damit ein Feld von einem anderen abhängt (z. B.: Wenn das Land „Mexiko“ ist, muss die Postleitzahl 5 Ziffern haben).
Verknüpfte Datensätze: Wie man JSON-Dateien generiert, die miteinander verknüpft sind (dass die product_id in der Sammlung „Verkäufe“ tatsächlich in der Sammlung „Produkte“ existiert). B. MongoDB Shell & Compass Als Data Seeder musst du Daten schnell verschieben:
mongoimport / mongoexport: Terminalbefehle zum massiven Laden von JSON-/CSV-Dateien.

**Roll Scrum Masters (Annel Ricaño):

 Im Laufe der Woche habe ich die aufgetretenen Blockaden bewältigt und die Standardisierung vorangetrieben. Mein Ziel war es, eine kurze Retrospektive über die Blockade durchzuführen, die während [...]. *Konsens fördern: Moderation einer kurzen Sitzung (Daily oder Refinement), um zu beschließen, dass Englisch der offizielle Standard sein soll. *Kohärenz gewährleisten: Sicherstellen, dass alle wussten, dass sich die Felder geändert hatten (z. B. von „mascotas“ zu „pets“), damit ihre Abfragen nicht fehlschlugen. A. Den „Blocker“ identifizieren: Im Board (Jira/Trello/GitHub) vermerken, dass die Rolle „Integration“ blockiert ist. B. Eskalation: Sprechen Sie mit dem Administrator des MongoDB Atlas-Clusters oder dem IT-Manager, um die Zugangsdaten zu erhalten. C. Abhilfe: Falls der Zugriff zu lange dauert, schlagen Sie vor, MongoDB Playground oder einen lokalen Docker-Container zu verwenden, um die theoretische Logik zu validieren.




