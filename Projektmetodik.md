# Teorihandboken - Projektmetodik (PJ)
Studerande: Emma Jensen

### PJ 1.1 Agila metoder (Scrum, Kanban, Extreme Programming)
Ordet Agil betyder i sig lättrörlig och/eller vig. 
När vi pratar om att en metod inom programering är "vig" (agil) så innebär det att en stor del av arbetet innebär att vara flexibel och planera för förändring under projektets gång.

"Var öppen för förändring och kommmunicera"

  

Fyra ==viktigaste== riktlinjerna inom agila metoder
*(Hannas lektion tis 3e okt)*

1. Individer och interaktioner framför processer och verktyg.    
2. Användbart resulat framför omfattande dokumentation.
3. Kundsamarbete framför kontraktförhandling.
4. Var förberedd att göra ändringar under projektet.
  
--- 
> - Förståelse och tålamod kring att att det kan vara komplext att planera och ibland rent av svårt att veta hur arbetet kommer att gå innan processen påbörjats.
> - Inkluderande och iterativt arbete, 
> - Utvärdering efter varje steg är centralt inom agila metoder (daily scrums, retrospekt etc).
#### SCRUM
##### Scrum Values
<img src="/Img/scrum-values-transparent.png" alt="Lista över värderingar inom" style="height: 200px; width:300px;"/>

#### Vad betyder det att arbeta i scrum och vilka delar ingår?
##### Roller
> - Product Owner
> - Scrum Master
> - Development Team

 ##### Artefakter
> - Product backlog
> - Sprint backlog
> - Increment
##### Ceremonier/Aktiviteter
> - Sprint
> - Sprintplanning
>  - Daily scrum
> - Sprint review/Sprint Demo
> - Sprint retrospective

 ### Artefakter
###### Product backlog
###### Sprint backlog
  Visualiserar de kort teamet åtagit sig under sprinten.
  (backlogen hanna visade på github)

###### Increment


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

  ![Hur Processen ser ut med alla dess steg.](img/scrum-transparent.webp)

---
### VERKTYG

##### USER STORIES
> - Istället för att beskriva features och funktionalitet eller buggar så får backlog endast innehålla stories.
> - Kan även användas under sprint-planning

Om vi inte har klar insikt i vår demografi så använder vi inte user stories utan undersöker istället vår användarbas genom intervjuer, tar reda på statistik, studier eller annat.

När vi däremot har för få personer att utgå ifrån gör vi istället *Personas* och hitta gemensamma faktorer.
--- 
##### PERSONA
Att skapa en *persona* är att på ett visuellt sätt ge en representation av målgruppen man vill nå och kommunicerea insikter om den genom en fiktiv person.

Att ha en (eller fler) persona att anpassa önskemål, krav eller behov kring underlättar processen av att ta fram designförslag för specifika personas istället för generellt till "alla" då det blir mindre abstrakt och ger en känsla för sin målgrupp..

 Vad är det?
  : Det är ett en sida långt dokument där fokus ligger på att få förståelse för användaren och dess främsta behov, utmärkande detealjer, info om personens intressen och annat som kan vara viktigt för att kunna utforma optimal design och vilka features som är viktiga att inkludera i produkten.
##### CARD
   Ett card är en fysisk eller digital "post-it" som används under planeringsfasen.
  Det fyller funktion som påminnelse för att hålla sig på banan och därför kunna möta personans behov.

Frågor att ställa sig: "Vem, vad och varför?"
 "As a **role** I want to **task** so that I can **goal**"


 Detaljnivå
: En stor story är en indikation på att den behöver brytas ner i mindre delar då riktlinjen för en "bra" story är att den ska kunna kodas och testas inom 1/2 dag - 2 veckor.
  Cards som går att utföra på en halv dag är fördelaktigt, då syns det även för produktägaren att projektet rör sig framåt och undivker osäkerhet eller frågor om varför det "står still" även när teamet jobbar för fullt.
 En story som innefattar två eller fler storys kallas en *epic*, då delas de helst (och oftast) upp i flera mindre delar. En epic -> tre mindre stories.

Konversation
: ????

Konfirmation
: I Planeringsfasen används baksidan av kortet för att hänvisa till acceptanstester.

Verksamhetstester och User Acceptance Test (UAT)
: Beställarens/kundens roll vid testning är att utvärdera produktens helhetsintryck. Det man tittar på är att systemet är logiskt användbart i verkligea livet och att avgöra huruvida deras användare kommer trivas med slutresultatet.

: Teamets roll i testningen är att se över och testa funktioner under projektets gång och bör göra det med fokus på hur produkten kommer användas. Målet är att allt ska gå smidigt när systemet/produkten väl är i drift.

: Detta görs löpande och kontinuerlig kommunikation med teamet/leverantören är väldigt viktigt för att undvika oväntade problem och slippa göra dubbelt jobb.
  

Scrum Poker
: "Estimera komplexiteten i utvecklingen"
 Att göra detta är momentet som programerare har svårast med, utöver sin kod. 
 Men man försöker avgöra komplexiteten i utförandet instället för att sätta det i ett perspektiv i tid. Då använder man sig av Storypoints på en skala 1-12 där 1 är lätt och 12 är svårt.
 En iteration får endast innehålla den mängd Story Points som teamet klarar av.
  Hur många poäng teamet klarade under föregående iteration blir teamet Velocity(score).

--- 






















#### KANBAN
Vad är Kanban?
: Kanban är en agil metod som fokuserar på att kontinuerligt optimera arbetet genom att effektivt hantera och visualisera arbetsflödet genom löpande uppdateringar och flerstegsfaser.

####Kanban board
En Kanban board är ett fysiskt eller digitalt hjälpmedel som visualliserar omfattningingen, statusen, flödet och processen av ett projekt. 

Det finns många sätt att strukturera en kanban board, beroende på projekt, detta är en generell beskrivning.

Det som beställaren har som "required features" skapar en backlog, där finns allt som projekten kommer att innehålla. 
Därefter läggs det antal stories/uppgifter/tasks som ska ske under denna iteration i en "input queue"(en to-do) som är redo att utvecklas.
Kommande stadie är flow, vilket är processen av utveckling. Där är uppgifterna WIP( work in progress) och faller under två kategorier, planerat arbete, så som en skapad uppgift från backlog, eller "firefighting" när någonting oväntat uppstår inom projektet. Ofta kan det vara något som andra uppgifter är beroende av och behöver då lösas omgående.
När uppgifterna är klara läggs dem i "done" för att bli dubbelcheckade. 
När dem blivit godkända blir dem markerade som "done done".

 ![Hur en Kanbanboard och dess flöde kan se ut.](img/pngtree-scrum-task-board-or-kanban-board-png-image_5976361.png)
---

Arbetsinnehåll:
: - Vad ska göras? 
: - Vad innebär uppgiften? Hur omfattande är den?
: - Definera vilken kategori uppgiften går under. Bugg, underhåll, byggande, helt ny tillagd feature? etc.

Priolista:
: - Vilken prioritering har uppgiften?
: - Hur tight är tidsramen? Är deadline nära?

Arbetsstatus:
: - Hur ligger det till med uppgiften just nu? status?
: - Är uppgiften påbörjad? Om ja, hur långt har man kommit?
: - Är uppgiften done eller done done?

Beroenden:
: - Väntar någon uppgift på att startas tills att denna är klar?
: - Är denna uppgift beroende av någon annan slutförs innan? 

Belastning:
: - Är belastningen jämnt fördelad inom teamet?
: - Hur många uppgifter har varje person?
: - Är någon överbelastad och behöver något omfördelas?

WIP :
: - Hur många tasks är igång samtidigt?
: - Finns det någon uttalad limit för WIP för att teamet eller systemet inte ska bli överbelastat? 

Genomloppstid:
: - Hur lång tid tar det för teamet från startgrop till målsnöre?
: - Finns det några "bottlenecks" på boarden som stoppar upp flödet och förlänger processen? Vad gör vi åt det?

Blockeringar:
: - Finns det något som blockerar arbetet och dess framsteg? Vad gör vi åt det?

Feedback:
: - Hur samlar vi in och dokumenterar feedback från alla parter? Kunder, samarbetspartners, kollegor osv.
: - Vad vad vi provat och vad funkade?

Kommunikation:
: - Hur kommunicerar teamet kring arbetet, dess framsteg och utmaningar?
: - Finns det nåfon rutin och schemalagda möten dör det ges utrymme för feedback?

Visualisering:
: - Används fysiska eller digitala boards för att ge en visuell överblick över arbetet och dess process?
: - Är detta tillgänlgigt och tydligt för alla i teamet?

Återkoppling:
: - Hur ofta sker återkoppling och analys inom teamet?
: - Hur ofta granskas prestanda?
: - Vad gör vi med den info vi samlar in? Vilka åtgärder vidtas?

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
### PJ 1.2 Icke-agila metoder
Icke-agila metoder är till skillnad från agila metoder mycket mer strukturerade, rigida i sitt arbetssätt och sättet att arbeta inom dem är mer homogent. Det är ett linjärt sätt att arbeta på där hela teamet steg för steg arbetar mot ett gemensamt mål.
Det kan tyckas låta svårt att arbeta så strikt, men det är väldigt fördelaktigt inom projekt där resultatet behöver vara totalt felfritt från deploy. 
Exempel på detta kan vara infrastruktur eller system inom vård, medicinsk utrustning, tungt maskineri, rymdfarkoster, banksystem, övervakningssystem eller annat som är säkerhetskänsligt.

En annan positiv aspekt av att arbeta icke-agilt är att det fullskaliga arbetet är kartlagt och att det är ytterst tydligt vilka förväntningar som finns på resultat och på teamet.

Det är fördelaktigt av många anledningar. Det ger klara och stabila krav, det ger hög säkerhet inför deployment, om det är särskilt viktigt för kunden att systemet uppfyller särskilda förväntningar och när projekten har flera komponenter som är komplext beroende av varandra kan det vara mer effektivt att arbeta linjärt då det öppnar för nogrann planering.

Baksidan av detta är just bristen på flexibilitet, det går t.ex. inte att implementera nya saker i mitten av ett projekt om en bättre lösning eller feature upptäcks.

Det är därför av yttersta vikt att ha mycket statistik och data när man ska jobba icke-agilt, för att undvika situationer av dubbelarbete. Det är endast tillåtet att gå tillbaka för justering när hela nuvarande arbetsfasen är avklarad, och det kan även i sig kräva mer arbetskraft, tid och pengar om produkten inte är upp till standard pga bristfälligt insamlad data.

Därför lämpar sig icke-agila metoder bäst för projekt där kraven är stabila och man inte kan förutse att det skulle ske ändringar under projektets gång.

--- 
#### Waterfall
Waterfall är en arbtesmetod som sker fas för fas i sekvens. 

Kravinsamling/Requirements:
: - Projektteamet arbetar tillsammans med en partner, produktägare eller intressent för att kartlägga och dokumentera krav inför kommande projekt. Man dokumenterar alla krav för projektet, funktionella som icke-funktionella.

Systemdesign:
: - Här utformas och designas strukturen och funktionaliteten för systemet i detalj. Då gör man en teknisk plan för hur allt ska fungera och dess komponenter, hur dem är sammankopplade och samverka, samt hur all data tar sig/flödar genom systemet teamet ska utveckla.

Implementering:
: - Med input från systemdesignen så skapas systemet först i små grupperingar (units) som senare ska komma att intregreras i nästa steg, varje unit genomgår tester för funktionalitet. Detta kallas "Unit testing".

Testning/Verification: 
: - Efter testningen så integreras alla units in i ett system. När allt blivit integrerat så testas systemet. Man letar då både efter funktionalitet och ickefunktionalitet.

Distribution/Deployment: 
: - När allt är klart, så blir systemet deployed i kundens miljö eller såld ut på marknaden.

Underhåll/Maintnence:
: - När det uppstår problem så försöker man lösa det och släpper sedan "patches" och bättre versioner av systemet. Att underhålla är att implementera detta i kundens miljö.

 ![Stegen inom waterfall.](img/waterfall-fancy.png)

--- 




## PJ 1.3 Entreprenörskap inom webbutveckling
<center> <h3>Inkomst</h3> </center>

##### Ta betalt per timme
Fördelar
: 1. Säkerställer att man blir rättvist kompenserad och får betalt för hela arbetet. Detta är väldigt positivt om projektet är oförutsägbart i sin complexitet.
   2. Det ger möjlighet för en utvecklare att vara flexibel i arbetet och att fakturera för alla delar inom projektet, även projektplanering och möten.

   3. Det ger kunden en tydlig överblick över hur mycket tid som går åt under olika uppgifter och hur mycket de olika sakerna kostar.

Nackdelar
: 1. Kunden kan tycka att det känns oroligt att anställa när de inte vet huruvida projektet oväntat kan komma att dra ut på tiden.
   2. Det kan innebära risk för att arbetet drar ut på tiden pga ekonomisk vinning och bekvämligheten att inte jobba under samma tidspress.

#### Ta betalt per projekt

Fördelar:
: 1. Ett fastställt pris gällande projektets total ger kunden väldigt tydliga ramar och trygghet, vilket ofta lockar kund. Särskilt om dem har en oflexibel budget.
  2. Motivationen att arbeta effektivt kan stiga när priset är fast då timtaxan blir "högre" ju kortare tid det tar.

Nackdelar:
: 1. Det kan vara riskabelt att sätta ett fast pris på ett komplext arbete, om det drar ut på tiden kan det innebära ojämn ersättning för det arbete som utförts.
1. Eftersom priset redan är satt så kan det vara svårt att omförhandla och leda till oenigheter om ytterligare ersättning.

<center> <h3>Utgifter</h3> </center>
Saker att tänka på innan man startar sin resa som entreprenör inom webbutveckling.

Startkapital
: Det behövs ett startkapital för att täcka minst de första månaderna av driftkostnad innan intäkter från kunder kan täcka dem. Det kan vara saker som kontorsplats, utrustning, licenser och annat.

Företagsform
: Det finns många olika företagsformer och det är klokt att komma fram till vilken typ av företag som passar det man vill erbjuda. 
   *Mer om det står nedan.*

Licenser och mjukvara:
:  Det är bra att undersöka vilka utvecklingsverktyg och licenser som behövs och eventuell månadskostnad för dem.

Hårdvara:
: Servrar, datorer och annat som behövs för t.ex. testning.

Kontor eller Co working space:
: Avgör om arbetet ska ske hemma, i ett co working space eller om det behövs budget för ett kontor.

Försäkringar: 
: Vilka försäkringar behöver tecknas? Se över företagsförsäkringar och ansvarsförsäkringar.
  
Marknadsföring
: Budgetera för marknadsföringskostnader.
  
Skatter och bokföring
: Förbereda ett stabilt bokföringssystem för att lätt kunna hantera skatter och deklarationer. 
  Om man inte vill bokföra själv kan man anlita en revisor, och då behöver även det räknas in i budget.

Kundrelationer och avtal
  : Budgetera för eventuella advokattjänster, avtal eller kundavtal.

  Eget arvode:
  : Ens egen lön, den ska icke glömmas. Kom ihåg att planera för den och så att den täcker dina livskostnader.

  Buffert:
  : Lägg undan en buffert för oförutsedda kostnader.

  Bokföring och ekonomisk planering:
  : Skapa ordentliga rutiner tidigt i processen för nogrann bokföring. Det hjälper med att hålla koll på utgifter och inkomster, var budgeten behöver utökas och var den kan skäras ner.


<center> <h3>De olika företagsformerna</h3> </center>

Enskild näringsverksamhet/enskild firma:
: En enskild näringsverksamhet är när man som ensam person äger och driver sitt företag med fullständigt ansvar och sitt eget personnummer istället för ett organisationsnummer. 
Då är det den enskilda personen som står på hyresavtal, kontrakt och är jurudiskt ansvarig och skyldig i t.ex. en domstolsprocess.
Det är viktigt att tänka på då företagets skulder också är dina privata skulder och därför bör man teckna en företagsförsäkring för att minska risken för ett sådant utfall.

: Som enskild firma behöver du ansöka för att bli godkänd för F-skatt och därmed även kunna registrera för moms. Om du vill ha anställda behöver du även registrera dig som arbetsgivare. Att registrera en enskild firma är gratis men det behövs ofta ett startkapital ändå för att sätta igång sin verksamhet.


Aktiebolag:
: I ett aktiebolag är delägarna inte personligen ansvariga för företagets skulder. Dock så krävs här, till skillnad från när man startar en enskild firma, ett kaptial på 25 000 kr, vilket benämns som *aktiekapital*.
Det motsvarar värdet på aktierna delägarna äger och agerar som kvitto på att dem faktiskt äger bolaget.

: Inom aktiebolag har man en styrelse på minst tre personer, om delägarna som då är styrelseledamöter är färre än tre så behövs en styrelsesuppleant.

: Det finns både privata och publika aktiebolag, och inom ett publik bolag så måste det sitta en vd, inom privata uppmuntras det, men krävs inte.

: Publika aktiebolag ska även ha en revisor som granskar bolagets ekonomi och därmed deras årsredovisning, medan privata bolag kan välja att inte ha en. Men när man har en revisor så lämnar bolaget in en *revisioinsberättelse* ihop med sin årsredovisning som visar på företagets förhållanden och förvaltning.

Handelsbolag/Kommanditbolag:
: Handelsbolag är i sig en juridisk person, vilket innebär att man kan ingå avtal i bolagets namn, och vem som får göra det avgör bolagsmännen. 
Dem är två eller flera delägare, och kan både vara privatpersoner eller företag.

: Inom ett handelsbolag finns ett solidariskt och juridiskt ansvar gentemot utomstående parter och detta går inte att avtala sig ifrån.
Det betyder att alla delägare är ansvariga med sin privata ekonomi inför företagets avtal och eventuella skulder. 
Om en person betalat någonting, medan de andra inte gjort det, så får hen kräva de andra delägarna/bolagsmännen på deras skuld till hen.

: Det av yttersta vikt att skriva ett kompanjonavtal inom ett handelsbolag, även om något är överenskommet muntligt.
Det finns inga strikta formella krav på avtalet, men dess syfte är att dokumentera hur ni ska fördela vinsten eller om någon vill köpas loss.

Kommanditbolag:
:  Ett kommanditbolag är en särskild förgrening inom handelsbolag och innebär att vissa bolagsmän(kommanditdelägare) har begränsat ansvar i relation till vad de har satsat i bolaget. En kommanditdelägarna har sällan någon juridisk rätt att bestämma om styret inom företaget, därmed måste det även finnas minst en person med obegränsat ansvar, som då benämns *komplementär*



Ekonomisk förening:
: En ekonomisk förening måste bestå av minst tre personer, juridiska som fysiska personer kan vara medlemmar. Alla betalar en medlemsinsats och får då rätt att tillsammans ta beslut inom föreningen och vilka grundläggande regler som gäller.
Summan behöver vara minst 1 kr men har ingen övre maxgräns.
Föreningen ska har fokus på att främja medlemmarnas ekonomiska intressen och ska fåå utbyte av att vara medlem. 
Det kan t.ex. vara förmåneliga priser på produkter på en butik eller en bostadrättsförening.


: En förening bestämmer var dem drar linjen för vilka medlemmar dem vill ha med och alla medlemmar ska på ett eller annat sätt delta i din ekonomiska verksamheten.
Det kan vara genom att använda tjänster föreningen erbjuder eller att köpa produkter inom en viss kedja. Medlemmarna är dock inte ansvariga för föreningern och riskerar därför inte mer än den medlemsavgift dem betalar för att få vara med.

: Något som är viktigt inom en ekonomisk förening är stadgar.
Det är föreningens grundläggande regler.


Ideell förening:
: Till skillnad från en ekonomisk förening så är en ideell förenings syfte inte att främja sina medlemmars ekonomiska intressen, dess syfte är istället att verka för medlemmarnas bästa på andra sätt. T.ex. med syfte att motverka orättvisa i samhället, lära medlemmarna en viss färdighet eller bidra till känsla av gemenskap mellan personer.

![Företagstyper](img/company-types.png)
---

## PJ 1.4 Issue distribution and handling in a group
###### Vad innebär det?
> Kort förklarat är det på vilka sätt man väljer att delegera, hantera och kommunicera kring uppgifter under ett projekt. 

<center> <h3>Github</h3> </center>
I en kontext där vi använder github så innebär Issue distribution att använda Github för att fördela och hantera ett arbete och låta teamet följa processen på ett enkelt sätt.

Det ger möjlighet att samarbeta, följa arbetets status och säkerställa att inget glömt bort att genomföras. 

Detta gör man genom att skapa en *issue*, vilket är en arbetsuppgift.
Detta kan göras på flera sätt och en väljer själv det som passar en själv och ens *workflow*.

 > När en *issue* nämns i en annan *issue* eller *pull  request* så syns dess tidslinje och tidigare arbete. 
 Varje *issue* har en en uppsättning information. Där ingår en label, uppgiftsbeskrivning, namn på ansvarig person, var denna issue ligger på priolistan och eventuell annat material som behövs för att utföra uppgiften. T.ex. bilder och filer.

Genom att skapa *projects* så går det att organisera och göra en priolista över sina *issues*.
För att kategorisera relaterade *issues* används *labels* och *milestones* 
För att spåra en *issue* inuti större *issues* anväds *task lists*. Detta är fördelaktigt då det bör undvikas att delegera för stora uppgifter och då är det bättre att bryta ner dem.
Det går även att skapa *actions* för att automatisera uppgifterna i sitt arbete genom att skapa ett *workflow*.
Det går både att ställa in så att ens worklflow agerar enligt ett schema eller reagerar på events, så som att skapas en issue, en kommentar skrivs eller en kedjereaktion 

När pullrequests sedan mergas så försvinner dess issues per automatik.

För att skicka en notis till/nämna en i teamet så använder man @mention.
Då kan man även länka en *issue* till nämnda teammedlem med *"#"*
På detta sätt kan du tilldela *issues* till teamet.

##### Steg inom Github Issue Distribution
1.  Skapa issues
2. Tilldela issues
3. Använda labels
4. Tilldela milestones
5. Använda project
6. Kommunicera och följa upp
7. Använda automatisering/actions
8. Prioritera issues
9. Stäng issues
10. Följ upp

#####Olika typer av discussions:

Github Issues
: - Är kopplat till *endast* ett specifikt repo och har oftast en specifik ägare.
: - Bra att kommunicera detaljer så som att rapportera buggar eller förbättringar.
: - Bra lämpat för att spåra tasks, buggar och förbättringar. Bra lämpat för feedback kring en specifik feature eller göra en bugg-rapport.

Pull request
: - Är också kopplat till *endast* ett repo.
: - Tillåter dig att kommentera på ändringsförslag från andra.
: - Tillåter dig att göra egna förslag på ändringar. 
: - Bra lämpat för att fixa ett typo eller ändra i ett repo, fixa en issue eller kommentera på andras förslag.

Github Discussion
: - Sträcker sig över *flertal* repositories.
: - Detta går att likna vid ett forum/kommentarsfält som passar bra där det behövs mycket samarbete som sker utanför kodbasen. Det ger möjligheter till att bolla idéer och utbyta kunskap och perspektiv.
: - Detta forum har sällan en tydlig ägare.
: - Lämpat för mer generella ämnen som inte är kopplade till specifika filer i repot.


Så, att förstå och kunna använda Github issue distribution är en kritisk del i projektledning för att hålla ordning på allt som sker parallelt.
Att kunna skapa, fördela, hålla koll på uppgifter och kommunicera med teamet på ett och samma ställe. Genom att använda labels och milestones är det lättare att prioritera och planera hela teamets arbete. 
Och genom att detta dessutom möjliggör automatisering och feedback via @mentions gör detta till en väldigt användbart verktyg för att få projektet att smidigt röra sig framåt.


> 	***Referenser:***
[- Shareitsolutions](https://www.shareitsolutions.com/blog/agile-non-agile/)
[- Codeop](https://codeop.tech/what-exactly-is-not-agile/)
[- Onbird](https://onbird.se/grunderna-i-scrum/?utm_term=&utm_campaign=I+-+Performance+Max+-+Konsult&utm_source=adwords&utm_medium=ppc&hsa_acc=5250760349&hsa_cam=19864017095&hsa_grp=&hsa_ad=&hsa_src=x&hsa_tgt=&hsa_kw=&hsa_mt=&hsa_net=adwords&hsa_ver=3&gad=1&gclid=Cj0KCQjwpompBhDZARIsAFD_Fp9ypqe75C9pRfBT-tiTinJcUAWPTIwUnKZaN4DUtQNbfMWEcVILV5AaAnfuEALw_wcB)
[-Projektforum](https://projektforum.se/scrum-2/)
[-Nulab](https://nulab.com/learn/project-management/kanban-guide/)
[-F8 Lunds tekniska högskola](https://fileadmin.cs.lth.se/cs/Education/EDAF45/2017/lectures/F08-2017.pdf)
[-Verksamt-företagsform](https://www.verksamt.se/fundera/valj-foretagsform)
[-Verksamt-räkna pris](https://www.verksamt.se/alla-e-tjanster/rakna-ut/rakna-ut-ditt-pris)
[-Uptech Team](https://www.uptech.team/blog/software-development-costs)
[-Standardbolag](https://www.standardbolag.se/information/valj-ratt-foretagsform?gclid=Cj0KCQjwm66pBhDQARIsALIR2zBXh2cufsBodrzE_vFoQhan6q6nYxoAt54i3zdnNwk6rr0ObNqj-5kaAvLZEALw_wcB)
[Github-issue distribution](https://docs.github.com/en/issues/tracking-your-work-with-issues/about-issues)
-Kursmaterial-föreläsningar
[Github-Quickstart](https://docs.github.com/en/get-started/quickstart/communicating-on-github#pull-requests)