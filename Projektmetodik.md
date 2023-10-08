# Teorihandboken - Projektmetodik (PJ)
Studerande: Emma Jensen

### PJ 1.1 Agila metoder (Scrum, Kanban, Extreme Programming)
Ordet Agil betyder i sig lättrörlig och/eller vig. 
När vi pratar om att en metod inom programering är "vig" (agil) så innebär det att en stor del av arbetet innebär att vara flexibel och planera...

Var öppen för förändring och kommmunikation

  

Fyra viktigaste riktlinjerna inom agila metoder
*(Hannas lektion tis 3e okt)*

1. Individer och interaktioner framför processer och verktyg.    
2. Användbart resulat framför omfattande dokumentation.
3. Kundsamarbete framför kontraktförhandling.
4. Var förberedd att göra ändringar under projektet.
  
--- 
> - Förståelse och tålamod kring att att det kan vara komplext och ibland rent av svårt att veta hur arbetet kommer att gå innan processen påbörjats.
> - Injkuderande och iterativt arbete, 
> - utvärdering efter varje steg är centralt (daily scrums, retrospekt etc)
#### SCRUM

*Personas -> User Stories -> Arbetsuppgifter i pr?*
##### Vad är scrum?
> - Värderinggar och vad dem innebär.
> - Vad fördelarna är


<img src="/Img/scrum-values-transparent.png" alt="Lista över värderingar inom" style="height: 200px; width:300px;"/>

#### Hur ser processen ut?

###### Roller
> - Product Owner
> - Scrum Master
> - Development Team
###### Ceremonier/Aktiviteter
> - Sprint
> - Sprintplanning
>  - Daily scrum
> - Sprint review/Sprint Demo
> - Sprint retrospective

###### Artefakter
> - Product backlog
> - Sprint backlog
> - Increment

### Ceremonierna
##### Sprint
> - 2-4 veckor
> - Spelregler

##### Sprintplanering
> - Vilka kort tar vi ur backlogen för denna sprint?
    - t.ex. feature 1,2 och 3.
  > - Man försöker sätta en velocity om hur många kort man kommer hinna med för att förutse hur lång tid allt kan tänkas ta.
      - Anta alltid att ditt arbete tar ca 2-4 gånger så lång tid som du initiellt tror.
##### Daily scrum
> 15 min varje dag där man står upp och deltagarna berättar vad de ska göra, har fjort och hur det går.
  Tanken är att teamet ska få en uppfattning för hur det går för alla och hur man ska planera dagen.
  Det går att omfördela resurser mellan personer men byter ej kort/arbetsuppgift för sprinten under sprinten pågår.
  Kanske väntar man på info eller material från andra aktörer för att kunna fortsätta arbetet.


   ##### Sprint review/sprint demo
  > Informellt möte.
    Demo för eventuella features.
    Visar det som går att visa.
    "detta gick, detta gick inte"

  ##### Sprint retrospective 
  Utvärderar en sprint, resurser, hantera problem, få erfarenhet, beröm eller annat.

   ### Artefakter
##### Product backlog
  ##### Sprint backlog
  Visualiserar de kort teamet åtagit sig under sprinten.
  (backlogen hanna visade på github)

##### Increment
---
### VERKTYG

#### User Stories
> - Istället för att beskriva features och funktionalitet eller buggar så får endast backlog innehålla stories.
> - Kan även användas under sprint-planning


Utgå från andra människor iom funktionalitet och hur den ska implementeras.

Om vi inte vet så använder vi inte user stories utan undersöker istället vår användarbas genom intervjuer, ta reda på statistik, studier eller annat. (prova på THINK ALOUD)

När vi har få personer att utgå ifrån gör vi istället *Personas* och hitta gemensamma faktorer.

##### Steg för steg.
> 1. Beskrivning
> 2. Konversation - mer detalj
> 3. Tester

##### Persona
Att skapa en *persona* är ett sätt att modellera, summera och kommunicerea insikter i en målgrupp genom en fiktiv person.

Att ha en (eller fler) persona att anpassa önskemål, krav eller behov kring underlättar processen av att ta fram designförslag för specifika personas istället för generellt till "alla" då det blir mindre abstrakt och ger en känsla för sin målgrupp..

  ***En persona***
  En sidas dokument, fokus är förståelse av användaren och dessbehov.
    Det brukar stå lite detaljer(specs) och på vilket sätt personen behöver applikationer/features eller vad som är viktigt.
###### CARD
    - fysisk eller digital "post-it"
    - Används för plannering
    - Påminnelse under konversation (hålla sig på banan)
    - Mer informellt


  >1. "As a **role** I want to **task** so that I can **goal**"
    Vem, vad och varför+
  >2. Detaljer

  ###### Detaljnivå
  - En stor story är en indikation på att den behöver brytas ner i mindre delar
  - En bra riktlinje är att en story ska kunna kodas och testas inom 1/2 dag - 2 veckor
     - Kort som går att utföra på en halv dag är optimalt, då syns det även för produktägaren att projektet rör sig framåt.
   - En story som innefattar två eller fler storys kallas en *epic* 
     - Delas ofta upp i mindre stories
       - Exempel 1.
       - Exempel 2.
       - Exempel 3.

###### Konversation
  ????

  ###### Konfirmation
   - I Planeringsfasen används baksidan av kortet för att hänvisa till acceptanstester.
  -  Ju tidigare man tänker på acceptanstester, desto bättre.

##### Scrum Poker
  Estimera komplexiteten i utvecklingen.
- Att göra detta är momentet som programerare har svårast med, utöver sin kod.
-  Istället för i tid- tänk komplexitet i utveckling
 - Ge varje story ett representativ värde mellan 1-12
 - där 1 är lågt och 12 är högt- Story points
 - en iteration får endast innehålla den mängd story points så länge velocity inte överskrids.

![Hur Processen ser ut med alla dess steg.](img/scrum-transparent.webp)

[Sebastians lektioner]

--- 
#### KANBAN
> blockquote Vad är Kanban?
> 
---
### Kanban vs Scrum
|                *PROCESSER*                |                                                                                   *Kanban*                                                                                   |                                                                                            *Scrum*                                                                                             |
| :---------------------------------------: | :--------------------------------------------------------------------------------------------------------------------------------------------------------------------------: | :--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------: |
|              **Arbetsmetod**              |  Fokuserar på att optimera ett kontinuerligt <br /> arbetsflöde inom problemlösningsprossecen med issues, <br /> för att få arbetet flytade i en strömlinjeformad riktning.  |                                                      Scrum är en ramkverk som genom att jobba i korta inkriments <br /> ger en helt allat                                                      |
|                **Tidsram**                | I Kanban arbetar teamet löpande med issues, vilket innebär att det inte finns en tidsram enligt Kanban som bör hållas även om det finns inom teamet och enligt prioritering. |                                                                       Sprints på 2-4 veckor där arbetsuppgiften slutförs                                                                       |
|               **Planering**               |                                  PLanering sker löpande under projektet och besluten tas oftast med arbetsbörda och framsteg som underlag.                                   |                            Inför varje sprint i scrum så uförs en sprintplanering från backlogen med priorineringslista och det bestäms vem som tar vilket område.                             |
|                **Roller**                 |     I Kanban jobbar man sällan med förutbestämda roller så som i scrum utan fokuserar på att hela teamet tillsammans strukturerar upp och sköter processen tillsammans.      | -  Product  Owner, Scrum Master, Development Team. Det är dock även här kutym att hela teamet ror projektet i hamn, det är ingen som iom sin roll har större ansvar för deploy än någon annan. |
| **Granskning och retrospektivceremonier** |
|  **Förändringar under pågående arbete**   |                             Uppmuntrar förändring under hela arbetets gång för att effektivisera framsteg eller krav som uppkommit efter start.                              |                                             Undviker förändring i arbetet under sprinten man befinner sig i. Ändringar görs under sprintplanering.                                             |

Både Kanan och Scrum är agila ramverk för att på ett flexibelt sätt strukturera upp hur ett team arbetar. Det beror mest på arbetsuppgiftens karaktär vilket ramverk man väljer, alt på hur teamet arbetar bäst. 
Den största skillnaden mellan just Scrum och Kanban är att Scrum har en tydligare struktur gällande roller, tidsramar och ceremonier medan Kanban är än mer flexibelt och fokuserar på att löpande optimera sin process under hela tiden arbetet pågår.


















---
#### Extreme programming

> 	***Referenser:***
[- Shareitsolutions](https://www.shareitsolutions.com/blog/agile-non-agile/)
[- Codeop](https://codeop.tech/what-exactly-is-not-agile/)
[- Onbird](https://onbird.se/grunderna-i-scrum/?utm_term=&utm_campaign=I+-+Performance+Max+-+Konsult&utm_source=adwords&utm_medium=ppc&hsa_acc=5250760349&hsa_cam=19864017095&hsa_grp=&hsa_ad=&hsa_src=x&hsa_tgt=&hsa_kw=&hsa_mt=&hsa_net=adwords&hsa_ver=3&gad=1&gclid=Cj0KCQjwpompBhDZARIsAFD_Fp9ypqe75C9pRfBT-tiTinJcUAWPTIwUnKZaN4DUtQNbfMWEcVILV5AaAnfuEALw_wcB)
[Kursmaterial lektion 8.9]
--- 
### PJ 1.2 Icke-agila metoder
Beskriv rubriken nedan här

> Vissa saker ska ske steg för steg. I situationer där något måste fungera felfritt vid första launch. T.ex. flygplansmjukvara, hjälpmedel inom sjukvård, hjärtstartare etc.
#### Waterfall


## PJ 1.3 Entreprenörskap inom webbutveckling
Beskriv rubriken nedan här

## PJ 1.4 Issue distribution and handling in a group
Vad innebär det?
> Vad ska göras och i vilken prio?
> Vem gör vad?
> Hur delar man upp i github? - backlog i projects, hur man skapar dem. 
>  Skapa ej för stora tasks. T.ex. "create fronpage", skapa istället mindre som "Create navbar", "style footer", "create draft about section"
> Hur kopplar man issues med commits?
> delegera efter urgency.
>
Vad är en issue?
- En issue på github är en "arbetsuppgift"

- Hur hanterar man issues i github?

