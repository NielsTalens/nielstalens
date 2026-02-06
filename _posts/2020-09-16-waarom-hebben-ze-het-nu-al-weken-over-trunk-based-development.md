---
layout: post
title: "Waarom hebben ze het nu al weken over Trunk Based Development?"
image: /assets/images/pexels-khari-hayden-923167.jpg
slug: waarom-hebben-ze-het-nu-al-weken-over-trunk-based-development
date: 2020-09-16T22:28:22
categories: ["dear non-it people"]
---
Dit artikel gaat over iets wat we versioning of versiebeheer noemen. Het is een van de basis zaken die je in moet richten als je software ontwikkelt. Waarschijnlijk heb je het woord Git wel eens gehoord. Dit is een van de meest gebruikte versiebeheer systemen. Andere gerelateerde namen die je misschien langs hoort komen zijn: SVN, Mecurial, GitLab, GitHub, BitBucket, Azure devops of AWS code commit.

### **Versiebeheer**

De meeste van ons hebben wel eens te maken met Office en OneDrive of Google Docs en Drive. Het bronbestand staat ergens op een server (vaak in de cloud) en iedereen die toegang heeft kan er wijzigingen in aanbrengen. Als jij lokaal (op jouw computer) een wijziging aanbrengt, dan zie ik dit via de server terug in het document op mijn computer. We kunnen het document in een editor (Word) openen maar ook in de browser als we willen.

Terwijl ik deze blog aan het typen ben zie ik dat het ook gelijk wordt opgeslagen op Google Drive:

![](/assets/images/saved.png)

Dat is mooi want dan weet ik zeker dat mijn bestand veilig in de cloud staat en dat mijn collega's de wijzigingen zullen zien. 

Een ander hele fijne eigenschap van deze manier van werken is het versiebeheer. Ik kan alle opgeslagen wijzigingen zien en kan zelfs versies terug als ik zou willen:

![](/assets/images/Screenshot-2020-09-16-at-18.17.21.png)

In de basis is dit hoe versiebeheer op code ook werkt. Maar waarom zou je hier dan in hemelsnaam weken over discussiëren?

### **Trunk based development vs feature branches**

Je kunt op verschillende manieren omgaan met versiebeheer en op hoe je vervolgens deze software naar productie krijgt. Laten we zeggen dat we samen een document maken en dat er nog iemand is die mee moet lezen.

**Trunk based development** (TBD) betekent dat we afspreken dat we één brondocument gebruiken, wat op een server staat, waar we allebei wijzigingen kunnen aanbrengen. Het mooie ervan is dat de persoon die meeleest alle wijzigingen direct kan zien. We moeten echter wel zeker zijn dat er een hele goede spellingscontrole is anders is de kans dat de meelezer fouten ziet groot.

Als we afspreken om **feature branches** te gebruiken dan maken we allebei een eigen versie van het bestand, dit heet dan een branch oftewel vertakking, (document\_versie\_niels.doc en document\_versie\_jouw\_naam.doc) en voeren allebei onze wijzigingen door. Als jij klaar bent met jouw deel dan upload jij jouw versie naar de server en dient een '**pull request**' in. Ik bekijk jouw wijzigingen en overleg eventueel hoe zaken beter kunnen. Als alles oké is '**merge**' ik jouw versie naar het brondocument en staan jouw wijzigingen in het bronbestand. De meelezer kan na het mergen pas jouw wijzigingen zien.

![](/assets/images/bramches-pexels-veeterzy-38136.jpg)

Image by veeterzy

Nu is versiebeheer wel iets geavanceerder dan dit maar hopelijk heb ik de essentie kunnen uitleggen. Dan kunnen we nu weer naar de initiële vraag:

### Waarom hebben ze het nu al weken over Trunk Based Development?

In de praktijk zijn er veel IT'ers die een sterke mening hebben over welke manier van werken het beste is. Soms is deze mening gebaseerd op het stellige geloof dat de ene manier de enige ware manier is en dat kan best ver gaan. Bepaalde personen of teams zijn zo overtuigd van hun gelijk dat het moeilijk is om een andere kant op te bewegen. Dat is helemaal lastig als ze bij hetzelfde bedrijf werken.

De oorzaak van lange discussies over de versiebeheer strategie is echter vaak een mix van overtuiging en onderliggende zaken. 

Mogelijke onderliggende zaken die ervoor zorgen dat teams feature branches willen gebruiken kunnen zijn:

*   Vertrouwen in elkaar/senioriteit teamleden: Doordat elke wijziging bekeken moet worden dmv het pull request borgen we dat de code is geschreven volgens de norm van het team. Het vier ogen principe geldt hier.
*   Vertrouwen in de kwaliteit van de infrastructuur: Als de omgeving waarop de software moet komen te staan niet goed werkt of vaak stuk gaat is het lastig om deze vaak te gebruiken. Het kiezen voor branches is in dit geval een geval van om de problemen proberen heen te werken.
*   Ontbreken van tests: als er niet voldoende kwaliteit is ingebouwd door onder andere automatische tests (de spellingscontrole van het voorbeeld) is het erg spannend en risicovol om elke versie live te zetten. 
*   ...

Mogelijke onderliggende zaken die ervoor zorgen dat teams trunk based development willen doen zijn:

*   Snelheid van delivery: branches (vertakkingen) zorgen er soms voor dat de wijzigingen die naar productie gaan veel groter zijn (en vaak meer problemen opleveren). Dit betekent dat feedback van de eindgebruiker pas later terugkomt.
*   Kwaliteit en vertrouwen: Het installeren, testen en op de server zetten van de software is een volledig geautomatiseerd process wat erg voorspelbaar is. Het herstellen van eventuele fouten is iets wat snel gaat. Waarom wachten met leveren in dit geval?
*   Snel kleine wijzigingen leveren: Elke feature wordt opgeknipt in zo klein mogelijke werkende software die direct naar productie kan.
*   ...

![](/assets/images/pexels-pixabay-433626.jpg)

**Alweer geen Haarlemmer olie**

Ook mbt het versiebeheer is er geen oplossing die perfect is voor elk team, bedrijf of product en moet een team goed nadenken over de juiste opzet. Het is echter een ondersteunend proces en niet de moeite waard om heel veel tijd en geld aan te spenderen. Het hoofddoel is altijd om een goed eindproduct te ontwikkelen. Niet om matige producten te maken met de perfecte versiebeheer strategie.

Ik gebruik hierbij vaak dezelfde tactiek als die ik hanteer bij de agile processen bij nieuwe teams. Laten we beginnen bij de meest simpele opzet die er mogelijk is en van daaruit bekijken wat we nog meer nodig hebben. Inspect and adapt!

### Extra: een aantal versiebeheer termen:

**Repository:**

De folder waarin het project (en dus alle code staat) binnen een versiebeheer systeem noemen we de repository.

**Merge conflict:**

Het kan bij TBD en feature branches beiden gebeuren dat we beiden dezelfde regel hebben aangepast. Dit heet een merge conflict en we zullen zelf aan Git moeten zeggen welke versie we willen behouden in het bronbestand.

**Push:**

Door Middel van een push commando stuur je de gewijzigde bestanden naar de server. Versiebeheer heeft over het algemeen geen auto-save en upload naar de server. Je bepaalt zelf wanneer je werk af is en het moet worden geupload.

**Pull:**

Om ervoor te zorgen dat je altijd de laatste versie van de bestanden hebt, met de wijzigingen van anderen, download je deze regelmatig dmv het pull commando.