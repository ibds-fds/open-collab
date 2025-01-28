---
layout: default
---

# API Groeimodel

> [!Note]Uitleg
> Dit document is bedoeld om samen te werken, input en feedback
op te halen over dit onderwerp.

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

![API Groeimodel praatplaat](https://github.com/ibds-fds/open-collab/blob/8f9d2ab5dc46c87306e97caee0b856720d8e6e28/docs/api-groeimodel/fds-dataservice-levels.jpg?raw=true)

# API Groeimodel voor Data Ontsluiting

Dit model biedt een gestructureerde aanpak voor organisaties om hun API-capaciteiten te ontwikkelen van een basis implementatie naar een volledig event-driven architectuur. Enkele belangrijke kenmerken van het model:

- Incrementele groei: Elk level bouwt voort op het vorige
- Praktische implementatie: Concrete capabilities per niveau
- Holistische benadering: Zowel technische als organisatorische aspecten
- Flexibiliteit: Organisaties kunnen hun eigen tempo bepalen

## Level 0: Basis API Aanwezigheid

- Implementatie van een basis REST API
- Fundamentele CRUD-operaties (Create, Read, Update, Delete)
- Basis authenticatie en autorisatie
- Minimale documentatie voor directe gebruikers
- JSON als standaard formaat voor data uitwisseling

## Level 1: Gestructureerde Metadata

- Implementatie van OpenAPI/Swagger specificaties
- Gestandaardiseerde foutafhandeling en statuscodes
- Basis versioning van de API
- Uitgebreide API documentatie met voorbeelden
- Monitoring van API gebruik en beschikbaarheid
- Rate limiting en quota management

## Level 2: Semantische Laag

- Implementatie van een ontologie voor datastructuren
- Gedocumenteerde relaties tussen databronnen
- Gestandaardiseerde begrippenkader en definities
- Content negotiation (JSON, XML, RDF)
- Implementatie van linked data principes
- Semantic versioning

## Level 3: Event-Driven Architectuur

- Implementatie van webhook mechanismen
- Audit logging van belangrijke gebeurtenissen
- Event-notifications voor data wijzigingen
- Mogelijkheid tot het abonneren op specifieke events
- Tracking van data lineage
- Asynchrone verwerkingspatronen

## Level 4: Event Sourcing

- Volledig event-gebaseerde architectuur
- Complete audit trail van alle wijzigingen
- Temporal querying (historische states opvragen)
- Event replay mogelijkheden
- Complex event processing
- Stream processing capabilities

## Level 5: Rijke Event Stream

- Real-time event streaming
- Geavanceerde event patronen herkenning
- Machine learning op event streams
- Predictieve analyses
- Self-healing capabilities
- Automatische schaalbaarheid

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
