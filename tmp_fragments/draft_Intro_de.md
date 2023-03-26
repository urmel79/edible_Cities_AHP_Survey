# Einleitung

Der Analytic Hierarchy Process (AHP) ist eine gängige und inzwischen weit verbreitete Methode, um auf der Basis mehrerer verschiedener Kriterien über eine Alternative zu entscheiden. Häufig erfolgt die Gewichtung der jeweiligen Kriterien durch eine geringe Anzahl von Entscheidungsträgern oder gar einen einzelnen Entscheidungsträger. Der AHP lässt sich dann organisatorisch wie auch technisch relativ einfach bewerkstelligen.

Wesentlich seltener findet die Gewichtung der Kriterien, die für die Entscheidungsfindung genutzt werden, durch eine Vielzahl verschiedener Stakeholder statt. Jedoch ist gerade für Entscheidungsfindungen mit hoher gesellschaftlicher Relevanz die Einbeziehung vieler Stakeholder sehr wichtig. An dieser Stelle stellen sich dann folgende Fragen:

1. Wie erhebe ich die Daten?
2. Welche Software bzw. welches Tool kann einen AHP mit Daten aus der Befragung einer Vielzahl von Stakeholdern durchführen?
3. Wie lässt sich die Datenerhebung und -verarbeitung sowohl organisatorisch als auch technisch sinnvoll und zeitlich effektiv kombinieren?

Im Rahmen des DFG-geförderten Projekts "Essbare Städte" war es das Ziel, verschiedene Formen urbaner Landwirtschaft mittels AHP hinsichtlich ihrer Nachhaltigkeit zu bewerten. Voraussetzung dafür war die Einbeziehung zahlreicher Stakeholder verschiedener Zielgruppen in die Gewichtung der zuvor selektierten Kriterien und Unterkriterien. Die für die Gewichtung erforderlichen paarweisen Vergleiche der Kriterien und Unterkriterien sollten mittels einer online-Befragung durchgeführt werden, an die sich idealerweise die AHP-Berechnung automatisch direkt anschließen sollte. Da es sich bei den hier befragten Stakeholdern überwiegend um Menschen aus dem nicht-wissenschaftlichen Umfeld handelte, musste die Befragung an diese Zielgruppen angepasst strukturiert werden.

Nach Kenntnis der Autoren existiert als einziges online-Tool zur Durchführung einer Befragung in Kombination mit einer sich direkt anschließenden Kriteriengewichtung nur "AHP-OS" von [BPMSG (Business Performance Management Singapore)](https://bpmsg.com).

Obige Anforderungen insbesondere bzgl. der Zielgruppen reflektierend erschien "AHP-OS" jedoch ungeeignet, da es zu stark darauf ausgelegt ist, konsistente Datensätze zu generieren. Dazu werden die Teilnehmer ggf. mehrfach gebeten ihre Entscheidungen zu überdenken und in Richtung Konsistenz anzupassen. Dieses sehr wissenschaftliche Vorgehen wäre für die angestrebten Zielgruppen nicht passend gewesen.

Daher verfolgten die Autoren den Ansatz, die Befragung der Stakeholder und die  anschließende Gewichtung der Kriterien organisatorisch und technisch voneinander zu trennen.

Das vorliegende Paper stellt erstmalig eine Prozedur vor, bei der die mit Hilfe der online-Befragungsplattform [SoSci Survey](https://www.soscisurvey.de) erhobenen Daten anschließend mit dem Paket "ahpsurvey" verarbeitet werden. Dieses Paket ist ausschließlich für die Statistik-Programmiersprache "R" verfügbar und erfüllt nach Kenntnis der Autoren als einziges Tool die in den vorigen Abschnitten skizzierten Anforderungen.
