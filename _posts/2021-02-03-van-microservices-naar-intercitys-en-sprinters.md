---
layout: post
title: "Van microservices naar intercity's en sprinters"
image: /assets/images/pexels-sergio-souza-train-lot-featured.jpg
slug: van-microservices-naar-intercitys-en-sprinters
date: 2021-02-03T18:02:46
categories: ["dear non-it people"]
---
Dit is het vijfde artikel in de ‘Dear non-IT people’ reeks waarin ik IT begrippen probeer te versimpelen voor niet ICT ers:

*   [Waarom hebben ze het nu al weken over Trunk based development?]({% post_url 2020-09-16-waarom-hebben-ze-het-nu-al-weken-over-trunk-based-development %})
*   [Over pipelines en continuous van alles en nog wat.]({% post_url 2020-10-19-over-pipelines-en-continuous-van-alles-en-nog-wat %})
*   [Unit testen, code coverage en komkommers.]({% post_url 2020-10-19-unit-testen-code-coverage-en-komkommers %})
*   [Wat is low-code en is dat echt zo makkelijk als iedereen zegt?]({% post_url 2020-11-30-what-is-low-code %})

_IT is voor ‘buitenstaanders’ vaak een black box met zijn eigen vakjargon, heel veel afkortingen en vaak zelfs een eigen cultuur. Zaken klinken vaak heel complex en er duiken regelmatig nieuwe buzzwords op met een nieuwe belofte van snelheid, kostenbesparing en toekomstvastheid. Helaas zie je die zaken vanuit de business niet altijd terug._

_Toch zul je verrast zijn over hoe relatief simpel veel IT zaken kunnen zijn. Of beter: zouden moeten zijn. In een aantal korte blogpost zal ik proberen om een aantal van de laatste buzzwords en begrippen uit te leggen zodat ze begrijpbaar zijn en zodat jij vooral beter kan aanvoelen of er effort wordt gestoken in de juiste zaken op het juiste moment._

## Monolieten, modulieten en microservices

We hebben de laatste jaren heel wat effort gestoken in het beter en sneller maken van software producten. We zeggen hierover dat we een hele lage time-to-market nodig hebben om zo snel feedback van eindgebruikers te verkrijgen. Enerzijds door de processen aan te passen (agile) maar het grootste effect komt toch door de technische ontwikkelingen zoals server virtualisatie, containers, continuous integration/delivery, nieuwe frameworks ed. 

Nu is het ook beter mogelijk/is er betere tooling om je applicatie op te knippen in hele kleine stukjes, ook wel microservices genoemd, zodat je in theorie met meerdere teams heel snel aanpassingen kan opleveren of je heel veel gebruikers hebt die bepaalde functionaliteit willen gebruiken. Je weet wel, net als Netflix! In sommige specifieke gevallen levert dat heel veel op maar men vergeet wel eens dat het ook behoorlijk wat kan kosten. 

![](/assets/images/Screenshot-2021-02-03-at-16.47.42.png)

Bij microservices wordt het systeem (vaak de monoliet) in van elkaar onafhankelijke services opgeknipt die enkel één doel hebben zoals zoeken, calculatie, rating, shopping cart, recommendation engine ed.   
Mocht je nou echt veel meer willen weten over microservices dan raad ik je de blog serie van Uwe Friedrichsen waar je het eerste deel hier kan vinden. [https://www.ufried.com/blog/microservices\_fallacy\_1/](https://www.ufried.com/blog/microservices_fallacy_1/)

## **Monoliet**

![](/assets/images/long-train-1.jpg)

Laten we uitgaan van een bestaande applicatie. Deze heeft al een aantal logische modules maar wordt meestal in zijn geheel opgeleverd. We kunnen deze vergelijken met een lange trein die ook een deel van het goederentransport en post meenemen.

De planning van de trein is niet erg flexibel maar wel betrouwbaar. Eén keer heen en terug per week. Ben je te laat of zijn er goederen niet op tijd geleverd moet je een week wachten. Als er een defect is of er ligt een boom op de rails dan heeft dit veel impact en de kans is groot dat de planning issues een paar weken doorwerken.

Wat infrastructuur betreft hebben we één spoor nodig en een aantal stations.

## **Modulair**

![](/assets/images/long-tran-2.jpg)

![](/assets/images/faster-personal-train.jpg)

Er komt een moment dat het personenvervoer een andere frequentie behoeft dan het goederenvervoer. Mensen willen dagelijks op en neer kunnen terwijl het voor de post en de goederen één keer per week prima is. 

We blijven hetzelfde spoor gebruiken met dezelfde stations maar zorgen dat we voor personenvervoer in speciaal hiervoor gemaakte treinen met een eigen planning personen van A naar B brengen. De planning wordt al iets lastiger maar er is ook wat meer flexibiliteit voor specifiek de personentreinen. We moeten ook gaan investeren in de infrastructuur want we gaan personen naar stations in de steden brengen en de post en goederen juist buiten het centrum. Op de gedeelde stukken moeten we nu wel twee sporen aanleggen.

Een volgende stap is om te onderkennen dat ook post een andere frequentie nodig heeft dat zowel de personen als de goederen en kunnen we deze ook opsplitsen.

Ook wordt de planning nu weer een stapje complexer en moet de infrastructuur ook weer worden aangepast.

## Microservices

![](/assets/images/Screenshot-2021-02-01-at-16.55.02.png)

The _ParkShuttle_ in Rotterdam

In theorie kunnen we nog veel verder differentiëren. In de realiteit hebben we al sprinters, intercity's en intercity direct treinen. Allemaal wel met vaste tijden en lijnen. 

Een vergelijking met microservices zou een soort train-on-demand zijn. Een soort Uber pool maar dan op het spoor. 

Om zo snel en flexibel mogelijk personen, goederen en post te kunnen leveren maken we een groot aantal verschillende treintjes met allemaal hun eigen specifieke doelen: 

Rotterdam - Gouda met alleen de 1e klas passagiers, 

Maastricht - Nijmegen voor de binnenlandse post, 

Amsterdam - Parijs voor gevaarlijke goederen, 

Amsterdam - Parijs voor 2e klas passagiers etc. 

Op het moment dat we een wagon aanpassen zodat er meer mensen in kunnen of dat je in een andere nu ook gevaarlijke goederen kan vervoeren dan kan die wagon gelijk 'live'. Zijn er passagiers of goederen dan kunnen deze direct naar de eindbestemming. Elk treintje doet één ding. We hoeven niet meer te wachten tot een bepaalde tijd of tot de wagon vol is maar we gaan wanneer het kan. De perfecte gebruikersbeleving.

![](/assets/images/pexels-sergio-souza-train-lot.jpg)

Sergio Souza - Pexels

Dit brengt wel weer extra complexiteit met zich mee en het is zeker niet gratis. Hoewel we nu wanneer we maar willen kunnen leveren (naar productie kunnen) hebben we wel een zeer goed monitoringssysteem nodig wat ervoor zorgt dat er geen ongelukken gebeuren. Mede omdat de druk op bepaalde momenten enorm kan toenemen zonder dat dat altijd te voorspellen is. Waar we voorheen een beperkt aantal treinen hadden hebben we nu een geavanceerd rangeerterrein nodig. We hebben waarschijnlijk ook meer rails nodig.

## Complexiteit

Met betrekking tot IT architectuur het het vaak zo dat als er aan de ene kant iets simpeler wordt dat de complexiteit ergens anders toeneemt. En complexiteit kost vaak gewoon effort en geld en de keuze hiervoor moet goed afgewogen worden. Zo ook bij microservices. Waar een monoliet soms als log wordt bestempeld heeft deze ook minder afhankelijkheden waar een microservices architectuur dat wel sterk heeft. 

Wordt het aan de ene kant veel makkelijker om snel kleinere aanpassingen op te leveren, wordt aan de andere kant een kunst om ervoor te zorgen dat alle andere services ook goed blijven werken en wordt in bepaalde gevallen het end-to-end testen zeer lastig. 

De complexiteit verschuift van Dev naar Ops in DevOps. Gelukkig zijn er oplossingen als service contracting versioning en nieuwe monitoring systemen ed maar feit blijft dat dit wel goed moet worden ingericht en bijgehouden.

![](/assets/images/pexels-aleks-magnusson-rails-bit-complex.jpg)

Aleks-magnusson - Pexels

In de praktijk ben je in de meeste gevallen goed uit als je ervoor kiest om de zaken die je snel en vaak wil opleveren of die extreem veel gebruikt gaan worden als services te bouwen. De rest van je applicatie kan dan vaak prima als monoliet of als moduliet door het leven. De neiging binnen de IT is echter vaak om 'alles helemaal anders te gaan doen met een nieuwe revolutionaire techniek'. Dat resulteert in een aantal bedrijven die voor 100% naar microservices zijn gegaan om over te gaan naar microservices maar daar uiteindelijk toch van terugkomen en langzaam weer de balans opzoeken zoals je [hier](https://www.infoq.com/presentations/microservices-monolith-antipatterns/) kan horen. Voor deze bedrijven een hele kostbare maar voor ons goede les.

## Wie ben jij en wat heb je nodig?

De vraag die je je moet stellen is of jij daadwerkelijk zo snel of extreem opschalen moet. Heb jij echt zoveel teams nodig om aan hetzelfde product te werken? Gaan de banken en verzekeraars in Nederland ons echt verbluffen met wekelijks nieuwe features? Of gaan we ons hier ook net als bij de pakketbezorging afvragen of het nou echt heel erg nodig is om alles direct de volgende dag thuis te hebben