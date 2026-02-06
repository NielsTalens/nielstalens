---
layout: post
title: "Over pipelines en continuous van alles en nog wat."
image: /assets/images/lost-places-2178884_1920-MichaelGaida-Pixabay.jpg
slug: over-pipelines-en-continuous-van-alles-en-nog-wat
date: 2020-10-19T22:46:24
categories: ["dear non-it people"]
---
Dit is het tweede artikel in de 'Dear non-IT people' reeks waarin ik IT begrippen probeer te versimpelen voor niet ICT ers. Het eerste ging over versiebeheer:

[Waarom hebben ze het nu al weken over Trunk based development?]({% post_url 2020-09-16-waarom-hebben-ze-het-nu-al-weken-over-trunk-based-development %})

_IT is voor 'buitenstaanders' vaak een black box met zijn eigen vakjargon, heel veel afkortingen en vaak zelfs een eigen cultuur. Zaken klinken vaak heel complex en er duiken regelmatig nieuwe buzzwords op met een nieuwe belofte van snelheid, kostenbesparing en toekomstvastheid. Helaas zie je die zaken vanuit de business niet altijd terug._

_Toch zul je verrast zijn over hoe relatief simpel veel IT zaken kunnen zijn. Of beter: zouden moeten zijn. In een aantal korte blogpost zal ik proberen om een aantal van de laatste buzzwords en begrippen uit te leggen zodat ze begrijpbaar zijn en zodat jij vooral beter kan aanvoelen of er effort wordt gestoken in de juiste zaken op het juiste moment._

Continuous integration, delivery & deployment zijn een aantal begrippen die je waarschijnlijk de laatste jaren steeds vaker hebt gehoord. Het zijn geen hele nieuwe onderwerpen en ze zijn in de loop van de laatste 10 jaar eigenlijk wel de industrie standaard geworden voor software development.

In basis is continuous delivery het process om de code van iemands computer geautomatiseerd naar de eindgebruiker te krijgen. In het kort de drie continuous zaken waar je waarschijnlijk vaker over gehoord hebt:

## Continuous integration

In dit artikel beschreef ik hoe versiebeheer in de basis werkt. Continuous integration wordt getriggerd door het versiebeheer systeem. Elke keer dat er een stukje code naar de versiebeheer repo wordt server gestuurd gaat ook de continuous integration server aan de slag. We zeggen dan dat de pipeline draait. Deze pipeline is niet anders dan een aantal script die tegen de server zeggen dat deze de code moet bouwen, dan de automatische test moet doen, vervolgens de code op security en code kwaliteit moet checken en om deze code vervolgens ergens neer te zetten. Als er in een stap iets niet goed is stopt het hele proces.

## Continuous delivery

Het op de server zetten van software was vaak een lastig en irritant klusje. Enerzijds was het een repeterend ding maar waren er wel vaak scripts waar je je aan moest houden. Als je geluk had dan. Als je pech had was er één persoon die het altijd deed en wist hoe eea moest. Je weet wel, de persoon die nooit op vakantie kon gaan.

![](/assets/images/cd-all.png)

Het continuous delivery process zet de software automatisch op de server op het moment dat je dit wil. Het zorgt ervoor dat database changes of migraties worden doorgevoerd, configuratie in het netwerk goed is, stopt en start de server indien nodig ed. Vervolgens draait het de acceptatie testen om te kijken of alles in orde is.

## Continuous deployment

Het verschil tussen continuous delivery en continuous deployment is dat je bij continuous delivery zelf bepaalt wanneer je deployed naar productie maar bij continuous deployment dit altijd gebeurd. Elke wijziging gaat dus direct naar de eind gebruiker:

![](/assets/images/deployment.png)

Welke problemen lossen we eigenlijk op?

*   Eliminatie repeterend en handmatig werk, 
*   Snelle feedback (als er iets niet goed is krijgen we daar direct een melding van),
*   Geen 'It works on my machine' meer. De software wordt immers door verschillende checks gehaald op verschillende systemen. 
*   Betrouwbare delivery en minder verstoringen tijdens en na deployments,
*   Weinig/geen tijd besteden aan deployment (tijd die in ontwikkelen kan worden gestoken),
*   Een mooi overzicht van knelpunten (doorlooptijd pipelines, aantal fouten na deployment, aantal deployments,... ),
*   Mogelijkheid voor thresholds. Door de kwaliteitschecks op te nemen kunnen we er voor zorgen dat de pipeline faalt als we onder deze criteria zitten,
*   ...

## Gold plating

Het maken en gebruiken van een goede pipeline is niet alleen enorm nuttig en kosten/tijd besparend, maar is voor veel mensen ook erg leuk om te maken. Dit is automatisering in de puurste zin van het woord. Er is ook erg veel mooie tooling en integraties met andere systemen. Daar schuilt een klein gevaar in als we niet oppassen: continuous delivery is een manier van werken die vaak erg nuttig is maar nooit een doel op zich.

![](/assets/images/faucet-1529179_1920_Retro-Gerber-Pixabay.jpg)

Vergelijk het met een keukenkraan. De kraan is er om water uit te halen. Er zullen altijd nieuwe en mooiere kranen gemaakt worden maar hetgeen waar het om gaat, water, moet er gewoon goed uitkomen. En altijd! En zo snel mogelijk.

Er zijn voor iemand die niet direct in het development team zit een aantal signalen waar je op kan letten:

*   Een pipeline die erg vaak faalt. Dit kan natuurlijk honderden redenen hebben maar ergens moet er toch een concrete oorzaak zijn. Als er een tal van oorzaken zijn (of er is geen eenduidig antwoord op de vraag wat de oorzaak is) dan adviseer ik om eens een value stream mapping met het team te doen. Dit is een hele fijne en snelle manier om te bekijken waar de meeste winst te behalen is. \[ https://en.wikipedia.org/wiki/Value-stream\_mapping\]
*   Een pipeline die langer kapot is. Vaak heb je hier te maken met gebrek aan gedeelde kennis en geen DevOps mindset. Een van de mantra's van continuous delivery is: 'if you break it, you fix it'. In principe gaat het fixen van de pipeline voor alles.
*   Er wordt veel tijd gespendeerd aan de pipeline. Hoewel er net als aan alle infra zaken tijd gespendeerd moet worden moet er ook voor deze zaken wel bekeken worden wat ze waard zijn. Soms zijn we zo aan het optimaliseren mbt continuous delivery terwijl een eindgebruiker die milliseconde winst in de automatische testen nooit zal zien in de applicatie. Sterker nog: alle tijd die we in die suboptimalisatie steken besteden we juist niet aan het verbeteren van de user experience! Om wel de juiste zaken te optimaliseren kan hier ook weer een value stream mapping de uitkomst bieden.
*   Geen zichtbaarheid/dashboards en alerts. De essentie van continuous integration is fast feedback. De pipeline werkt zo dat we, op het moment dat er iets niet ok is, we dit gelijk weten. De pipeline faalt immers. Dit zou je dus dan ook ten alle tijde moeten kunnen zien dmv dashboards en alerting.  
*   …

Value stream mapping voor continuous deployment:

![](/assets/images/better-faster-vsm.png)

Een continuous deployment pipeline is dus niks anders dan een aantal scripts die op logische volgorde worden uitgevoerd. Vroeger voerden we de scripts zelf uit en nu doet Jenkins, Azure DevOps, GitLab of Bamboo dit voor ons. Niks meer en niks minder. De essentie is om zsm feedback te krijgen over de kwaliteit van de software en het proces om deze naar de gebruiker te krijgen. Deze manier van werken kan er dus voor zorgen we die tijd nu dus besteden aan het mooier en beter maken van onze producten.