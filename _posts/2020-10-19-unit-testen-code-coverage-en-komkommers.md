---
layout: post
title: "Unit testen, code coverage en komkommers."
image: /assets/images/header.jpg
slug: unit-testen-code-coverage-en-komkommers
date: 2020-10-19T22:59:34
categories: ["dear non-it people"]
---
Dit is het derde artikel in de 'Dear non-IT people' reeks waarin ik IT begrippen probeer te versimpelen voor niet ICT ers:

[Waarom hebben ze het nu al weken over Trunk based development?]({% post_url 2020-09-16-waarom-hebben-ze-het-nu-al-weken-over-trunk-based-development %})

[Over pipelines en continuous van alles en nog wat.]({% post_url 2020-10-19-over-pipelines-en-continuous-van-alles-en-nog-wat %})

_IT is voor 'buitenstaanders' vaak een black box met zijn eigen vakjargon, heel veel afkortingen en vaak zelfs een eigen cultuur. Zaken klinken vaak heel complex en er duiken regelmatig nieuwe buzzwords op met een nieuwe belofte van snelheid, kostenbesparing en toekomstvastheid. Helaas zie je die zaken vanuit de business niet altijd terug._

_Toch zul je verrast zijn over hoe relatief simpel veel IT zaken kunnen zijn. Of beter: zouden moeten zijn. In een aantal korte blogpost zal ik proberen om een aantal van de laatste buzzwords en begrippen uit te leggen zodat ze begrijpbaar zijn en zodat jij vooral beter kan aanvoelen of er effort wordt gestoken in de juiste zaken op het juiste moment._

In [dit artikel]({% post_url 2020-09-16-waarom-hebben-ze-het-nu-al-weken-over-trunk-based-development %}) vertelde ik iets meer over automatisch testen, een erg belangrijk onderdeel van continuous integration. Ik leg begrippen als unit testing, integratie testen, end to end testing, acceptatie testen, TDD, BDD, code coverage uit

## Van achteraf valideren naar samen ontwerpen

Er was een tijd dat software development een zeer strak gedefinieerde fasering had waarbij testen de laatste stap was. Als er nog budget over was dan. In de praktijk werd dat vaak een ellenlange 'it's not a bug, it's a feature' discussie. Tegenwoordig hebben we meer de neiging om testen als integraal onderdeel van software ontwikkeling te zien en niet een afgebakend onderwerp. Ook het automatisch testen is tegenwoordig ook een geaccepteerde en standaard manier van werken.

> _Continuous delivery zonder testen is een beetje als je airbags uitzetten en met een blinddoek de A4 oprijden. Je ziet wel hoe het gaat en misschien kom je best een eind maar of het nou een goed plan is... Ik kan me voor beide dan ook geen goede argumenten bedenken._

Als voorbeeld voor dit artikel nemen we een shopping card van een webshop:

![](/assets/images/card.png)

In principe kijken we hier al naar minimaal 4 features (waarbij ik de footer even buiten beschouwing laat) die elk weer hun eigen functionaliteiten hebben. Alle functionaliteit samen resulteert erin dat een klant zijn of haar order kan opmaken en in een volgende stap iets kan bestellen:

![](/assets/images/card-sliced.png)

## Unit testen

![](/assets/images/unit-animated.gif)

Elke feature of component heeft zijn eigen specifieke set aan functies. Bijvoorbeeld het optellen als je op het plusje naast de schoen klikt of het invullen en controleren van een coupon code. Het testen van al deze functies noemen we unit testen. Een unit doet idealiter maar één ding. Laten we de berekeningen van de item prijs als voorbeeld nemen:

![](/assets/images/unit-tests.png)

De eerste regel geeft de totaalprijs aan en de code hiervoor zal dus iets zijn als: 

> Totaalprijs items = item prijs x aantal. In dit geval dus 1 x 299,43.

Een unit test is een stukje code wat elke keer als de testen worden gedraaid controleert of de code nog doet wat ie moet doen. In dit geval zou de test er als volgt uitzien:

*   Stel de item prijs is $ 50 en het aantal 3 dan is de verwachte totaalprijs van alle items $150,-
*   Stel de item prijs is $ 3,33 en het aantal 0 dan is de verwachte totaalprijs van alle items $ 0,-

In dit voorbeeld betaal je alleen verzendkosten als je onder de $300 aan items besteld. De unit testen hiervoor zijn:

*   Stel de item prijs is $ 50 en het aantal 3 dan zijn de verwachte verzendkosten $40,-

(de totaalprijs van de items is dus $ 150,-. Dit is lager dan $ 300 en dus moeten er verzendkosten worden betaald)

*   Stel de item prijs is $ 50 en het aantal 7 dan zijn de verwachte verzendkosten $0,-

Hetzelfde doen we ook voor de importkosten en het totaal van de card. Het is erg fijn om te weten dat wat we ook veranderen in de code dat de berekeningen in ieder geval juist zullen zijn.

### TDD

TDD staat voor Test Driven Development. Het is een manier van werken waarbij je eerst de test schrijft en pas daarna de code. Om de test in eerste instantie te kunnen schrijven moet een ontwikkelaar erg goed begrijpen wat de functionaliteit moet doen. 

De zin: stel de item prijs is $ 50 en het aantal 3 dan is de verwachte totaalprijs van alle items $150,- geeft een bredere context en een voorbeeld over wat er daadwerkelijk moet gebeuren. Het maken van de functionaliteit is een kwestie van deze test te laten slagen.

### Integratie testen 

![](/assets/images/DizzyHandsomeJohndory-size_restricted.gif)

Met integratie testen bekijken we of de samenwerking tussen de features/componenten ook goed werken. We moeten bijvoorbeeld zeker weten dat we het totaalbedrag goed doorgeven aan de creditcard provider. Maar ook de samenwerking tussen de verschillende onderdelen binnen een feature moeten we goed testen. Je kunt het vergelijken met een zin. Elk woord is goed gespeld, maar je zult toch moeten kijken of het geheel (de zin) ook goed is.

Als we op het plusje naast de schoen klikken dan verwachten we dat de prijzen ook worden aangepast. We testen in dit geval of we de juiste aantallen doorkrijgen en niet of het plusje werkt. De werking van het plusje hebben we immers al als unit test gedekt (elke klik op het plusje hoogt het aantal op met één).

![](/assets/images/integratie.png)

*   Stel de item prijs $ 70 is en het aantal 1, dan is de verwachte totaalprijs van alle items is $70,-
*   Als het aantal in het bovenste component veranderd naar 2 dan is de verwachte totaalprijs van alle items is $140,-

### End-to-end/acceptatie testen/BDD/ATDD

Deze testen hebben het meeste raakvlak met hoe de gebruiker de software ervaart. We bekijken hier het gedrag van de applicatie. Ook de beschrijvingen van deze testen worden vaak in menselijke taal geschreven.

![](/assets/images/unit-vs-integration02-1.gif)

### BDD & ATDD

BDD staat voor Behaviour Driven Development en ATDD voor Acceptance Test Driven Development en is dus hetzelfde als automatische acceptatie testen. End-to-end betekent dat we de applicatie van begin tot het einde testen. 

In al deze gevallen betekent dit dat we vooraf het gewenste gedrag al kunnen beschrijven en de validatie hiervan automatiseren als onderdeel van het ontwikkelproces.

Het mooie hiervan is dat personen van elke discipline hierover kunnen meedenken en stappen kunnen beschrijven. Het is heel verhelderend om vooraf al te bedenken welke stappen een user neemt (een user journey) en wat voor keuzes we vooraf al kunnen maken. Het beste is om te starten met een happy path (de ideale user journey zonder complicaties) en daarop varianten verzinnen:

![](/assets/images/e2e.png)

De test om de coupon functionaliteit te testen:

*   Stel dat ik 1 x Nike Zoom blauw 1 x Nike Zoom rood in de shopping cart heb gezet,
*   Wanneer ik op het hartje klik, 
*   Dan zie ik dat het hartje rood wordt,
*   Wanneer ik de code 'BLABLABLA\_FOUTE\_CODE' invul bij de coupon,
*   En ik op Apply klik, 
*   Dan zie ik de foutmelding 'Your coupon is not correct'

En in het geval van een juiste code:

*   ...
*   Wanneer ik de code 'XzOp014524BDZ' invul bij de coupon,
*   En ik op Apply klik, 
*   Dan zie ik de melding 'Congrats, you receive an 25% discount!'
*   En is mijn totaalprijs $575.15

### Komkommers

Misschien heb je je team wel eens over Cucumber horen praten en dacht je dat dat wel vreemd was aangezien het nog lang geen lunchtijd was. Cucumber is simpelweg een tool die al een tijd bestaat waarmee je BDD & ATDD testen kan doen. Hoewel Cucumber erg bekend is zijn er de afgelopen jaren enorm veel automatische test tools bijgekomen.

### Code coverage

De code coverage is het aantal relevante regels code wat wordt getest. Vaak wordt er een getal als 80% aangehouden maar er zijn ook zat teams die de coverage rond de 100% willen houden. Op het moment dat deze coverage te laag wordt kan je ervoor zorgen dat de pipeline stopt. Coverage zegt echter niks over de kwaliteit van de testen! Je kunt namelijk ook weer slechte automatische testen schrijven. Iets wat hierbij dan weer kan helpen (testen voor je testen) zijn mutation tests maar dat gaat te ver voor dit artikel.

![](/assets/images/coverage.png)

### Geen garantie

Hoewel er altijd in elke applicatie, en vaak op het meest onmogelijke momenten, bugs kunnen optreden hebben we door het automatiseren het moment van testen naar voren getrokken en testen we vele malen vaker. De automatische testen worden continu door de ontwikkelaars gedaan, bij elke commit op de test- en productie servers. 

In het kort levert automatisch testen de volgende voordelen:

*   Eerder nadenken over testen zorgt voor een betere architectuur en gebruikerservaring,
*   Als iets lastig te testen is dan is de te testen code vaak complex/te afhankelijk van andere code,
*   Doordat de code wordt getest is het makkelijk voor nieuwe developers om snel up and running te zijn,
*   Je kunt met zekerheid stukken code aanpassen zonder dat er andere delen stuk gaan,
*   De testen dienen als documentatie voor hoe de applicatie moet werken,
*   Snelle en hoge frequentie van feedback (Hoe later je een bug moet fixen hoe duurder het wordt),
*   Door testen meer te zien als design pattern wordt het iets wat door het hele team incl stakeholders kan worden gedaan,
*   …

Heb je nog vragen/aanvullingen? Hoor je vaak argumenten waarom jullie applicatie/programmeertaal/bedrijf niet geschikt is om te testen? Laat een reactie achter. Dan kijken we er samen eens naar.