# Teorihandboken - Programmeringsmetodik (PG)
Studerande: Emma Jensen

## PG 1.1 Versionshantering (Git)
Att versionshatera innebär att använda ett system som ordnar och håller reda på ändringar i en fil eller i en mapp / samling filer och mappar över tid. Detta gör att de sparade versionerna går att återkalla senare för att kunna återställa, ändra eller felsöka i just den versionen.

#### GIT
Git är ett versionshanteringssystem som spårar sparade ändringar i källkod under utvecklingens gång och gör det möjligt för flera utvecklare att arbeta tillsammans på samma projekt utan att störa varandras arbete men även för en ensam utvecklare att hålla reda på sina ändringar och möjligöra att testa att utveckla och modifiera features i arbetet utan att ta sönder det som redan fungerar. 

Ett par exempel på de absolut mest grundläggande git kommandon är **git init** i en mapp för att initiera att den mappen blir ett nytt lokalt repository, **git add** för att lägga till ändrade filer (*stagea*) inför att spara filen i repot, **git commit** sparar ändringarna i ditt lokala repo.


````
# Initiera ett nytt Git-repository
git init
````

````
# Lägg till en fil i staging-området
git add minTeorihandbok.txt
````

````
# Committa ändringar med ett meddelande
git commit -m "Lade minTeorihandbok.txt"
````
````
# Visa status för lokala ändringar
git status
````
````
# Visa loggen över commits
git log
````
````
# Stasha dina ändringar
git stash
````
````
# Poppa dina stashade ändringar
git stash pop
````




#### Varför använder vi git?
Det gör vi för att förbättra samarbetet och minimera riskerna att förstöra vårt eget eller andras arbete, samt för att säkerställa versionskontroll och förenkla arbetsflödet genom det. 

Ett par kommandon som används mycket i sammarbeten och som jag själv upplever har använts mycket under våra gruppprojekt är:

````
# Klona ett repository
git clone <repository-url>
````
````
# Fetch senaste ändringarna från remote
git fetch origin
````
````
# Pull de senaste ändringarna och slå ihop dem
git pull origin feature-branch
````
````
# Merge en annan branch in i din nuvarande branch
git merge annan-branch
````
````
# Aborta en pågående merge (om något går fel)
git merge --abort
````
````
# Rebase din branch på toppen av en annan branch
git rebase master
````
````
# Abort en pågående rebase
git rebase --abort
````
````
# Fortsätt en pågående rebase efter att ha löst konflikter
git rebase --continue
````

Jag upplevde att vissa av dessa kommandon kändes snarlika varandra tills att jag insåg konsekvenserna av hur jag använder dem. 

| **Kommando** | **Beskrivning**                                                                           | **Fördelar**                                                                                                                                                    | **Nackdelar**                                                                                                                                                                                                                                                                           |
| ------------ | ----------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Pull**     | Hämtar de senaste ändringarna från remote och slår samman dem med din nuvarande branch.   | - Enkel att använda och kombinerar två steg i ett kommando.                                                                                                     | - Kan skapa problem om det uppstår konflikter, eftersom ändringarna slås ihop direkt efter hämtning. Eftersom pull automatiskt gör en merge efter att ha hämtat ändringarna, tvingas du lösa konflikter omedelbart, vilket kan vara besvärligt om du inte är förberedd.                 |
| **Fetch**    | Hämtar de senaste ändringarna från remote utan att slå ihop dem med din nuvarande branch. | - Ger dig kontroll över när och hur du vill slå ihop ändringarna.<br>- Minskar risken för konflikter genom att låta dig se ändringarna innan du integrerar dem. | - Kräver ett extra steg för att integrera de hämtade ändringarna. Efter att ha använt fetch måste du manuellt slå ihop dem med din lokala branch genom att köra antingen **merge** eller **rebase**, vilket kan vara mindre effektivt och kräver mer arbete.                            |
| **Merge**    | Slår ihop ändringar från en branch till en annan och skapar en merge-commit.              | - Bevarar hela historiken och visar tydligt när en branch har blivit mergead.<br>- Enkel och säker metod för att slå ihop arbete från olika branches.           | - Detta kan leda till en komplex och otydlig commit-historik, eftersom varje merge skapar en extra commit. Historiken kan bli svår att läsa med många merge-commits och förgreningar, vilket kan orsaka förvirring och göra det svårt att spåra ändringar.                              |
| **Rebase**   | Flyttar eller kombinerar commits till en ny bascommit.                                    | - Ren och linjär commit-historik.<br>- Ingen merge-commit skapas, vilket gör historiken lättare att följa.                                                      | - Eftersom rebase omskriver commit-historiken, kan det skapa problem vid delade branches genom att ändra commits som andra utvecklare arbetar med, vilket leder till förvirring och felaktig historik. Detta gör rebase mindre lämpligt för branches som delas mellan flera utvecklare. |

---
## PG 1.2 Benchmarking
Benchmarking är processen av att mäta och utvärdera prestandan av en programvara. Detta gör man genom standardiserade tester som kan inkludera att mäta svarstid, minnesanvändning, genomströmmning, uppstartstid och failovertid, men även många andra viktiga mått. 
>**Svarstid** (*Latency*): Tiden det tar för systemet att svara på en förfrågan.
>**Genomströmning** (*Throughput*): Antalet förfrågningar eller transaktioner systemet kan hantera per tidsenhet
>**Minnesanvändning** (*memory usage*): Mängden minne som används av systemet under olika belastningar.
>**Failover-tid** (*failover time*): Tiden det tar för systemet att starta upp och bli operativt.

Andra mått är: *CPU usage, disk I/O, network latency, error rate, maximum concurrent users, startup time, garbage collection, thread usage, queue length, bandwidth usage, cache-hit ratio, energy or power consumption, response time under load, failover time, and throughput per process.*

#### Hur och varför?
Benchmarking utförs genom att köra specifika testscenarion och sedan samla in data, denna analyseras i tur för att identifiera *bottle necks* och då kunna optimera systmet som testas. 

Det är en viktig del av att utveckla applikationer för att säkerställa att prestandakraven och belsatningsnivå matchar förväntningarna för appen. Genom att göra detta regelbundet genom utvecklingen så ger vi oss själva chans att upptäcka och identifiera eventuella problem innan användarna gör det och blir påverkade. 

#### Verktyg för benchmarking

#### Frontend

**Lighthouse** är ett open-source verktyg från Google som hjälper utvecklare att förbättra kvaliteten på webbsidor. Det kan köras mot vilken webbsida som helst, offentlig eller kräver autentisering, och ger insikter om prestanda, tillgänglighet, bästa praxis och SEO.

**GTmetrix** är ett annat verktyg för att analysera webbprestanda. Det kombinerar data från Google Lighthouse och andra källor för att ge en detaljerad analys av webbplatsens hastighet och förslag på förbättringar.

#### Backend
**Apache JMeter** är ett populärt verktyg för att utföra belastningstester på webbapplikationer. Det kan simulera ett stort antal användare som gör förfrågningar till en server och ger inblick om svarstider, fel och serverprestanda.

___

## PG 1.3 Testdriven utveckling
Testdriven utveckling är en metodik som fokuserar på skriva tester före implementering av funktionalitet.
   Därmed definieras varje funktionalitet genom tester som initialt misslyckas, därefter utvecklas funktionen för att klara testet.

Ett enhetstest för en specifik funktion eller förbättring, som ej finns än, skrivs av en utvecklare, testet körs och förväntas misslyckas då funktionliteten inte finns tillgänlig för testet.
 Sedan implementeras funktionen för att passera testet. När testet passerar och funktionen beter sig som väntat så refaktoreras koden vid behov för att förbättra kodstrukturen. 

Detta tillvägagångssätt gör att vi kan säkerställa att varje enkild funktion beter sig som förväntat.

#### Hur TDD?
TDD-processen kan sammanfattas i tre steg, ofta kallade "Red-Green-Refactor":

**Red:** Skriv ett enhetstest som misslyckas eftersom funktionen ännu inte är implementerad.
**Green:** Implementera den minsta mängd kod som behövs för att passera testet.
**Refactor:** Förbättra koden utan att ändra dess beteende, säkerställ att alla tester fortfarande passerar.
#### Jest
Jest är ett testverktyg för JavaScript och TypeScript, utvecklat av Facebook. Det används för att skriva enhetstester och integrera tester för att säkerställa kodkvalitet med hjälp av funktioner som snapshot-testning, parallell körning av tester och inbyggd support för mockning av moduler

Exempel på test Jest för Javascript:

*En funktion som förväntas korrekt utföra matematisk addition och ge korrekt resultat.*
```js
const { add } = require('./calculator');

test('adds 2 + 3 to equal 5', () => {
    expect(add(2, 3)).toBe(5);
});

test('adds -1 + 1 to equal 0', () => {
    expect(add(-1, 1)).toBe(0);
});

test('adds 0 + 0 to equal 0', () => {
    expect(add(0, 0)).toBe(0);
});

test('adds -2 + -3 to equal -5', () => {
    expect(add(-2, -3)).toBe(-5);
});


```
<br>

*Detta test kommer att misslyckas eftersom funktionen 'add' ännu inte är definierad.*



```js
function add(a, b) {
    return a + b;
}

module.exports = { add };


```
<br>

*Här har koden skrivits som förväntas passera testet ovan*


```js
function add(a, b) {
    return a + b;
}

module.exports = { add };
```

___

## PG 1.4 Deploy och staging
**Deploying** innebär att föra över applikationen från utvecklingsmiljön till produktionsmiljön, där den blir tillgänglig för användare.Denna process är avgörande för att säkerställa att applikationen fungerar korrekt och pålitligt under verkliga förhållanden.

Processen involverar att bygga applikationen, köra tester, och sedan flytta den till produktionsservrar.

**Staging** är en mellanliggande miljö där applikationen testas innan den deployas till produktion. Stagingmiljön, som speglar produktionsmiljön, används för att simulera hur applikationen kommer att bete sig i produktion. Detta inkluderar att köra applikationen med samma databaser, konfigurationer och tjänster som i produktionsmiljön.

Genom att utföra sista minuten-testning i stagingmiljön kan buggar eller andra problem identifieras och åtgärdas innan de når användarna. Detta hjälper till att förebygga driftstopp och andra oväntade problem som kan påverka användarna i produktion.

Det är viktigt att följa best practices vid deployment, inklusive användning av versionskontroll, kontinuerlig integration och kontinuerlig leverans (*CI/CD*), samt ha dokumenterade rollback-strategier på plats ifall något går fel. En väl utförd deployment bidrar till en smidigare och säkrare övergång till produktion, vilket resulterar i en bättre användarupplevelse och minskad stress för utvecklarna.

#### Continuous Deployment
Continuous Deployment innebär att alla kodändringar som passerar automatiserade tester omedelbart deployas till produktion. Detta minskar tiden mellan utveckling och leverans till användare, men kräver starka tester och övervakning för att undvika att buggar når produktionen.

Continuous Integration *(CI)* och Continuous Delivery/Deployment *(CD)* är metodologier som automatiserar stegen i mjukvaruutveckling för att möjliggöra snabbare och pålitligare leveranser.
| **Term**                        | **Beskrivning**                                                                                             | **Fördelar**                                                                                               |
| ------------------------------- | ----------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------- |
| **Continuous Integration (CI)** | Utvecklare sammanfogar kod regelbundet. Automatiserade bygg- och testprocesser körs för varje integration.  | Tidig felupptäckt, förbättrad kodkvalitet, minskad risk för integrationsproblem                            |
| **Continuous Delivery (CD)**    | Kod är alltid i releasbart tillstånd efter tester och byggprocesser. Deployment till produktion är manuell. | Snabbare och pålitligare releaser, minskad risk för fel vid release, flexibilitet att släppa när som helst |
| **Continuous Deployment (CD)**  | Utökning av Continuous Delivery där kod automatiskt deployas till produktion efter godkända tester.         | Omedelbar leverans av uppdateringar, snabbare feedback från användare, ökad releasefrekvens                |


#### Rollback Strategier
Rollback-strategier är metoder för att återställa en tidigare stabil version av en applikation om en ny release orsakar problem. Vanliga strategier inkluderar *blue-green deployment* och *canary releases*.

#### <span style="color:CornflowerBlue">B</span>lue-<span style="color:MediumSeaGreen">G</span>reen Deployment
Blue-green deployment innebär att ha två identiska miljöer, en är <span style="color:CornflowerBlue">blue</span> och en <span style="color:MediumSeaGreen">green</span>. Uppdateringar deployas till <span style="color:MediumSeaGreen"> green</span> medan <span style="color:CornflowerBlue">blue</span> hanterar trafiken. 

#### Canary Releases
Canary releases innebär att löpande rulla ut nya funktioner till en liten del av användarna innan de når alla. Detta gör det möjligt att upptäcka och åtgärda problem i en kontrollerad miljö utan att påverka alla användare samtidigt.

___

## PG 1.5 Debugging
 Debugging är processen att hitta och fixa buggar i programvaran.
 Buggar kan vara allt från syntaxfel till logiska fel som orsakar oväntade beteenden i applikationen.
 Detta kan ske manuellt eller med hjälp av verktyg som integrerade utvecklingsmiljöer *(IDEs)*, debugger- och loggningsverktyg. 

 Vanligtvis innefattar debugging dessa steg:

 - *Identifiera* att buggen existerar genom att antingen observera oväntat beteende eller få ett felmeddelande/error.

 - *Reproducera* buggen genom att återskapa en situation är buggen visar sig konsekvent för att förstå kontexten kring varför detta uppstår.

 - *Analysera* koden genom att använda debugger-verktyg för att steg för steg genom koden inspektera syntax, radavstånd och tillstånd.

 - *Fixa* buggen genom att modifiera koden att bete sig som vi väntar oss.

 - *Verifiera* genom att testa koden och därmed säkerställa att buggen är fixad och att dessa ändringar inte skapat ytterligare buggar. 
  

#### Varför?
Debugging används främst för att vi inte lyckas implementera den funktionalitet som fungerar som förväntat och behöver då lösa detta. 

Att löpande och systematiskt identifiera och fixa buggar när dem uppstår bidrar även till att koden är stabil och fungerar korrekt. 
Det effektiviserar utvecklingen då det hjälper med att identifiera och åtgärda problem snabbt vilket kan ta lång tid att åtgärda när det finns flera buggar än en och det då är svårare att identifiera orsaken och åtgärda problemet. 

Utöver detta så leder en buggfri applikation till att användarupplevelsen blir bättre, att användarna är nöjda i högre grad och att supportärenden till följd av det blir färre.
Då behöver även utvecklarna inte störa arbetsflödet för "fire fighting" i efterhand med funktionalitet de trodde var avklarad. Debugging bidrar därmed till en mer effektiv utvecklingsprocess och en mer robust slutprodukt.

#### Debugger Verktyg

**Google Chrome DevTools** är ett inbyggt debugger-verktyg i Google Chrome som erbjuder många verktyg för att bland annat debugga, inspektera nätverkstrafik, analysera och optimera prestanda. DevTools används främst för frontend då verktyget är väl utvecklat för att felsöka HTML, CSS och JavaScript direkt i webbläsaren i realtid.


Något jag finner oerhört hjälpsamt är att DevTools inkluderar ett verktyg för nätverksinspektion som visar alla förfrågningar och svar, vilket gör det möjligt att se vad som händer bakom kulisserna i realtid och kunna identifiera oväntat beteende. Detta är särskilt användbart för att felsöka API-anrop och laddningstider.
De verktyg jag använder oftast är *console* samt *elements panel* +  *inspect* för att inspektera och redigera i *DOM-träd* och *CSS*.
<img src="/Img/Skärmavbild 2024-07-27 kl. 17.40.54.png" alt="exempel på att skapa element i  DevTools console">


**VS Code Debugger - Node.js**
Visual Studio Code stödjer debugging för många fler språk än bara JavaScript, Python och språk som transpileras till JavaScript. Verktyget kan också debuggera språk som C#, Java, Ruby, PHP, Go och många fler, beroende på installerade tillägg.
Den inbyggda terminalen och möjligheten att ansluta till fjärrservrar gör felsökning på olika miljöer smidig.

Två funktioner jag vill lära mig att använda mer är *call stack inspection*, som visar den aktuella platsen i koden och vilka funktioner som anropats fram till denna punkt, samt *watch expression* som gör att man kan välja vissa variabler eller uttryck i koden och kontinuerligt se deras aktuella värden under körning.
Med det hoppas jag kunna identifiera och åtgärda problem i koden snabbare, effektivisera processen och höja kvaliteten på den slutliga applikationen.

[- Chrome DevTools DOM | Google](https://developer.chrome.com/docs/devtools/dom)
[- Chrome DevTools CSS | Google](https://developer.chrome.com/docs/devtools/css)
[- Debugging | Visual Studio Code](https://code.visualstudio.com/docs/editor/debugging)
[- Debugging | Node.js](https://nodejs.org/en/learn/getting-started/debugging)

___

## PG 1.6 Dokumentation
Dokumentation är en av de mest kritiska aspekterna av webbutveckling och programmering och fungerar som en detaljerad guide och referens för utvecklare, användare och andra intressenter.
Dokumentation säkerställer att alla som är involverade i ett projekt kan förstå hur programvaran fungerar, hur den ska användas, och hur den kan underhållas och utvecklas vidare.

#### Vad är Dokumentation inom webbutveckling?
Inom programmering och webbutveckling avser den skriftliga och ibland visuella information som beskriver aspekter av ett program eller en applikation.
Den inkluderar detaljer om kodens struktur, funktionalitet, användningssätt, och underhåll. 

Dokumentation kan skapas under utvecklingsprocessen eller efter att en viss del av projektet är slutförd och kan dokumenteras. 

Det finns två huvudsakliga typer av dokumentation: *intern* och *extern*.

#### Intern Dokumentation
**Intern dokumentation** riktar sig till utvecklare och andra tekniska teammedlemmar. 
Den kan inkludera:

***Kodkommentarer*** är korta beskrivningar i själva kodfilen som förklarar vad specifika delar av koden gör. Kommentarer hjälper utvecklare att snabbt förstå och navigera genom koden, det är dock viktigt att inte dokumentera för mycket i koden då det kan göra den svårläst.

***ReadMe-filer*** finns vanligtvis i projektets root och ger en översikt över projektet, hur man installerar och använder det, samt annan relevant information.

***API-dokumentation*** beskriver detaljerat funktioner, metoder och klasser i ett API *(Application Programming Interface)*. API-dokumentation är avgörande för utvecklare som behöver integrera eller använda APIs.

***Tekniska specifikationer*** är dokument som innehåller detaljerad information om arkitektur, databasmodeller, flödesdiagram och andra tekniska aspekter av projektet.

#### Extern dokumentation
***Extern dokumentation*** riktar sig till slutanvändare och icke-tekniska intressenter. Den kan inkludera:

***Användarhandböcker*** guidar och hjälper användare att förstå hur man använder applikationen. De kan innehålla steg-för-steg-instruktioner, skärmbilder och problemlösningstips.

***Installationsguider*** instruerar användare att installera programvaran på sina system. De kan inkludera systemkrav, installationssteg och konfigurationsanvisningar.

***FAQ*** (Frequently Asked Questions) är en samling av vanliga frågor och svar som hjälper användare att snabbt hitta lösningar på vanliga problem.

***Utbildningsmaterial*** som kan inkludera tutorials, videor och annan pedagogisk information som hjälper användare att ta till sig information och lära sig använda programvaran effektivt.

## PG 1.7 Struktur av kod i projekt
Beskriv rubriken här

## PG 1.8 Automatisering av arbetsflöde
Beskriv rubriken här

## PG 1.9 Virtualisering av utvecklingsmiljö
Beskriv rubriken här

## PG 1.10 Bundeling-verktyg
Beskriv rubriken här

## PG 1.11 Terminalinterface
Beskriv rubriken här

