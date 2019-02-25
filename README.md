# Abschlussarbeit CAS Datenjournalismus 18/19

Als Abschlussarbeit habe ich das Projekt umgesetzt, in welches ich am meisten Zeit investiert habe. Die Idee hatte ich schon zu Beginn des Kurses: Ich wollte der Frage nachgehen, in welchem Masse und inwiefern der Schweizer Fussball vom Geld bestimmt wird. Antworten sollten die Marktwerte der Mannschaften liefern, die von der Webseite transfermarkt.ch (https://www.transfermarkt.ch/super-league/startseite/wettbewerb/C1/plus/?saison_id=2018) erhoben werden.

Im Laufe der ersten Recherchen wurde mir klar, dass schon andere Arbeiten auf den Zusammenhang zwischen Geld und Erfolg hingewiesen haben, wenn auch in ausländischen Ligen. Das bestätigte mir meine **Briefing Person** Florian Raz, Sportredaktor beim Tages-Anzeiger. Er fand das Thema aber spannend und bestärkte mich in meinem Vorhaben, einen Schritt weiterzugehen: Nicht nur aufzuzeigen, dass Geld den Fussball beeinflusst, sondern auch, welche Mannschaften am meisten aus ihrem Geld beziehungsweise Möglichkeiten machen.

Da ich selbst Fussballfan bin, beobachte ich die Schweizer Super League schon länger. Dabei ist mir besonders aufgefallen, dass sich der FC Thun regelmässig über Wert verkauft - zumindest gefühlt. Trotz kleinem Budget schaffen es die Berner Oberländer fast jedes Jahr, nichts mit dem Abstieg zu tun zu haben. Ist das nur mein Eindruck? Oder lässt er sich durch Zahlen bestätigen? Dieser Frage bin ich in meiner Abschlussarbeit nachgegangen.

**Meine Ausgangsthesen lauteten:**
These 1: Je höher der Marktwert einer Mannschaft in der Super League ist, desto erfolgreicher spielt sie.
These 2: Der FC Thun holt am meisten aus seinen Möglichkeiten heraus.

Zu Beginn des Projektes unterschätzte ich den **Aufwand** zugegebenermassen. Ich dachte, dass die Daten schnell erhältlich sind und relativ einfach ausgewertet werden können. Aber schon bei der Datenbeschaffung stiess ich auf erstes ein grosses Hindernis, weil die Seite transfermarkt.ch Anfragen mit BeautifulSoup blockiert. Barnaby musste mir hier mit einem Code helfen, damit ich die Blockade umgehen konnte. Danach stellte sich vor allem das Scraping mit all seinen Tücken als **Knackpunkt des Projektes** heraus. Es dauerte schon mal Stunden, bis ich gewisse Bugs beheben konnte. Umso grösser war dann die Freude, wenn auf einmal etwas klappte oder ich beim Codieren einen “Lauf” hatte. 

Eine gewisse Einschränkung ergab sich aus der Verfügbarkeit der Daten: transfermarkt.ch erhebt die Marktwerte aller Schweizer Teams erst seit der Saison 2005/2006. Allerdings gibt es die Super League in ihrer heutigen Form ohnehin erst seit 2003.

Nachdem die Idee stand, bin ich folgendermassen vorgegangen:

**Arbeitsprotokoll (jupyter notebook):**
1. Benötigte Libraries importieren
2. Beispielseite scrapen > aktuelle Saison (hier brauchte ich Barnabys Code)
3. Mithilfe des Entwicklertools auf Google Chrome und BeautifulSoup die Gesamtmarktwerte der Teams aus 1. Tabelle auf der Seite herauslesen > Prototyping Marktwerte
4. Dann die Punkte der Teams aus der 2. Tabelle auf der Seite herauslesen > Prototyping Punkte
5. Die beiden Auswertungen zusammenbringen
6. Scrapen der Gesamtmarktwerte aller Saisons seit 2005
7. Scrapen der Punkte aller Saisons seit 2005
8. Die beiden Tabellen mergen
9. Visualisierungen

Nachdem alle Daten ausgewertet waren, habe ich mir Gedanken über den Aufbau des Artikels gemacht. Diesen will ich erst am Schluss der aktuellen Saison publizieren, also Ende Mai. Dann muss ich die Auswertungen nochmals aktualisieren. Denn die Zahlen, die ich für die aktuelle Saison berechnet habe, sind momentan noch diejenigen bis zur Winterpause. Trotzdem weiss ich schon, wie die Storyline ungefähr aussehen soll:

---------------------------------

## TITEL:
## Thun macht am meisten aus seinen Möglichkeiten - Sion am wenigsten
## (Alternative:) So beeinflusst Geld den Schweizer Fussball

### Lead:
### Wer viel Geld hat, ist tendenziell erfolgreicher. In der Super League trifft das aber nicht immer zu. Das zeigt eine Auswertung von 14 Saisons.

Geld regiert den Fussball, heisst es. In der englischen Premier League schmeissen die Clubs nur so mit Geld um sich, geben für einen durchschnittlichen Spieler schon mal dutzende Millionen aus. Steinreiche Besitzer und Investoren sowie der lukrative TV-Vertrag ermöglichen solche Eskapaden.

In der Schweiz wird mit kleinen Brötchen gebacken. Aber auch hier hat sich der Einsatz in den letzten 13 Jahren vervielfacht. Die Clubs leisten sich immer teurere Spieler… 
>hier Budgets???? Sagen, dass nie ganz klar, deshalb Marktwerte..

Seit der Saision 2005/2006, als die Seite transfermarkt.ch zum ersten Mal alle Marktwerte der Super-League-Teams erhoben hat, ist der Gesamtmarktwert der Liga um … Franken und damit … Prozent gestiegen.

**GRAFIK: Entwicklung des Gesamtmarktwerts der Liga (alle Saisons)**
![Entwicklung des Gesamtmarktwerts](gesamtmarktwerte.jpg)

Waren alle Spieler der Super-League 2005 zusammen noch 116 Millionen Franken wert, kosten sie heute schon fast 244 Millionen Franken - mehr als doppelt so viel. 

BOX? 
Transfermarkt.ch schätzt seine Angaben, indem… > Vorgehen erläutern
Webseite transfermarkt.ch erhoben werden. Sie gehört zum deutschen Axel-Springer-Verlag und gehört zu den grössten und meistbesuchten Sportwebseiten im deutschsprachigen Raum.

(GRAFIK ?: Entwicklung Geld pro Punkte > hat sich dementsprechend auch über die Jahre erhöht)

Auch in der Schweiz fliesst also immer mehr Geld in den Fussball. Aber was hat das für Auswirkungen?
Ich will die These beweisen, dass erfolgreicher ist, wer mehr Geld investiert und sich ein teures Team leistet.

**GRAFIK: Je mehr Geld, desto mehr Punkte (alle Saisons)**
![Bildtext](Linkzumbild.jpg "Bildtitel")

Wie die Grafik schon andeutet, gibt es aber immer wieder Ausreisser…
Zum Glück gibt es aber immer Teams, die überraschen - in der aktuellen Saison zum Beispiel (wieder einmal) der FC Thun… Seine Mannschaft hatte in der aktuellen Saison den drittkleinsten Marktwert. Trotzdem schaffte sie es auf den … Rang.

In der gerade zu Ende gegangenen Spielzeit verfügten die Young Boys über die teuersten Spieler. Gut 62 Millionen Franken waren sie zusammen wert, der FC Basel folgte mit 53 Millionen. Die restlichen Teams kamen nicht einmal auf die Hälfte dieses Werts. Neuchatel Xamax konnte sich gerade einmal Spieler leisten, die zusammen einen Marktwert von 9,5 Millionen haben - fast sieben Mal weniger als YB.

**GRAFIK: Vergleich zwischen den Ranglisten nach Marktwert und nach Punkten (aktuelle Saison) >Hier wäre ein Flussdiagramm schön, dass die Rangveränderung zeigt. Dafür bräuchte ich aber Hilfe der Infografik**
![Bildtext](Linkzumbild.jpg "Bildtitel")

Dass YB viele Punkte geholt hat/Meister geworden ist, konnte man vor der Saison also erwarten. Aber welche Teams sind über sich hinausgewachsen? Wer hat am meisten aus seinem Möglichkeiten gemacht?

Um das zu beantworten, haben wir berechnet, wie viel Geld die Mannschaften pro Punkt gebraucht haben. 

**GRAFIK: Geld pro Punkt (aktuelle Saison)**
![Bildtext](Linkzumbild.jpg "Bildtitel")

Überperformer, Unterperformer...

**GRAFIK: Geld pro Punkt (alle Saisons)**
![Bildtext](Linkzumbild.jpg "Bildtitel")

Das Resultat: Xamax und Thun haben in den letzten 13 Jahren im Schnitt am wenigsten Geld pro Punkt investiert, Basel und Sion am meisten. Allerdings gibt es zwischen diesen Teams grosse Unterschiede: Während Thun überraschte und sich mehrmals für europäische Wettbewerbe qualifizieren konnte, klassierte sich Xamax durchgehend in der hinteren Hälfte der Tabelle, stieg sogar zweimal ab. Der FC Basel investierte zwar viel, das zahlte sich aber auch aus: seit der Saison 2005 wurde er ...mal Meister. Sion hingegen hat stets eine teure Mannschaft, reisst in der Liga aber nichts.




………


Skizze der weiteren Schritte bis zur Publikation
Briefing Person bietet seine Hilfe an, wenn ich inhaltlich nicht weiterkommen sollte.
>> vielleicht beim FC Thun vorbeigehen, anfragen
