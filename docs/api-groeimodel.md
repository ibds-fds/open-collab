---
layout: default
---

# API Groeimodel

> [!Note]Uitleg
> Dit document is bedoeld om samen te werken, input en feedback
op te halen over dit onderwerp.

> [!Note]Status v0.1
> Er is een eerste versie van het groeimodel uitgewerkt door Marc van Andel en feedback is van harte welkom. De implementatie onderdelen zijn nog erg prematuur en slechts ter suggestie.

> [!Note]Participeren?
>
> [![hackmd-github-sync-badge](https://hackmd.io/@sKaZGRntQFK2ujQafF2s3g/By6z6yxdke/badge)](https://hackmd.io/@sKaZGRntQFK2ujQafF2s3g/By6z6yxdke) \
> :100: Het staat iedereen vrij te participeren in dit document. Op basis van goed vertrouwen.

> [!Important]Beheerder
> :smiley: Marc van Andel

> [!Tip]Github account?
> :star: Voor iedereen met een github account. Je kan
hier inloggen via dat account zodat je bijdragen traceerbaar zijn.

Natuurlijk zijn er
[REST-API Design Rules](https://www.forumstandaardisatie.nl/open-standaarden/rest-api-design-rules).
Dat is een mooi begin. Maar is een REST API _alles_? :thinking_face: 

Sterker nog, een API is het begin van het ontsluiten en (dus) kunnen raadplegen van gegevens. Een RESTful API heeft ook mogelijkheden voor het bijwerken van informatie. Maar ... is dat voldoende voor de informatievoorziening in een keten? **Nee! Zeker niet!**

Oh nee? Hoezo dan?

Wel, bij het delen van informatie is de _interpretatie_ ook van groot belang. U hebt het over een `brug`? Is dat een `brug` vanuit het perspectief van een weggebruiker? Of is dat een `brug` vanuit het perspectief van een vaartuig? Of ... is dat het perspectief gezien vanuit de tandheelkunde? :boom: 

**Metadata** _matters_. Begrippen, ontologieën, informatiemodellen, algoritmes; ze doen ertoe! Bij het delen van informatie (data, gegevens) tussen twee organisaties is het van belang dat de interpretaties op elkaar aansluiten. En dat passende transformaties worden toegepast. Voor een overheidsorganisatie komen daar nog _publieke waarden_ bij als dataminimalisatie, privacy bewaking en verantwoording. Dit is allemaal nog niet zo eenvoudig...

Alleen een (REST) API is niet genoeg. Er is méér nodig! 'Capabilities' als historische bevragingen, traceerbaarheid en correctie zijn moeilijke en ingewikkelde eisen. En zit daar mogelijk een opbouw in?

Dit is precies de vraag van het **API Groeimodel**. Welke capabilities heeft een API nodig en hoe zou daarin een groeimodel, volwassenheidsmodel, niveau's in opgesteld kunnen worden? En bij voorkeur ook gelijk: _hoe_ vul je die eisen dan (mogelijk) in?

Praatplaat:

![API Groeimodel praatplaat](https://github.com/ibds-fds/open-collab/blob/main/docs/api-groeimodel/API-Groeimodel.jpg?raw=true)

# Het model

Dit model biedt een gestructureerde aanpak voor organisaties om hun API-capaciteiten te ontwikkelen van een basis implementatie naar een volledig event-driven architectuur. Enkele belangrijke kenmerken van het model:

- Incrementele groei: Elk level bouwt voort op het vorige
- Praktische implementatie: Concrete capabilities per niveau
- Holistische benadering: Zowel technische als organisatorische aspecten
- Flexibiliteit: Organisaties kunnen hun eigen tempo bepalen

Het model bestaat uit de volgende levels:

- [Level 0: Basis API Aanwezigheid](#Level-0-Basis-API-Aanwezigheid)
- [Level 1: Gestructureerde Metadata](#Level-1-Gestructureerde-Metadata)
- [Level 2: Semantische Laag](#Level-2-Semantische-Laag)
- [Level 3: Historie en Correctie](#Level-3-Historie-en-Correctie)
- [Level 4: Event-Driven Architectuur](#Level-4-Event-Driven-Architectuur)
- [Level 5: Rijke Event Stream](#Level-5-Rijke-Event-Stream)

## Level 0: Basis API Aanwezigheid

Voor een API groeimodel is (uiteraard) eerst een API nodig. In het kader van dit groeimodel wordt met API geduidt op een 'web API', een Application Programming Interface (API) die via het web / internet te benaderen is. De meest bekende en huidige staat van technologie gebruikte vorm is **REST API**. Dat betekent dat een API via het internet(protocollen) te benaderen is en gebruik maakt van JSON, de JavaScript Object Notation, voor data uitwisseling.

Denk bij dit niveau aan:

- Implementatie van een basis REST API
- Fundamentele ~~CRUD-operaties (Create, Read, Update, Delete)~~ Read operatie
- Basis authenticatie en autorisatie
- Minimale documentatie voor directe gebruikers
- JSON als standaard formaat voor data uitwisseling

## Level 1: Gestructureerde Metadata

Een REST API wordt beter te gebruiken als deze voorzien van documentatie en allerlei metadata over dit gebruik. Om dit te bereiken bestaat al een mooie set van [REST API Design Rules](https://www.forumstandaardisatie.nl/open-standaarden/rest-api-design-rules).

De strategie in de ontwikkeling van (REST) API's is **API First**. Dat betekent dat _eerst_ het (API) contract wordt opgesteld waar de API aan gaat voldoen. _Daarna_ komt pas de implementatie en het gebruik. Een 'API contract' wordt opgesteld volgens de open standaard [Open API Specificatie](https://www.forumstandaardisatie.nl/open-standaarden/openapi-specification), voorheen en ook bekend als Swagger.

Met REST API's wordt ook vaak [REST*ful*](https://docs.geostandaarden.nl/api/vv-hr-API-Strategie-20190715/#restful-principles) bedoeld of begrepen. Dit gaat uit dat elk data-object een *Resource* is waarop 'functies' kunnen worden aangeroepen. Er zijn ook alternatieven van REST API's die hier andere oplossingen voor bieden, zoals GraphQL en SPARQL. Dit zijn goeie alternatieven met verschillende karakteristieken in ontwikkeling en gebruik.

Denk bij dit niveau aan:

- Implementatie van OpenAPI/Swagger specificaties
- Gestandaardiseerde foutafhandeling en statuscodes
- Basis versioning van de API
- Uitgebreide API documentatie met voorbeelden
- Monitoring van API gebruik en beschikbaarheid
- Rate limiting en quota management

## Level 2: Semantische Laag

Hoewel gestructureerde metadata al mogelijkheden geeft voor uitgebreidere beschrijving van de data en het gebruik, ontbreekt daar de verplichting om de semantiek uitgebreid en volledig te beschrijven. Voor het gebruik is het wel van belang dat begrippen en terminologie (ontologie) wel overeenkomst met de informatie die beschikbaar wordt gesteld dmv een API. In level 2 ligt de nadruk daarom op de volledigheid en uitgebreidheid van de semantiek.

Semantische standaarden zijn vooral bekend als [linked data](https://nl.wikipedia.org/wiki/Linked_data). Hoewel semantiek ook met REST(ful) API's mogelijk is, worden hier toch vaak de alternatieven GraphQL en SPARQL gebruikt. SPARQL is echt gebaseerd op de semantische standaarden en linked data. GraphQL is een 'middenweg' tussen REST API's en SPARQL. In gebruik lijkt GraphQL sterk op REST, terwijl structuur en semantiek wel afgedwongen worden en flexibel ingezet kunnen worden.

Denk bij dit nvieau aan:

- Implementatie van een ontologie voor datastructuren, bijvoorbeeld dmv semantische standaarden
- Gedocumenteerde relaties tussen databronnen, zie ook [NORA Online | Nationaal Semantisch Vlak](https://www.noraonline.nl/wiki/Nationaal_Semantisch_Vlak) en [federatief.datastelsel.nl | Metadata](https://federatief.datastelsel.nl/kennisbank/metadata/)
- Gestandaardiseerde begrippenkader en definities
- Content negotiation (JSON, XML, RDF)
- Implementatie van linked data principes
- Semantic versioning

## Level 3: Historie en Correctie

Waar voorgaande levels gingen over seq ontsluiting en semantiek ontbreekt het daar nog aan het besef van historie. Als data (her)gebruikt wordt, is het van belang _wanneer_ dat precies gebruikt is, zeker als die data gebruikt is bij besluiten in het verleden. Het zou zomaar kunnen gebeuren dat deze besluiten bevraagd of zelfs in twijfel worden getrokken en dan moet het mogelijk zijn om opnieuw _dezelfde_ vraag te kunnen stellen. Of te weten wat er mogelijk gewijzigd is _in het verleden_, bijvoorbeeld door correcties, waardoor we nú meer weten. Dan zou het zomaar anders kunnen zijn dan ten tijde van het maken van de beslissing.

API's dienen daarom historische bevragingen te ondersteunen en het besef van tijd en versies van gegevens te kennen. Dit wordt ook wel lineage of traceerbaarheid genoemd. Voor toepassing van deze capaciteiten bestaan er ook semantische standaarden die aanbevolen worden om te volgen.

Het project [Uit betrouwbare bron](https://uitbetrouwbarebron.nl) beoogt duidelijkheid en richting te geven aan hoe dit in de context van registers van een (digitale) overheid toe te kunnen passen.

Denk bij dit niveau aan:

- Implementatie van historie, bi-temporale bevraging en semantische standaarden tbv lineage
- Vastleggen van uitgeleverde gegevens
- Audit logging van opgevraagde gegevens
- Versioneren van gegevens
- Temporal querying (historische states opvragen)

## Level 4: Event-Driven Architectuur

De voorgaande niveau's geven vooral richting voor het ontsluiten van gegevens (data). Hergebruik van data / gegevens en API's betreft ook voornamelijk het ontsluiten, terwijl wijzigen veel beperkter herbruikbaar en vrijwel altijd een specifieke context kent. API's voor het wijzigen van data kennen daarom een ander karakter. Dit wordt ondersteund door het [Command Query Responsibility Segregation (CQRS)](https://en.wikipedia.org/wiki/Command_Query_Responsibility_Segregation) patroon. Dit stelt dat API's voor wijzigen ('Commands') anders en gescheiden moeten zijn van API's voor opvragen / ontsluiten ('Queries').

Bij het wijzigen van gegevens / data komt een extra aspect kijken, namelijk het informeren dat er wijzigen zijn aan afnemers. Een systeem kent API's voor het ontsluiten en daar wordt hergebruik van gegevens mogelijk gemaakt dmv API's. Maar afnemers willen wellicht *óók* weten dat er wijzigingen zijn in eerder opgevraagde en gebruikte gegevens. Als op basis van die gegevens in 'afnemende processen' beslissingen zijn genomen, dan zouden wijzigingen van die opgevraagde gegevens wellicht tot impact in die processen kunnen leiden.

Het informeren over wijzigingen aan afnemers wordt vaak [notificeren](https://www.noraonline.nl/wiki/Notificeren_aan_belanghebbenden_van_gebruik_van_machtigingen) (NORA definitie) genoemd. Hierbij is het uitgangspunt dat afnemers zich abonneren op een gegeven / object / resource en dan notificaties krijgen dat er wijzigingen (updates) zijn. Dit is ook bekend als het publiceren van 'events', gebeurtenissen. Het inrichten van acties die reageren op gebeurtenissen wordt een _Event Driven Architecture_ genoemd, in het Nederlands ook wel _gebeurtenisgedreven architecturen_ genoemd. In ieder geval komt het erop neer dat wijzigingen van gegevens / data / objecten / resources naast de gegevens zelf ook gepubliceerd worden, op te vragen zijn of zelfs op te abonneren zijn.

Denk bij dit niveau aan:

- Implementatie van webhook mechanismen
- Audit logging van belangrijke gebeurtenissen
- Event-notifications voor data wijzigingen
- Mogelijkheid tot het abonneren op specifieke events
- Tracking van data lineage
- Asynchrone verwerkingspatronen

## Level 5: Rijke Event Stream

De Event-Driven architectuur van level 4 is mogelijk met redelijk traditionele software architecturen. Dit kent echter de beperking dat gebeurtenissen / events afgeleid zijn uit de traditionele 'bijwerk functionaliteiten'. Maar de volgende stap is dat ook de systemen zélf gebaseerd zijn op gebeurtenissen oftewel 'events'. Dit patroon heet **Event Sourcing**. Dit is architectuurpatroon is in de techniek al lang toegepast bijvoorbeeld voor database replicatie. Vanuit de stroming waarin het businessdomein centraal staat, genaamd *Domain Driven Design*, wordt Event Sourcing als businesspatroon toegepast. Hierdoor ontstaat er synergie tussen techniek, software en businessprocessing. Event-Driven architecturen worden hierdoor veel sterker en veel minder technisch gedreven.

Event Sourcing versterkt de Event-Driven architecturen en daarmee ontstaat met dit niveau een rijke set aan mogelijkheden voor het bijwerken van gegevens / data en het ontsluiten daarvan. De ontsluiting van het bijwerken kan dmv rijke event streams waarop afnemers zich kunnen abonneren en zelfs een eigen interpretatie zouden kunnen doen van wat die gebeurtenissen in hun domein voor effect hebben. Zo ondersteunt het ook de mogelijkheden van *meerdere* projecties of 'Queries' van het CQRS patroon. Het wordt mogelijk om voor verschillende contexten van hergebruik toegespitste ontsluiting API's beschikbaar te stellen en bijvoorbeeld dataminimalisatie optimaal toe te passen.

Het project [Uit betrouwbare bron](https://uitbetrouwbarebron.nl) beoogt duidelijkheid en richting te geven aan hoe dit in de context van registers van een (digitale) overheid toe te kunnen passen.

Denk bij dit niveau aan:

- Volledig event-gebaseerde architectuur
- Complete audit trail van alle wijzigingen
- Event replay mogelijkheden
- Complex event processing
- Stream processing capabilities

# Implementatievereisten

## Per Level Vereiste Capabilities

### Technisch

- Infrastructuur requirements
- Security maatregelen
- Performance eisen
- Schaalbaarheid voorzieningen

### Organisatorisch

- Governance structuren
- Team competenties
- Documentatie standaarden
- Support processen

### Data Management

- Data kwaliteit controles
- Privacy maatregelen
- Retention policies
- Backup strategieën

## Transitie tussen Levels

Voor elke overgang tussen levels moet een organisatie:
1. Assessment uitvoeren van huidige capabilities
2. Gap analysis maken voor het volgende level
3. Roadmap opstellen voor implementatie
4. Risico analyse uitvoeren
5. Resources alloceren
6. Training en educatie verzorgen
7. Monitoring implementeren voor succes metrics

## Succesfactoren

- Executive sponsorship
- Duidelijke business case per level
- Adequate resource allocatie
- Gestructureerd change management
- Continue evaluatie en bijsturing
- Stakeholder management
- Training en kennisdeling

# Implementatie

## Level 0: Basis API Aanwezigheid

### Kenmerken

- Eenvoudige REST API die data ontsluit via HTTP-endpoints
- Basis CRUD-operaties op resources
- Vaste endpoint structuur (bijvoorbeeld `/api/v1/resources`)
- Consistente JSON response structuur
- Statische dataset zonder real-time updates

### Technische Vereisten

- HTTP/HTTPS toegang
- Basis authenticatie (bijvoorbeeld API key of Bearer token)
- JSON response formatting
- Standaard HTTP methodes (GET, POST, PUT, DELETE)
- Basis foutafhandeling met HTTP status codes
- Minimale input validatie

### Documentatie & Support

- Basis README met endpoint beschrijvingen
- Voorbeelden van requests en responses
- Contactpersoon voor support vragen
- Handleiding voor authenticatie
- Basis troubleshooting guide

### Beperkingen

- Beperkte schaalbaarheid
- Geen formele versioning strategie
- Basis rate limiting
- Beperkte zoek- en filtermogelijkheden
- Geen formele SLA's

## Level 1: Gestructureerde Metadata

### API Specificatie

- Volledige OpenAPI/Swagger documentatie
- Machine-readable API specificaties
- Gestandaardiseerde response schemas
- Uitgebreide foutcodes en beschrijvingen
- Consistent gebruik van HTTP methods en status codes

### Monitoring & Beheer

- API usage analytics
- Performance monitoring
- Uptime tracking
- Response time metrics
- Error rate monitoring
- Gebruiksstatistieken per endpoint

### Verbeterde Functionaliteit

- Paginatie voor grote datasets
- Uitgebreide zoek- en filtermogelijkheden
- Field selection (sparse fieldsets)
- Sorting opties
- Bulk operations
- Caching headers

### Governance

- API style guide
- Versioning strategie
- Deprecation policy
- SLA definities
- Rate limiting policies
- Security policies

## Level 2: Semantische Laag

### Ontologie & Datamodel

- Formele beschrijving van concepten en relaties
- RDF/OWL ontologie definities
- Linked Data principes implementatie
- URI strategie voor resources
- Semantic versioning van het datamodel
- Begrippenwoordenboek

### Data Standaardisatie

- Gestandaardiseerde datatypes
- Gevalideerde waardenlijsten
- Domein-specifieke vocabulaires
- Mapping naar standaard ontologieën
- Cross-referencing tussen concepten
- Temporele aspecten van data

### Interoperabiliteit

- Content negotiation (JSON-LD, RDF, Turtle)
- Hypermedia controls (HATEOAS)
- Schema.org annotaties
- Dublin Core metadata
- Semantic annotations
- Interface contracts

### Data Kwaliteit

- Data validatie regels
- Kwaliteitsmetrieken
- Consistentie checks
- Completeness validatie
- Referentiële integriteit
- Data lineage tracking

### Gebruikerservaring

- Interactieve API documentatie
- Semantische zoekmogelijkheden
- Context-aware responses
- Suggesties voor gerelateerde resources
- Intelligente query expansie
- Betekenisvolle foutmeldingen

### Governance & Beheer

- Semantisch model governance
- Versiebeheer van ontologieën
- Change management proces
- Stakeholder consultation
- Review procedures
- Impact analyses

### Tools & Infrastructuur

- Triple stores
- SPARQL endpoints
- Ontologie editors
- Validatie tools
- Visualisatie tools
- Testing frameworks
