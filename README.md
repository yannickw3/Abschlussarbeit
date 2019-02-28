# Abschlussarbeit CAS Datenjournalismus 18/19

Als Abschlussarbeit habe ich das Projekt umgesetzt, in welches ich am meisten Zeit investiert habe. Die Idee hatte ich schon zu Beginn des Kurses: Ich wollte der Frage nachgehen, in welchem Masse und inwiefern der Schweizer Fussball vom Geld bestimmt wird. Antworten sollten die Marktwerte der Mannschaften liefern, die von der Webseite transfermarkt.ch (https://www.transfermarkt.ch/super-league/startseite/wettbewerb/C1/plus/?saison_id=2018) erhoben werden.

Im Laufe der ersten Recherchen wurde mir klar, dass schon andere Arbeiten auf den Zusammenhang zwischen Geld und Erfolg hingewiesen haben, wenn auch in ausländischen Ligen. Das bestätigte mir meine **Briefing Person** Florian Raz, Sportredaktor beim Tages-Anzeiger. Er fand das Thema aber spannend und bestärkte mich in meinem Vorhaben, einen Schritt weiterzugehen: Nicht nur aufzuzeigen, dass Geld den Fussball beeinflusst, sondern auch, welche Mannschaften am meisten aus ihrem Geld beziehungsweise Möglichkeiten machen.

Da ich selbst Fussballfan bin, beobachte ich die Schweizer Super League schon länger. Dabei ist mir besonders aufgefallen, dass sich der FC Thun regelmässig über Wert verkauft – zumindest gefühlt. Trotz kleinem Budget schaffen es die Berner Oberländer fast jedes Jahr, nichts mit dem Abstieg zu tun zu haben. Ist das nur mein Eindruck? Oder lässt er sich durch Zahlen bestätigen? Dieser Frage bin ich in meiner Abschlussarbeit nachgegangen.

**Meine Ausgangsthesen lauteten:**
- These 1: Je höher der Marktwert einer Mannschaft in der Super League ist, desto erfolgreicher spielt sie.
- These 2: Der FC Thun holt am meisten aus seinen Möglichkeiten heraus.

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
## Thun macht am meisten aus seinen Möglichkeiten – Sion am wenigsten
## (Alternative:) So beeinflusst Geld den Schweizer Fussball

### Lead:
### Wer viel Geld hat, ist tendenziell erfolgreicher. In der Super League trifft das aber nicht immer zu. Das zeigt eine Auswertung von 14 Saisons.

Im internationalen Fussball gibt das Geld längst den Ton an. Das beste Beispiel ist die englische Premier League, wo Clubs nur so mit Geld um sich schmeissen und auch für einen durchschnittlichen Spieler schon mal dutzende Millionen ausgeben. Steinreiche Besitzer und Investoren sowie der lukrative TV-Vertrag ermöglichen solche Eskapaden. Oft zahlt sich der Einsatz aus: An der Spitze der Premier League stehen diejenigen Teams, die sich die teuersten Spieler leisten können.

Geld regiert den Fussball, heisst es. Aber trifft das auch auf die Schweiz zu? In der Super League wird natürlich mit kleinen Brötchen gebacken. Trotzdem ist der gestiegene Einfluss des Geldes auch hierzulande spürbar. Die Clubs leisten sich immer teurere Spieler, wie Zahlen Seite transfermarkt.ch zeigen. Der Gesamtmarktwert aller Mannschaften respektive Spieler hat sich in den letzten 14 Jahren vervielfacht.

**GRAFIK: Entwicklung des Gesamtmarktwerts der Liga (alle Saisons)**
![Entwicklung des Gesamtmarktwerts](gesamtmarktwerte.jpg)
![Entwicklung des Gesamtmarktwerts](Schreibtisch/Abschlussarbeit/gesamtmarktwerte.jpg?raw=true "Entwicklung des Gesamtmarktwerts")

Seit der Saision 2005/2006, als die transfermarkt.ch zum ersten Mal alle Marktwerte der Super-League-Teams erhob, hat sich der Gesamtmarktwert der Liga verdoppelt: von 116 Millionen Franken auf fast 244 Millionen Franken. 

> BOX: So erhebt transfermarkt.ch seine Zahlen

Auch in der Schweiz fliesst also immer mehr Geld in den Fussball. Aber was hat das für Auswirkungen? Ist ein Club auch in der Super League erfolgreicher, wenn er mehr Geld investieren und sich ein teures Team leisten kann? Um diese Frage zu beantworten, haben wir die Marktwerte und erzielten Punkte aller Mannschaften seit 2005 ins Verhältnis gesetzt.

**GRAFIK: Je mehr Geld, desto mehr Punkte (alle Saisons)**
![Bildtext](Linkzumbild.jpg "Bildtitel")

Das Resultat: Es gibt einen klaren Zusammenhang zwischen Marktwerten und Punkten. Das heisst, je teurer die Mannschaften sind, desto mehr Punkte holen sie. Die Grafik zeigt aber auch, dass es immer wieder Ausreisser gibt, also Ausnahmen von der Regel. Das sind Clubs, die überraschen - in der aktuellen Saison zum Beispiel der FC Thun. Seine Mannschaft hatte mit 18,25 Millionen Franken den drittkleinsten Marktwert der Liga. Trotzdem schaffte es Thun auf den dritten Rang (Stand Winterpause, auch bei nachfolgenden Aussagen).

Nur Lugano und Neuchatel Xamax verfügten über ein noch günstigeres Kader. Die Neuenburger konnten sich gerade einmal Spieler leisten, die zusammen einen Marktwert von 9,5 Millionen hatten - fast sieben Mal weniger als Ligakrösus YB. Gut 62 Millionen Franken war die Mannschaft der Berner Young Boys in der abgelaufenen Saison wert. Der Gewinn der Meisterschaft kommt deshalb wenig überraschend. Auch der Abstieg von Xamax folgt der Logik des Geldes.

**GRAFIK: Vergleich zwischen den Ranglisten nach Marktwert und nach Punkten (aktuelle Saison) >Hier wäre ein Flussdiagramm schön, dass die Rangveränderung zeigt. Dazu bräuchte ich aber Hilfe der Infografik**
![Bildtext](Linkzumbild.jpg "Bildtitel")

Neben Thun schnitten auch Zürich, St.Gallen und Lugano besser ab, als es der Marktwert vor Beginn der Saison erahnen liess. Eine Saison allein ist aber noch nicht so aussagekräftig. Wir haben deshalb berechnet, wie oft die Clubs in den letzten 14 Jahren ihre Erwartungen übertrafen, erfüllten oder auch nicht erfüllten.

Der Stolperstein: Während YB, Basel und die Grasshoppers alle ausgewerteten Saisons in der Super League spielten, mischte Xamax nur sechs Jahre in der obersten Liga mit, ein Team wie Yverdon-Sport, das längst in den Niederungen des Schweizer Fussballs versunken ist, sogar nur eine. Wir haben deshalb nur Mannschaften berücksichtigt, die mindestens ... Saisons dabei waren.

**GRAFIK: Die Over- und Underperformer der Liga (alle Saisons)**
![Bildtext](Linkzumbild.jpg "Bildtitel")

Am häufigsten übertraf der Thun die Erwartungen, gefolgt von Luzern und Zürich. Die Grasshoppers und Sion blieben stattdessen am häufigsten unter den Erwartungen, hatten also ein teures Team, das aber nicht erfolgreich war. Dass die Basler so oft die Erwartungen erfüllten, hat damit zu tun, dass sie jahrelang das teuerste Kader hatten und damit die Meisterschaft gewannen.

Lässt sich das auch rechnerisch belegen? Welche Teams sind über sich hinausgewachsen? Wer hat am meisten aus seinem Möglichkeiten gemacht?
Um das zu beantworten, haben wir berechnet, wie viel Geld die Mannschaften pro Punkt gebraucht haben. 

**GRAFIK: Geld pro Punkt (aktuelle Saison)**
![Bildtext](Linkzumbild.jpg "Bildtitel")


blabla

> BOX: blabla

**GRAFIK: Geld pro Punkt (alle Saisons)**
![Bildtext](Linkzumbild.jpg "Bildtitel")

Das Resultat: Xamax und Thun haben in den letzten 13 Jahren im Schnitt am wenigsten Geld pro Punkt investiert, Basel und Sion am meisten. Allerdings gibt es zwischen diesen Teams grosse Unterschiede: Während Thun überraschte und sich mehrmals für europäische Wettbewerbe qualifizieren konnte, klassierte sich Xamax durchgehend in der hinteren Hälfte der Tabelle, stieg sogar zweimal ab. Der FC Basel investierte zwar viel, das zahlte sich aber auch aus: seit der Saison 2005 wurde er ...mal Meister. Sion hingegen hat stets eine teure Mannschaft, reisst in der Liga aber nichts.


---------------------------------


Skizze der weiteren Schritte bis zur Publikation
Briefing Person bietet seine Hilfe an, wenn ich inhaltlich nicht weiterkommen sollte.
>> vielleicht beim FC Thun vorbeigehen, anfragen
