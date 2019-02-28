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

Nachdem alle Daten ausgewertet waren, habe ich mir Gedanken über den Aufbau des Artikels gemacht. Diesen will ich erst am Schluss der aktuellen Saison publizieren, also Ende Mai. Dann muss ich die Auswertungen nochmals aktualisieren. Denn die Zahlen, die ich für die aktuelle Saison berechnet habe, sind momentan noch diejenigen bis zur Winterpause. Trotzdem weiss ich schon, wie die **Storyline** ungefähr aussehen soll:

---------------------------------

## TITEL: Thun macht am meisten aus seinen Möglichkeiten – Sion am wenigsten
## (Alternative:) So beeinflusst Geld den Schweizer Fussball

### LEAD: Wer viel Geld hat, ist tendenziell erfolgreicher. In der Super League trifft das aber nicht immer zu. Das zeigt eine Auswertung von 14 Saisons.

Im internationalen Fussball gibt das Geld längst den Ton an. Das beste Beispiel ist die englische Premier League, wo Clubs nur so mit Geld um sich schmeissen und auch für einen durchschnittlichen Spieler schon mal dutzende Millionen ausgeben. Steinreiche Besitzer und Investoren sowie der lukrative TV-Vertrag ermöglichen solche Eskapaden. Oft zahlt sich der Einsatz aus: An der Spitze der Premier League stehen diejenigen Teams, die sich die teuersten Spieler leisten können.

Geld regiert den Fussball, heisst es. Aber trifft das auch auf die Schweiz zu? In der Super League wird natürlich mit kleineren Brötchen gebacken. Trotzdem ist der gestiegene Einfluss des Geldes auch hierzulande spürbar. Die Clubs leisten sich immer teurere Spieler, wie Zahlen Seite transfermarkt.ch zeigen. Der Gesamtmarktwert aller Mannschaften respektive Spieler hat sich in den letzten 14 Jahren vervielfacht.

**GRAFIK: Entwicklung des Gesamtmarktwerts der Liga (alle Saisons)**
![Entwicklung des Gesamtmarktwerts](https://github.com/yannickw3/Abschlussarbeit/blob/master/graphics/gesamtmarktwert.png "Entwicklung des Gesamtmarktwerts")

Seit der Saision 2005/2006, als die transfermarkt.ch zum ersten Mal alle Marktwerte der Super-League-Teams erhob, hat sich der Gesamtmarktwert der Liga verdoppelt: von 116 Millionen Franken auf fast 244 Millionen Franken. 

> BOX: So erhebt transfermarkt.ch seine Zahlen

Auch in der Schweiz fliesst also immer mehr Geld in den Fussball. Aber was hat das für Auswirkungen? Ist ein Club auch in der Super League erfolgreicher, wenn er mehr Geld investieren und sich ein teures Team leisten kann? Um diese Frage zu beantworten, haben wir die Marktwerte und erzielten Punkte aller Mannschaften seit 2005 ins Verhältnis gesetzt.

**GRAFIK: Je mehr Geld, desto mehr Punkte (alle Saisons)**

![Je mehr Geld, desto mehr Punkte](https://github.com/yannickw3/Abschlussarbeit/blob/master/graphics/regression_alle%20saisons.png "Je mehr Geld, desto mehr Punkte")

Das Resultat: Es gibt einen klaren Zusammenhang zwischen Marktwerten und Punkten. Das heisst, je teurer die Mannschaften sind, desto mehr Punkte holen sie. Die Grafik zeigt aber auch, dass es immer wieder Ausreisser gibt, also Ausnahmen von der Regel. Das sind Clubs, die überraschen - in der aktuellen Saison zum Beispiel der FC Thun. Seine Mannschaft hatte mit 18,25 Millionen Franken den drittkleinsten Marktwert der Liga. Trotzdem schaffte es Thun auf den dritten Rang (Stand Winterpause, auch bei nachfolgenden Aussagen).

Nur Lugano und Neuchatel Xamax verfügten über ein noch günstigeres Kader. Die Neuenburger konnten sich gerade einmal Spieler leisten, die zusammen einen Marktwert von 9,5 Millionen hatten - fast sieben Mal weniger als Ligakrösus YB. Gut 62 Millionen Franken war die Mannschaft der Berner Young Boys in der abgelaufenen Saison wert. Der Gewinn der Meisterschaft kommt deshalb wenig überraschend. Auch der Abstieg von Xamax folgt der Logik des Geldes.

**GRAFIK: Vergleich zwischen den Ranglisten nach Marktwert und nach Punkten (aktuelle Saison) >Hier wäre ein Flussdiagramm schön, dass die Rangveränderung zeigt. Dazu bräuchte ich aber Hilfe der Infografik**
![Marktwerte](https://github.com/yannickw3/Abschlussarbeit/blob/master/graphics/marktwerte.png "Marktwerte")
![Punkte](https://github.com/yannickw3/Abschlussarbeit/blob/master/graphics/punkte.png "Punkte")

Neben Thun schnitten auch Zürich, St.Gallen und Lugano besser ab, als es der Marktwert vor Beginn der Saison erahnen liess. Eine Saison allein ist aber noch nicht so aussagekräftig. Wir haben deshalb berechnet, wie oft die Clubs in den letzten 14 Jahren ihre Erwartungen übertrafen oder im Gegenteil nicht erfüllten.

Am häufigsten überraschte auch über alle ausgewerteten Saisons gesehen der FC Thun. Kumuliert hat er 30 Plätze besser abgeschnitten als es seine finanziellen Möglichkeiten erahnen liessen. Mit grossen Abstand folgen der FC Luzern mit 13 und Lugano mit 5 gutgemachten Plätzen. Am meisten unter seinen Erwartungen blieb der FC Sion. Auch die Grasshoppers hätten sich anhand ihres Marktwerts in vielen Saisons besser platzieren müssen, hatten also ein teures Team, das aber nicht erfolgreich war.

**GRAFIK: Die Over- und Underperformer der Liga (alle Saisons)**
![Over- und Underperformer](https://github.com/yannickw3/Abschlussarbeit/blob/master/graphics/over_underperformer.png "Over- und Underperformer")

(Der Stolperstein: Während YB, Basel und die Grasshoppers alle ausgewerteten Saisons in der Super League spielten, mischte Xamax nur sechs Jahre in der obersten Liga mit. Bei Yverdon-Sport, das längst in den Niederungen des Schweizer Fussballs versunken ist, war es sogar nur eine. Hier könnte man eine Einschränkung machen: z.B. nur Mannschaften berücksichtigt, die mindestens fünf Saisons dabei waren.)

Man könnte diese Berechnungen auch anders visualisieren. Zum Beispiel, indem man anzeigt, wie viele Male die Clubs die Erwartungen übertrafen, einfach erfüllten oder auch nicht erfüllten. So sieht man den Anteil der Saisons, in denen sie enttäuschten oder überraschten. Dass die Basler so oft "nur" die Erwartungen erfüllten, hat damit zu tun, dass sie jahrelang das teuerste Kader hatten und damit die Meisterschaft gewannen. Sie waren also trotzdem erfolgreich, ergo: Ich muss bei jedem Team noch schauen, was sie im untersuchten Zeitraum erreicht haben (Titel, Teilnahme europäischer Wettbewerb).

**GRAFIK: Die Over- und Underperformer der Liga (alle Saisons)**
![Over- und Underperformer](https://github.com/yannickw3/Abschlussarbeit/blob/master/graphics/over_underperformer2.png "Over- und Underperformer")

Das Ganze lässt sich auch rechnerisch belegen. Wir haben ausgewertet, wieviel Geld die Clubs (indirekt) pro Punkt investiert haben. 

> BOX: Methodik: So bin ich bei der Berechnung vorgegangen

In der aktuellen Saison hat der FC Basel am meisten ausgegeben. Im Gegensatz zu den Grasshoppers, die in diesem Ranking den unrühmlichen zweiten Platz belegen, sind die Basler damit aber immerhin auf dem zweiten Platz gelandet. GC hingegen musste als Zweitletzter in die Barrage. St.Gallen und Thun investierten am wenigsten, wobei Letztere trotz kleinem Budget erfolgreich waren.

**GRAFIK: Geld pro Punkt (aktuelle Saison)**

![Geld pro Punkt (aktuelle Saison)](https://github.com/yannickw3/Abschlussarbeit/blob/master/graphics/geld_saison1819.png "Geld pro Punkt (aktuelle Saison)")

Über alle Saisons gesehen hat Xamax im Schnitt noch weniger ausgegeben als Thun. Allerdings gibt es zwischen diesen Teams grosse Unterschiede: Während die Berner Oberländer überraschten und sich mehrmals für europäische Wettbewerbe qualifizieren konnten, klassierte sich Xamax durchgehend in der hinteren Hälfte der Tabelle, stieg sogar zweimal ab. 

**GRAFIK: Geld pro Punkt (alle Saisons)**

![Geld pro Punkt (alle Saisons)](https://github.com/yannickw3/Abschlussarbeit/blob/master/graphics/geld_alle_saisons.png "Geld pro Punkt (alle Saisons)")

Der FC Sion investierte am meisten, mit mässigem Erfolg in der Liga. Immerhin holten die Walliser seit 2005 viermal den Cup, der in dieser Statistik nicht enthalten ist. Der FC Basel liess sich seine Punkte ebenfalls viel kosten, das zahlte sich aber auch aus: Seit der Saison 2005 wurde er 10 Mal Meister.

---------------------------------

Bis zur Publikation könnte ich noch einen Schritt weitergehen und der Frage auf den Grund gehen, warum es bei einigen Clubs auch mit wenig Budget klappt und bei anderen nicht. Vielleicht könnte ich beim FC Thun vorbeigehen und mit den Verantwortlichen reden, um herauszufinden, was das Erfolgsrezept des Vereins ist. Meine Briefing-Person Florian Raz hat seine Hilfe angeboten, wenn ich inhaltlich nicht weiterkommen sollte.
