---
layout: post
title: "Wat is low-code en is dat iets wat echt zo makkelijk is als iedereen zegt?"
image: /assets/images/technology-2816614_1280.jpg
slug: "614"
date: 2020-11-30T17:40:27
categories: ["dear non-it people"]
---
Dit is het vierde artikel in de ‘Dear non-IT people’ reeks waarin ik IT begrippen probeer te versimpelen voor niet ICT ers:

1.  [Waarom hebben ze het nu al weken over Trunk based development?]({% post_url 2020-09-16-waarom-hebben-ze-het-nu-al-weken-over-trunk-based-development %})
2.  [Over pipelines en continuous van alles en nog wat.]({% post_url 2020-10-19-over-pipelines-en-continuous-van-alles-en-nog-wat %})
3.  [Unit testen, code coverage en komkommers.]({% post_url 2020-10-19-unit-testen-code-coverage-en-komkommers %})
4.  [Wat si low-code en is dat echt zo makkelijk als iedereen zegt?]({% post_url 2020-11-30-what-is-low-code %})

_IT is voor ‘buitenstaanders’ vaak een black box met zijn eigen vakjargon, heel veel afkortingen en vaak zelfs een eigen cultuur. Zaken klinken vaak heel complex en er duiken regelmatig nieuwe buzzwords op met een nieuwe belofte van snelheid, kostenbesparing en toekomstvastheid. Helaas zie je die zaken vanuit de business niet altijd terug._

_Toch zul je verrast zijn over hoe relatief simpel veel IT zaken kunnen zijn. Of beter: zouden moeten zijn. In een aantal korte blogpost zal ik proberen om een aantal van de laatste buzzwords en begrippen uit te leggen zodat ze begrijpbaar zijn en zodat jij vooral beter kan aanvoelen of er effort wordt gestoken in de juiste zaken op het juiste moment._

**Wat is low-code/no-code?**

Low-code betekent dat je softwareproducten kan maken zonder dat je een programmeertaal beheerst. Vaak doe je dit op een low-code development platform wat de omgeving levert waarop je dit kan doen. In theorie doe je dit dan door middel van het selecteren van bestaande elementen die je dan in jouw applicatie op pagina's zet. Je kan het idee een beetje vergelijken met hoe je in Confluence of Microsoft Teams pagina's aanmaakt en daarop verschillende elementen kan zetten. Wordpress is misschien wel het bekendste low-code/no-code platform wat er is.

Netto krijg je hetzelfde soort product dan als je geen low-code platform gebruikt. Een database, een back end, een front end en iets als een api gateway. Het is niet zo dat er een hele nieuwe architectuur of talen op de achtergrond worden gebruikt. Het grootste verschil is dat je all-in gaat op het platform. Waar je bij software development kan kiezen uit verschillende talen en deze kan veranderen als je wil kan je niet makkelijk switchen tussen verschillende low-code platformen.

**Welk probleem lossen we op?**

Het probleem is echter niet dat we niet in staat zijn om snel software kunnen maken. Je hebt al bijna 20 jaar frameworks waarmee je dit kan en er komen steeds meer bij. Het probleem is ook niet dat we software zonder manuele actie naar de eindgebruiker kunnen brengen. Het probleem is ook niet dat we niet in staat zijn om software te maken waar onze gebruikers enorm blij van worden. 

Toch zijn er een aantal beloftes die gedaan worden als het om low-code/no-code gaat. Ik zal er een paar behandelen:

**De belofte: 'Klikkerdeklik en je hebt een live applicatie'**

![](/assets/images/pexels-tatiana-syrikova-3933276.jpg)

Maar denk je eens in waarop je dan 'klikkerdeklik' zomaar even nieuwe functionaliteit maakt? Wie maakt het datamodel en wie zorgt voor de functies die de interface laten werken? Wie definieert de acceptatiecriteria? Wie zorgt er voor jouw (bedrijf)specifieke designs en UI? En wat doe je als als je de element net even wat anders wil laten doen? Wie zal de automatische test implementeren? Hoe zorg je voor continuous delivery? Wat zijn de logische user journeys en hoe kunnen we de roadmap het beste slicen...

Als je al deze vragen in ogenschouw neemt dan is het 'klikkerdeklik' gedeelte maar een fractie van hetgeen er gedaan moet worden. Dit verschilt geheel niet van software development. Daar zit immers ook het meeste werk in de definitie en de detaillering van zaken.

Achter iets als een simpele button is er, net zoals in software development, een hele set aan keuzes die gemaakt moeten worden. Ik zeg niet dat dit heel complex is maar het moet wel gebeuren en iemand zal het moeten doen. Hieronder zie je een voorbeeld van de configuratie van een button in APEX:

![](/assets/images/button-config-screen.png)

**De belofte: 'We kunnen het zelf en hebben dan helemaal geen developers nodig.'**

In praktijk heb je niet minder mensen maar mensen met andere interesses nodig. Nu bestaan de teams waarmee je werkt waarschijnlijk uit software developers die in een bepaalde set van talen(technologie stack) programmeert. Mensen die het leuk vinden om technische problemen op te lossen, nieuwe dingen te maken en nieuwe technische zaken te leren. Vaak vinden developers het leuker en makkelijker om code te schrijven dan om met de muis icoontjes in een interface te slepen en vervolgens parameters via de UI in te geven. Voor de meeste developers lijkt dit een beetje een omslachtige manier om functionaliteit te maken.

Tegenwoordig kan je thuis redelijk goed muziek produceren. Het beeld wat veel mensen daarbij hebben is dat je iets moet hebben om het op te nemen en dat daar jouw fans daar via Spotify of een andere dienst naar kunnen luisteren. 

![](/assets/images/record-listen.png)

Maar om het goed te doen heb je nu nog altijd een engineer nodig. De engineer is de persoon die letterlijk de plaat kan maken of kraken. En engineering is een wereld op zich. Niet iets wat je er even bij doet en in een paar middagjes leert.

![](/assets/images/pexels-clam-lo-3355365.jpg)

Als je dus geen engineer hebt zul je zelf de engineer moeten worden. In het geval van low/no-code zul je de basis moeten leren van HTML, CSS, Javascript en de specifieke database programmeertaal van je platform. En als iets niet werkt zul je het zelf moeten fixen en als iets niet bestaat in het low-code platform zul jij het zelf moeten maken. En dat doe je dan naast je huidige werk want we hebben geen developers meer nodig ;-)

**De belofte: 'Betere producten'**

Als je doel is om betere producten aan je eindgebruikers aan te bieden dan is de techniek het laatste waar je naar zal moeten kijken. Je hebt allereerst een goed beeld van je strategische doelstellingen, business cases, product visies en objectives nodig. Ook als je met een low-code/no-code platform gaat werken. Het maken van betere producten staat los van hoe je deze producten gaat maken. Het hoe dient het wat. 

**De belofte: 'Veel sneller en goedkoper'**

Er zijn een aantal zaken die ons hier in beperken. Binnen een enterprise veranderen de infra en regels niet omdat je functionaliteit bouwt op een low-code platform. Er zijn nog steeds risico's en kansen op fouten. Er zijn nog steeds de afdelingen Risk en Security die hier de regels voor opstellen.

Ook bij low-code/no-code horen automatische testen en continuous integration. Een goede ontwikkeling is dat deze onderwerpen bij software development in het algemeen de standaard zijn en er al heel veel tools en trainingen ed zijn. Bij de huidige low-code/no-code oplossingen lijken deze onderwerpen niet de hoogste prio te hebben en dus in de praktijk wat meer tijd vergen om op te zetten.

Ik heb zelf nog geen open source no-coding platform gevonden. Er zal dus altijd een prijskaartje aan vast zitten.

**Wat? Alweer geen one-size fits all oplossing?**

![](/assets/images/young-3061646_1920.jpg)

Begrijp me niet verkeerd. Ik ben absoluut niet anti-low-code/no-code. Sterker nog, ik ben op dit moment bezig met het opzetten van testautomatisering voor low-code/no-code product. Er zijn zeker een aantal use cases te bedenken waarin ik zelf voor low-code/no-code zou kunnen kiezen. Ik doe dat pas echter nadat ik het domein begrijp en snap welke business doelen we willen halen of welke problemen we willen oplossen. 

Ik ben al gelukkig dat als jij weer hoort dat low-code/no-code echt de de oplossing voor de meeste problemen is dat je even denkt aan big data, blockchain, internet of things, artificial intelligence, scrum, microservices en hoe deze achteraf bij het gemiddelde bedrijf toch niet alle problemen heeft opgelost. 

We komen elke keer in dezelfde situatie als het gaat om trends omdat we te vaak Wat - Hoe - en soms Waarom als volgorde aanhouden in plaats van Waarom - Hoe - Wat. Wat zijn de business doelen of problemen die we moeten oplossen?, Hoe denken we dat we dat het beste kunnen doen? Wat gaan we daarvoor inzetten? Low-code? Ja, in bepaalde gevallen helpt low-code hierbij.
