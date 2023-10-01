---
permalink: /studioreflection/
title: Studio Reflection
excerpt: A preliminary report on the studio project done in October 2023
last_modified_at: 2021-05-11T10:23:16-04:00
toc: true
layout: single
classes: wide
header:
  overlay_image: /assets/images/about_header.jpeg
  overlay_filter: 0.5
author_profile: false
author: Aron Petau
tags:
  - radio
  - broadcast
  - rtl-sdr
  - antenna
  - software-defined
  - radio
  - public
  - sphere
  - subversive
  - listening
  - pirate
  - radio
  - police
  - radio
  - BOS
  - studio
  - d+c
  - university
  - of
  - the
  - arts
  - berlin
  - udk
  - TODO,
  - unfinished
created: 2023-07-26T23:41:07+02:00
updated: 2023-10-01T20:08:25+02:00
---

## Studio Bericht SS23
#### Aron Petau, Joel Tenenberg
30.90.2023

### Abstract
Radio as a Subversive Exercise
Radio is a prescriptive technology. You cannot participate in or listen to it unless you follow some basic physical principles. Yet, radio engineers are not the only people mandating certain uses of the technology. It is embedded in a histori-social context of clear prototypes of the sender and receiver. Radio has many facets and communication protocols yet still often adheres to the dichotomy or duality of sender and receiver, statement and acknowledgment. The radio tells you what to do, and how to interact with it. Radio has an always identifiable dominant and subordinate part.
Are there instances of rebellion against this schema? Places, modes, and instances where radio is anarchic? This project aims to investigate the insubordinate usage of infrastructure.
Its frequencies.
It's all around us.
Who is to stop us?

### Kooperativer Teil:

*Inhaltlich-konzeptionelle Beschreibung eurer bisherigen Arbeit: Wie lautet eure Forschungsfrage bisher? Welche Fortschritte habt ihr in der Beantwortung von dieser schon gemacht? Bitte nennt hier auch Referenzen (Literatur, Künstler*innen/ Artworks, Projekte, etc.)*

**Forschungsfrage**
Im Verlauf des letzten Semesters haben wir uns mit der Frage auseinandergesetzt, wo Instanzen der Zersetzung von hegemonialen Machtverhältnissen in der Infrastruktur von Funk sind. Dabei versuchen wir herauszufinden, inwiefern diese aufgezeigt werden und im Weiteren direkt erfahrbar und spürbar gemacht werden können.

Begonnen hat unsere Recherche mit einer SDR Antenne, die Aron gekauft hat. SDR steht für Software Defined Radio, wir reden hier also über eine Antenne und einen zugehörigen digitalen Verstärker, die in der Lage sind, ein extrem breites Spektrum an Funkfrequenzen zu empfangen. Diese Antenne unterscheidet sich insofern von einem traditionellen Radio, als dass Sie digital auswertbar und somit algorithmisch nutzbar ist, sowie eben über ein deutlich weiteres Spektrum an Frequenzen verfügt.
Durch die SDR Antenne und GQRX, einer Python-basierten Software, konnten wir die transmittierten Informationen teilweise decoden.
![[assets/images/radio/gqrx.png]]
Wir verstehen Funk als eine Methode, eine Technologie. Die moderne Gesellschaft macht sich hier bestimmte Elektromagnetische Eigenschaften in der Physik zu eigen und kann diese auf extrem vielfältige Weisen einsetzen. Von GPS über Mobilfunk zu Fernbedienungen, bestimmt Funk unser tägliches Leben und fällt häufig nur auf, wenn es fehlt, ein klares Merkmal von Infrastruktur im Allgemeinen.

Funk ist insofern gleichzeitig offen und geschlossen, als dass die Frequenzen nach physikalischen Gesetzmäßigkeiten agieren und sich nur bedingt manipulieren lassen. Sie sind pervasiv und missachten politische Grenzen. Anders jedoch die Übertragung der hier eingespeicherten Informationen. Damit sich Daten in Sinuskurven kodieren lassen, gibt es viele verschiedene Ansätze und Algorithmen zum abspeichern und einlesen von Informationen hierin. Manche Ansätze nutzen Amplitudenmodulation (AM) oder Frequenzmodulation (FM). Es gibt allerdings auch Mischkonzepte und abenteuerlichere Formate. Hier, in der En- und Decodierung werden natürlich auch viele Übertragungen noch zusätzlich verschlüsselt.
Im Sinne der Erfindenden ein großartiges Feature: ein Kommunikationskanal, der keinerlei Kabel benötigt und somit für die Kommunikationsteilnahme Vieler immer verschwindendere Kosten verbuchen kann. Das Radio ist geboren für die one-to-many Kommunikation.
In Deutschland, und in vielen anderen Ländern auch, ist die Verpachtung der entsprechenden Frequenzen eine staatliche Angelegenheit, mit engen Regularien und Vorschriften über die Nutzung von Frequenzen. Schaut man sich die Situation über die
Bundesnetzagentur (siehe Quellenverzeichnis) an, wird schnell klar, dass hier eine extrem hierarchisch funktionierende Struktur vorliegt, die sich größtenteils an Kapitalverhältnissen ausrichtet.

Bestimmte, sicherheitsrelevante Frequenzen sind gesetzlich sogar soweit gesichert, dass das bloße anhören der noch verschlüsselten Signale unter Strafe steht (siehe BOS-Funk).
Hier verschiebt sich also die Grenze des Unauthorisierten massiv zugunsten der Kapital und Infrastrukturträger*innen.
Mit Bezug auf BOS-Funk ist also die bloße Teilhabe an der Infrastruktur, das Mithören von Kommunikation von Polizei, Feuerwehr und anderen Staatlichen Instrumenten bereits eine sträflich zu verfolgende Machtzersetzung.

Nichtsdestotrotz existieren schon lange Subkulturen, die vorhandene, offene Frequenzen für private und gesellschaflich relevante Zwecke nutzen, zum Beispiel die in Deutschland aktive Hobbyfunkerszene, Freifunk oder quelloffene Standards zu Wetterballons und -stationen.
Funk befindet sich also in gewisser Weise in einer Dualität: Als Herrschaftsinstrument und als subversives, oder einfach nur nicht-regierbares Mittel.
Es gibt also in der Methode "Funk" ein unauthorisiertes, illegales Element, das sich über Grenzen hinwegsetzt und durch seine technische Beschaffenheit anarchische Strukturen fördert.

Die zu untersuchende Subversion hat hier 2 Teile:
	Den Akt des **Empfangens** und
	Den Akt des **Sendens**
Beide können auf eigene Art Subversiv sein.
Ein Beispiel für subversives Empfangen wäre also das mithören von Polizeifunk, oder das in der DDR berühmte Hören von "Westradio"
Subversives Senden kann sich ausdrücken beispielsweise in sogenannten Piratensendern, von denen es historisch seit Beginn des Radios immer welche gab, zum Beispiel das Radio freies Wendland (siehe Quellen).

**Wie passt Hacking ins Bild?**
Alles Mögliche an alltäglicher Infrastruktur nutzt öffentliche Funksgnale:
Autotüren, Garagentore, Walkie Talkies, Flugzeuge, Krankenwagen, Funkuhren, Wetterstationen, Ampeln, Smartphones ...
Hacking versteht sich als unerlaubter Zugriff auf Systeme und Informationen. Das Bild eines Einbrechers, der sich Zugang zu einem Serverraum verschafft, lässt sich aber schwer zusammenbringen mit einer Funkantenne, die Informationen im eigenen Wohnzimmer empfängt. Eine Frage, die uns interessiert, ist also: Wo beginnt der Unerlaubte Zugriff, wenn wir Schwingungen im Raum als System betrachten?

### Exkurs Infrastruktur:
Oftmals wird der Begriff Infrastruktur als grobe Kategorie von verschiedenen allgegenwärtigen Netzwerkressourcen, wie Straßen, Bahnschienen, Wasser- und Abwasserrohren, Stromversorgung und -leitungen gesehen. Das Feld der Infrastruktur lässt sich jedoch auch auf Informationssysteme und Datenspeicherungen erweitern. Wir haben in diesem Kontext Funk als Technologie mit einer Infrastruktur identifiziert. Die Bundesnetz Agentur verwaltet die Senderechte für die bestimmten Frequenzen und organisiert die Versteigerung unter Unternehmen. Sowohl der hegemonielle Status, wie auch das Machtpotenzial dieser Infrastruktur sind weder deutlich im Alltag zu erkennen noch einfach zu analysieren. Um eine subversive Aktion innerhalb der Infrastruktur von Funk zu planen, muss diese erst analysier- und sichtbar gemacht werden.
In "Database Infrastructure – Factual repercussions of a ghost" beschreibt Francis Hunger die Attribute von Infrastrukturen und Wege, diese sichtbar zu machen. Der Text bezieht sich dabei auf Databases, also Rechenzentren und Datenspeicher, die Ansätze sind jedoch auf andere Infrastrukturen anwendbar.

Die erste beschriebene Methode ist das Spiel mit einem hypothetischen Szenario, bei dem von einem Breakdown der Infrastruktur ausgegangen wird. Der Allgegenwärtige und unantastbare Charakter der Infrastruktur wird so kritisch hinterfragt und die mit einem Ausfall einhergehenden Ängste und Abhängigkeiten abgebildet.
Eine weitere Methode der Sichtbarmachung ist die Dokumentation und Verortung von infrastrukturellen Bauwerken auf Karten, durch Fotos, Videos oder einfachen Standortmakierungen. Im Falle von Funk können hierzu Funkmasten, Dachmasten oder kleine Smallcells endeckt, fotografiert und kartiert werden.
Diese Art des Sichtbarmachens soll keine Panik vor Funkmasten schüren, sondern nur den scheinbar unsichtbaren Charakter von Infrastrukturen aufzeigen.
Diese Erkundungstouren können auch als Gruppe durchgeführt werden und einem Workshop Format ähneln.
Die letzte beschriebene Methode wurde von Lisa Parks entwickelt und als Infrastructure inversion bezeichnet:

	*"Parks argues, that infrastructure is often of high complexity, that even with full access to all resources it would be difficult to describe an infrastructural setting in its entirety and to make it comprehensible.
	Rather, Infrastructural inversion tries to deduct its underlying classification systems and standards from a small portion of the infrastructural complex."*
-- Lisa Parks

Gerade im Bereich der Kommunikation ist das eigentliche Infrastruktur Netz aus von Walkie Talkies bis zu Satelliten schwer zu überschauen. Infrastructure Inversion bietet eine Möglichkeit von einem kleinen observierbaren Teil auf die große allumfassende Struktur zu schließen.
Die beschriebenen Methoden müssen nicht als einzelne Ansätze gesehen werden, sondern lassen sich im besten Fall miteinander verknüpfen und bilden verschiedenen Arbeitsphasen in einer vollumfänglichen Strukturanalyse ab.

Ein **Experiment** zur Sichtbarmachung von Funksignalen haben wir bereits durchgeführt.
Dafür haben wir einen Oscillator an ein SDR Audio Signal einer SDR Antenne angeschlossen und Signale empfangen. Wir haben sowohl Radio Signale auf verschiedenen Frequenzen empfangen und dargestellt, als auch direkt im Raum mit Walkie Talkies geredet und die Funksignale erfolgreich abgebildet.
Da der Ausschlag von Frequenzen eindimensional ist, haben wir zum Ausschlag des Signals auf der y-Achse eine Sinuskurve auf die x-Achse gelegt.
Dieser Versuch dient zur Demonstration des allanwesenden Funkverkehrs. Wir sehen das Sichtbarmachen als Praktik des Aufzeigens von Infrastruktur im öffentlichen Raum und einhergend das Erschaffen eine besser Wahrnehmung dieser. Darauffolgend lassen sich Disskusionen über Nutzungsrechte und verteilung von Ressourcen innerhalb der Infrastruktur anstoßen.

Im Feedback zu dem Versuch wurden Paralellen zum 90s modder style gezogen und durch den sehr rohen Aufbau starke Synth vibes evoziert. Der Fokus der Anwesenden lag viel mehr auf der Hardware die wir genutzt haben als auf dem eigentlichen Fokus der Sichtbarmachung von Funk. Der Versuch hat uns gezeigt, dass es mehr Ebenen der Sichtbarmachung braucht, um den gewollten Effekt einer erhöhten Sensibilisierung für die Infrastruktur zu provozieren.

### Pros und Cons im Team
*Arbeitsprozess + Reflexion: Geht darauf ein, wie sich der kollektive Arbeitsprozess für euch gestaltet hat. Was hat im Team gut funktioniert und was waren Herausforderungen?*

Wir haben uns zu dieser Aufgabe erst ziemlich spät im Semester zusammengefunden, doch bisher klappt eine zusammenarbeit oft sehr gut. Kommunikation über Aspekte des Themas klappt gut, wir beschäftigen uns auch beide individuell mit eigenen perspektiven zum Thema. Bisher war es allerdings nicht ganz offensichtlich, wie wir beide unsere Fokuspunkte so einbringen können, dass sie ein kohärentes Ganzes ergeben. Das war noch kein großes Problem, da wir uns noch in einer sehr offenen und explorativen phase befinden, in der häufige Perspektivwechsel und neue Inputs hilfreich erscheinen. Gleichzeitig hat uns das aber in der Konkretisierung und genaueren absteckung des Themas behindert. Treffen finden häufig statt und fühlen sich produktiv an. Wir haben zu Beginn wohl leider zu wenig Protokoll geführt, sodass ein Zwischenbericht ohne einen lebendigen Prototypen für uns zu Früh in unserer Entwicklungsphase stattgefunden hat.

Was hat gut geklappt?
Unser größter gemeinsamer Themenbereich ist die kritische Hinterfragung von Machtmonopolen und deren Subversion. Wir sind beide motiviert dieses Projekt in eine konkrete Form zu bringen, gerade weil wir durch die verschiedenen persönlichen Forschungsansätze bereits eine solide Wissensgrundlage geschaffen haben.

3. Projektskizze:
Im Verlauf des Semesters haben wir verschiede Projekte skizziert. Im Kontext unserer Recherche beziehen sich diese Projekte immer auf das Thema der Sichtbarmachung, bzw. der Subversion.

**Avenue I:** Sphere Projection, Funk spürbar/sichtbar machen
Ausgehend von der Motivation, Funk sichtbar zu machen, ist ein Ansatz eine Installation zu planen. Vielleicht kann diese auch in soziale Gegebenheiten eingreifen und sie verändern. Es wäre möglich eine begehbare Kugel aufzustellen, in der alle empfangbaren Funksignale graphisch projektiert werden. Diese könnten mit Infos zur Betreibern und Ownership der Signale unterfüttert werden. Interessant wäre es eine Möglichkeit einzubinden empfangene Signale zu Interrupten. Der Fokus sollte auf dem visuellen Feedback für Funk Signale liegen und die unsichtbare Agency mit Machtpotenzial darstellen.

**Avenue II:** Drone Scan
Auch auf eine Sichtbarmachung der Daten im Raum fokussiert, ist das Konzept einer 360 Grad Momentaufnahme mit verschiedenen Ebenen. Dafür nimmt eine Drohne auf verschiedenen visuellen Kanälen Panoramas auf, die in der Nachbearbeitung übereinander gelegt werden. Es entsteht die Visualisation von normalerweise unischtbaren Informationsebenen. Im besten Fall können dadurch sogar Rückschlüsse auf unsichtare Infrastruktur gemacht werden, zum Beispiel bei Funksignalen aus Gebäuden oder durch Bilder einer Wärmekamera. Inspiration für diesen Versuch haben wir aus dem Video von

**Avenue III:** Datenkrake
Um die stille generierung und extraktion von Daten zu untersuchen haben wir die Idee einer Datenkrake gehabt. Eine Apparatur, die alle erfassbaren Daten in einem Raum aufnimmt und dokumentiert. Es soll vorallem auf das übergriffige, nicht-konsensuellen Sammeln von Daten aufmerksam machen. In kombination mit dem Stichwort Datenkapitalismus soll dieser Versuch sensibilisieren und aufzeigen wie schnell Daten extrahiert und für eine eigene Sache benutzt werden können.

### Outlook
Wie möchtet ihr eure Projektskizzen im kommenden Semester weiterführen? Welche Potentiale ergeben sich daraus für euch als Team? Worauf hättet ihr Lust? Wie möchtet ihr eure Zusammenarbeit weiter gestalten?

In den nächsten Wochen möchten wir gern Individuelle Beratungsgespräche nutzen, um dem gerade noch sehr weit offenen Projekt eine klarere Form zu geben.
Wir sind auch damit beschäftigt, einige kleinere Prototypen zu erstellen, die alle Funk sichtbar machen. Das erste Experiment, das mit Sichtbarmachung der Amplitude gearbeitet hat, ist nur ein Weg, Radiowellen visuell oder haptisch darzustellen.

### Perspektive: Aron
*Verfasse einen Text, in dem Du darauf eingehst, wie Du deine individuellen Perspektiven und Positionen in den kollektiven Arbeitsprozess eingebracht hast.
Gebe einen Ausblick darauf, wie Du deine individuellen Positionen und Themen im kommenden Semester weiterentwickeln möchtest und wie Du diese Themen in (neue) Teams einbringen und weiterentwickeln möchtest.*

Keywords: prototyping, hacking, queering funk, alternative communication, disruptive, Subversion

Im letzten Semester, hauptsächlich im Kurs Politics of Design habe ich mich mit Hegemonien und ihrer Durchbrechung beschäftigt.
Eine Hegemonie als das gesellschaftlich unmarkierte, dominante narrativ zu einem bestimmten Fokusfeld. Hegemonien und Infrastruktur bedingen sich in vielen fällen gegenseitig, da Infrastruktur oft genau das beschreibt, was die Hegemonie aufrecht erhält. Die Begriffe überlappen also, wobei Infrastruktur eine gegebene Möglichkeit, ein Potenzial suggeriert und die Hegemonie sich eher auf die Machtverhältnisse in einem gegebenen sozialen system konzentriert. Im POD Kurs war das ergebnis dann ein Mobiler autonomer Staat, der also Machtverhältnisse durch eine Gegenmacht temporär zersetzt.
Die Frage, ob für den Abbau von Hegemonien Gegenmächte, oder "Counter-Hegemonies" (Laclau, Mouffe) benötigt werden, ist für mich selbst nicht ganz eindeutig. Was mich hier aber besonders interessiert, ist der Akt des Hervorholens, des Markierens, der Sichtbarmachung. Hegemoniale Kontinuitäten werden durch schweigen erzeugt und durch Markierung geschwächt. Eine solche Markierung hat viele Gesichter, eine gute Darstellung zeigt sich in den "queering devices" von Sara Ahmed, die gesellschaftliche Normen und Gegebenheiten im Gegensatz dazu als "straightening devices" festmacht. Wir reden also immer über eine bewusste Nichtachtung von normen oder ihrer Überschreibung durch anders geartete praktiken.
 Ich finde, dieses Phänomen wird am besten durch "hacking" beschrieben. Hier kommt der bewusste teil viel mehr heraus, da beim Hacking natürlich auch immer mit gesetzlichen Normen und Legalität gespielt wird.

Hacking hat immer ein widerständiges Element, die Idee, einem gedachten Nutzungsszenario zuwider zu handeln.
Lässt sich diese Idee auf funk Übertragen, dreht sich nun alles um die Frage, welche Nutzungsszenarien In Radio, Funk und drahtloser Kommunikation im allgemeinen innewohnen.

Im Semester war mein Hauptproblem, dass es mehrere Projekte gleichzeitig gab und eine klare prioritisierung erst spät stattgefunden hat. Als zusätzlichen Faktor habe ich den Rundgang als hinderlich empfunden. Ich habe ganz bewusst und gezielt wenig auf dem Rundgang gezeigt, und es war doch noch zu viel Mehrarbeit. Gerade im Kontext des Studios und der Studioarbeit ist eine der größten Herausforderungen das Abschätzen von Zeit und Aufwand, das eben doch immer wieder nicht erfolgreich funktioniert.
Ich halte es für sehr wertvoll, dass wir als Gruppe größtenteils selbstorganisiert und eigenständig recherchieren, handeln und ausstellen können, dabei Fehlt aber immer der Rahmen und die zeit zum Abstimmen, planen und gemeinsamen Kuratierens. Immer wieder sind wir im vergangenen Semester an die Barriere gestoßen, dass das Inhaltliche weiterarbeiten an einem Projekt total entgrenzt stattgefunden hat, sodass das gemeinsame organisieren, sowie das Vor- und Nachbereiten von gemeinsamen Arbeiten konstant gelitten hat und oft gar nicht stattgefunden hat.

Mich haben die Thematischen Richtungsgeber rund um das Setting "Terrestrial" gut weitergebracht, ich habe mich inhaltlich sehr gut unterstützt gefühlt und hatte das Gefühl, mich in einem für mich sehr relevanten Themenkreis zu bewegen. Die Exkursion hat mich in der Gruppenzusammenarbeit gestärkt und ein schönes Arbeitsklima erzeugt. Schon dort, im Bezug auf "Fences" kommt ein wichtiges Element durch, das auch jetzt noch im Radio Projekt drin steckt. Doch auch hier hatte ich das Bedürfnis nach mehr Raum für Organisationsprozesse und gemeinsame Reflektion/Nachbereitung.

### Perspektive: Joel
Joel: Infrastruktur, Machtverhältnisse, Ownership von Daten und Infrastruktur

In dem letzten Semester habe ich mich intensiv mit dem Thema der Datenextraktion auseinandergesetzt. Dabei habe ich mich weniger auf den eigentlichen Akt der Datenextraktion und mehr auf die Strukturen, die diese ermöglichen konzentriert. Dieses Thema habe ich versucht in den kollektiven Arbeitsprozess unserer Studiengruppe einfließen zu lassen. Im Verlauf der weiterführenden Recherche habe ich meinen Fokus auf weitere Themen erweitert. Darüber möchte ich einen kurzen Überblick verschaffen:

Angefangen bei dem Überbegriff der Datenextraktion, dessen Vielschichtigkeit ich in dem Projekt Trees mit Yagmur bereits untersucht hatte, führten weitere Untersuchungen in den Bereich der Megastrukturen und Hyperobjects. Also Strukturen, die die menschliche Wahrnehmung überschreiten und immensen Einfluss auf unsere Umwelt, soziale Begebenheiten und Machtverhältnisse haben. Untersuchungen in diesem Bereich zeigen das hohe, aber undurchsichtige und verschleierte Machtpotenzial dieser Strukturen. Megastrukturen und Hyperobjects sind dabei nicht als konkrete Bauwerke zu sehen, sondern als eine Kategorie durch die bereits bekannten Strukturen neu analysiert werden.

Hyperobjects sind komplexe Phänomene, die schwer fassbar sind und eine Vielzahl von Auswirkungen auf unsere Welt haben. Untersucht man Infrastrukturen in dem Kontext der Hyperobjects wird ihre Systemrelevanz und gleichzeitige Ungreifbarkeit offengelegt. Diese Infrastrukturen, wie etwa Datenzentren, sind für die meisten Menschen unsichtbar, aber sie spielen eine entscheidende Rolle in unserer vernetzten Welt und ihre Kontrolle liegt in privater Hand. Als Hyperobjects sind Datenzentren nicht nur als Solitäre zu sehen, sondern sie bilden einen kleinen Teil in einem größeren Netz aus Infrastrukturen, deren Daten sie speichern. Die Nutzung dieser, oft systemrelevanten Infrastrukturen, generiert Daten, die im Fall einer privaten Verwaltung zur Kapitalisierung genutzt werden.
Durch die Datenextraktion im öffentlichen Raum sind die gesammelten Daten eigentlich Gemeingut und sollten nicht der Gewinnoptimierung, sondern wieder der Verbesserung des sozialen Miteinanders zugutekommen. Niklas Maak beschreibt in seinem Servermanifest2 mögliche Ansätze einer Demokratisierung von Nutzungsdaten. Er plädiert dafür, Daten als öffentliches Gut zu begreifen und auf eine Ebene mit Wasser, Strom und sauberer Luft zu stellen. Diese Ansätze sind wichtig, um den Status Quo anzufechten und neue Wege der Datenverarbeitung real werden zu lassen.
Außerdem beschreibt Maak das widersprüchliche Verhältnis von Datenzentren zu Daten. Das Bild der Cloud suggeriert zwar eine immaterielle Speicherung der Daten, die zugrunde liegenden Infrastrukturen werden jedoch oft in riesigen Komplexen aus fensterlosen anonymen Hallen in Wüsten und vor Städten gebaut. Eine Architektur die sich aus dem Bild der Stadt und damit aus dem Bewusstsein der Menschen entzieht.

Um von dem Thema Datenzentren wieder einen weiter gefassten Forschungsansatz zu bekommen, habe ich mich dem größeren Konzept der Database gewidmet. Angeleitet durch das Buch Search Routines: Tales of Databases3 des D21 Kunstraum Leipzig, habe ich wieder im Kontext der Hyperobjects versucht die Database in Ihrer Entstehung und Ausdehnung zu untersuchen. Das Buch ist eine Zusammenfassung verschiedener Projekte und Workshops, die sich kritisch mit dem Thema der Datenorganisation, Datenextraktion und Datenspeicherung auseinandersetzen. Ein besonderer Beitrag ist der Text von Francis Hunger Database Infrastructure – Factual Repercussions of a Ghost, der nicht nur die historische Entwicklung von Databases beschreibt, sondern auch Methoden zur Sichtbarmachung erläutert. Eine interessante Methode ist die Infrastructure Inversion, entwickelt von Lisa Parks, die die eigentlich essenziellen Charakteristika der Infrastructure und Hyperobjects, wie Unüberschaubarkeit und Unfassbarkeit absichtlich ignoriert und diese Strukturen anhand von kleinsten, observierbaren Details analysiert.
Dieser Ansatz eignet sich besonders gut, um ihn in ein Studioprojekt einzubeziehen, da er sich mit überschaubaren Dimensionen auseinandersetzt, dabei aber nicht die größeren Skalen auslässt. Im Verlauf der Recherche habe ich Kontakt zu Francis Hunger aufgenommen und wir konnten uns über seine Arbeit austauschen. Er hat mir weitere Texte von Ihm zugeschickt und interessante weitere Referenzen gegeben. Der Kontakt zu einer Person außerhalb des Studiums mit diesem Schwerpunkt war äußert hilfreich und motivierend.

Besonders innerhalb der Gruppe haben wir Funk als eine interessante Infrastruktur entdeckt. Funk bietet eine großflächig gebaute Infrastruktur, eine interessante Historie und lässt sich schon mit kleinen Geräten nutzen. Ich möchte mich in Zukunft auch mit den visuellen Erscheinungen solcher Megastrukturen auseinander setzten, zum Beispiel durch eine Dokumentation von Funktürmen und -masten. Mein persönliches Ziel ist es, die zugrundeliegenden Infrastrukturen bestehender Machtverhältnisse aufzuzeigen und durch die neu entstandene Wahrnehmung dieser eine natürliche Aufmerksamkeit zu erzeugen. Es geht darum, die Gesellschaft für die Auswirkungen dieser Megastrukturen und unsichtbaren Infrastrukturen zu sensibilisieren. Im kommenden Semester möchte ich weiter zu Machtverhältnissen und Infrastrukturen forschen und die Ergebnisse als Fundament für eine künstlerische Auseinandersetzung nutzen.

Die Zusammenarbeit mit Aron ist interessant, auch wenn wir es bisher noch nicht geschafft haben unsere beiden Interessen konkret zu vereinen. Eine Konkretisierung unserer vereinten Forschungsfrage möchte ich auf jeden Fall zeitnah angehen. Dabei haben wir auch schon mit Johannes über ein Beratungstermin geredet.

### Quellangaben:

[1] Morton T. Hyperobjects: Philosophy and Ecology After the End of the World. Minneapolis:
University of Minnesota Press; 2014.

[2] Maak, Niklas. Servermanifest, Architektur der Aufklärung: Data Center als Politikmaschinen. Hatje Cantz, 2022.

[3] Hunger, Francis. Search Routines: Tales of Databases. D21 Kunstraum Leipzig, 2015.

[Lisa Parks on Lensbased.net](https://rcpp.lensbased.net/infrastructural-inversion-or-how-to-open-black-boxed-database-management-systems/){: .btn .btn--large}

[Hunger, Francis über Infrastrukturen und Databases](https://www.irmielin.org/wp-content/uploads/2015/12/search_routines-tales_of_databases.pdf){: .btn .btn--large}

**Maak**, Alexander, Servermanifest Architektur der Aufklärung: Data Center als Politikmaschinen. Hatjecantz, 2022

**Bastani**, Aaron. Fully automated luxury communism. Verso Books, 2019.

**Morozov**, E. (2016). The net delusion: How not to liberate the world. In Democracy: A Reader (pp. 436-440). Columbia University Press.

**Stäheli**, U. (1999). Die politische Theorie der Hegemonie: Ernesto Laclau und Chantal Mouffe. Politische Theorien der Gegenwart, 143-166.

**Gramsci** on Hegemony: [Stanford Encyclopedia](https://plato.stanford.edu/entries/gramsci/){: .btn .btn--large}

[TLDR on Mouffe/Laclau](https://www.youtube.com/watch?v=62a6Dk9QmJQ){: .btn .btn--large}

Alex **Demirovic**: [»Hegemonie funktioniert nicht ohne Exklusion« ](https://www.youtube.com/watch?v=h77ECXXP2n0){: .btn .btn--large}

**Ahmed**, S. (2020). Queer phenomenology: Orientations, objects, others. Duke University Press.

### Sonstige Quellen
Was für eine Antenne haben wir:
[NESDR Smart](https://www.nooelec.com/store/sdr/sdr-receivers/nesdr-smart-sdr.html){: .btn .btn--large}

Was für eine Antenne hätten wir gern:
[HackRF One](https://greatscottgadgets.com/hackrf/one/){: .btn .btn--large}

Frequency Analyzer + Replayer
[Flipper Zero](https://shop.flipperzero.one/){: .btn .btn--large}

Hackerethik
[CCC Hackerethik](https://www.ccc.de/hackerethics){: .btn .btn--large}

Radio freies Wendland
[Wikipedia: Radio Freies Wendland](https://de.wikipedia.org/wiki/Radio_Freies_Wendland){: .btn .btn--large}

Freie Radios
[Wikipedia: Definition Freie Radios](https://de.wikipedia.org/wiki/Freies_Radio){: .btn .btn--large}

**Radio Dreyeckland**
[RDL](https://rdl.de/){: .btn .btn--large}

[RND Newsstory: Querdenker kapern Sendefrequenz von 1Live](https://www.rnd.de/medien/piratensender-kapert-frequenz-von-1live-fur-querdenker-thesen-MER4ZGR2VXNNXN6VZO3CVW6XTA.html){: .btn .btn--large}

[NDR Reportage: Westradio in der DDR](https://www.ndr.de/geschichte/ndr_retro/Empfang-westdeutscher-Funk-und-Fernsehsendungen-in-der-DDR,zonengrenze246.html){: .btn .btn--large}

**SmallCells**
[SmallCells](https://www.nokia.com/networks/mobile-networks/small-cells/){: .btn .btn--large}

The **Thought Emporium**: 
Ein Youtuber, der wifi Strahlung sichtbar macht:  
[Thought Emporium](https://www.youtube.com/@thethoughtemporium){: .btn .btn--large}
[The Wifi Camera](https://www.youtube.com/watch?v=g3LT_b6K0Mc&t=457s){: .btn .btn--large}
[Catching Satellite Images](https://www.youtube.com/watch?v=L3ftfGag7D8){: .btn .btn--large}

**GQRX**
[GQRX Software](https://gqrx.dk){: .btn .btn--large}

Was ist eigentlich **RF** (Radio Frequency):
[RF Explanation](https://pages.crfs.com/making-sense-of-radio-frequency){: .btn .btn--large}

**Bundesnetzagentur**, Funknetzvergabe
[Funknetzvergabe](https://www.bundesnetzagentur.de/DE/Fachthemen/Telekommunikation/Frequenzen/start.html){: .btn .btn--large}

**BOS Funk**
[BOS](https://www.bdbos.bund.de/DE/Digitalfunk_BOS/digitalfunk_bos_node.html){: .btn .btn--large}
