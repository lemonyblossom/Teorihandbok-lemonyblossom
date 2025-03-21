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

[- Git, What is it? | atlassian.com](https://www.atlassian.com/git/tutorials/what-is-git)
[- Git guide | github.blog ](https://github.blog/developer-skills/programming-languages-and-frameworks/what-is-git-our-beginners-guide-to-version-control/)

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

[- Lighthouse](https://developer.chrome.com/docs/lighthouse)
[- Apache jmetertm](https://jmeter.apache.org/)
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
[- Testdriven utveckling | consid](https://www.consid.com/sv/insikter/artiklar/testdriven-utveckling-skriv-test-forst-och-kod-sen-med-tdd-metoden/)
[- OOP | geeksforgeeks](https://www.consid.com/sv/insikter/artiklar/testdriven-utveckling-skriv-test-forst-och-kod-sen-med-tdd-metoden/)
[- Jest | jestjs.io](https://jestjs.io/)
[- Jest test example inspo](https://medium.com/@dirussogaetano/unit-tests-javascript-jest-4f792124e136)
___

## PG 1.4 Deploy och staging
**Deploying** innebär att föra över applikationen från utvecklingsmiljön till produktionsmiljön, där den blir tillgänglig för användare. Denna process är avgörande för att säkerställa att applikationen fungerar korrekt och pålitligt under verkliga förhållanden.

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

[- CI/CD | limetta.se](https://limetta.se/tips-metoder-for-digitala-projekt/Vad-ar-CI-CD--Continuous-Integration-och-Delivery/)
[- CI/CD | gitlab](https://about.gitlab.com/topics/ci-cd/)
[- Deployment strategies | harness.io](https://www.harness.io/blog/blue-green-canary-deployment-strategies)
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
Visual Studio Code stödjer debugging för många fler språk än bara JavaScript, Python och språk som transpileras till JavaScript. Verktyget kan också debuggera språk som C#, Java, Ruby, PHP och många fler, beroende på installerade tillägg.
Den inbyggda terminalen och möjligheten att ansluta till fjärrservrar gör felsökning på olika miljöer smidig.

Två funktioner jag vill lära mig att använda mer är *call stack inspection*, som visar den aktuella platsen i koden och vilka funktioner som anropats fram till denna punkt, samt *watch expression* som gör att man kan välja vissa variabler eller uttryck i koden och kontinuerligt se deras aktuella värden under körning.
Med det hoppas jag kunna identifiera och åtgärda problem i koden snabbare, effektivisera processen och höja kvaliteten på den slutliga applikationen.

[- Chrome DevTools DOM | Google](https://developer.chrome.com/docs/devtools/dom)
[- Chrome DevTools CSS | Google](https://developer.chrome.com/docs/devtools/css)
[- Debugging | Visual Studio Code](https://code.visualstudio.com/docs/editor/debugging)
[- Debugging | Node.js](https://nodejs.org/en/learn/getting-started/debugging)
[- debugging in software engineering | geeksforgeeks](https://www.geeksforgeeks.org/software-engineering-debugging/)

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

[- Documentation types | altexsoft.com](https://www.altexsoft.com/blog/technical-documentation-in-software-development-types-best-practices-and-tools/)
[- External docs  document360.com](https://document360.com/blog/external-documentation/)
[- Importance of Documentation | edu.edu](http://www.cs.ecu.edu/karl/3300/spr16/Notes/Documentation/documentation.html)

---
## PG 1.7 Struktur av kod i projekt

Genom att följa etablerade programmeringsmetodiker, använda designmönster, CI/CD-processer, versionshanteringssystem och kodstandarder, kan utvecklingsteam skapa en kodbas som är lätt att förstå, underhålla och vidareutveckla. 
En välstrukturerad kodbas är lättare att förstå, underhålla och vidareutveckla, vilket sparar tid och minskar risken för fel.


En av de grundläggande principerna för att strukturera kod är att dela upp funktionalitet i separata moduler. Moduler är självständiga enheter som ansvarar för en specifik del av applikationens funktionalitet, vilket är centralt i metodiker som modulär programmering och *object-oriented programming (OOP)*.

***I modulär programmering*** delas koden in i små, återanvändbara delar. Varje modul har ett tydligt definierat ansvar, vilket gör det enkelt att förstå vad modulen gör och hur den kan användas i olika delar av projektet. *OOP* tar detta ett steg vidare genom att organisera kod i klasser och objekt, vilket möjliggör inkapsling, arv och polymorfism.
Detta gör att relaterade funktioner och data grupperas tillsammans och bidra till att koden blir mer logiskt strukturerad och lättare att följa. 

```js
// auth.js - Modul för user auth
export function login(username, password) {
  return (username === "user" && password === "pass");
}

// session.js - Modul för sessionshantering
let currentUser = null;

export function setSession(user) {
  currentUser = user;
}

export function getSession() {
  return currentUser;
}

// main.js - entry point som importerar och använder modulerna
import { login } from './auth.js';
import { setSession, getSession } from './session.js';

const username = "user";
const password = "pass";

if (login(username, password)) {
  setSession(username);
  console.log("User logged in:", getSession());
} else {
  console.log("Invalid credentials");
}

```

***Objektorienterad Programmering (OOP)*** är en metodik som organiserar programvaran runt objekt, vilket hjälper till att skapa en tydlig och strukturerad kodbas. OOP använder sig av klasser och objekt för att representera data och funktionalitet.
> ***Inkapsling:*** Detta innebär att samla data och metoder som manipulerar denna data inom samma enhet, eller klass.

> ***Arv*** tillåter en klass att ärva egenskaper och metoder från en annan klass. Detta främjar återanvändbarhet och kan minska duplicering av kod. Genom att använda arv kan utvecklare skapa nya klasser baserade på befintliga, vilket gör koden mer flexibel och skalbar.
> 
> Arv bör användas när det finns en klar "is-a" relation mellan bas- och underklassen, som när en *Roman* är en typ av *Bok*.
Däremot bör arv undvikas när relationen inte är en "is-a" relation eller när det kan leda till tight koppling, som när en *Roman* har en *Författare* och därför har en "has-a" relation.

Exempel på ***"is-a"*** relation
```ts
// Bok.ts
class Bok {
    titel: string;

    constructor(titel: string) {
        this.titel = titel;
    }

    läs(): void {
        console.log(`Läser boken: ${this.titel}`);
    }
}

// Roman.ts
class Roman extends Bok {
    genre: string;

    constructor(titel: string, genre: string) {
        super(titel);
        this.genre = genre;
    }

    läs(): void {
        console.log(`Läser romanen: ${this.titel}, Genre: ${this.genre}`);
    }
}

const minRoman = new Roman("Utvandrarna", "Klassiker");
minRoman.läs();  // Output: Läser romanen: Utvandrarna, Genre: Klassiker
```

Exempel på ***"has-a"*** relatioin
```ts
// Författare.ts
class Författare {
    namn: string;

    constructor(namn: string) {
        this.namn = namn;
    }

    skrivBok(): void {
        console.log(`${this.namn} skriver en ny bok.`);
    }
}

// Roman.ts
class Roman {
    titel: string;
    författare: Författare;

    constructor(titel: string, författare: Författare) {
        this.titel = titel;
        this.författare = författare;
    }

    läs(): void {
        console.log(`Läser romanen: ${this.titel} av ${this.författare.namn}`);
    }
}


const minFörfattare = new Författare("Vilhelm Moberg");
const minRoman = new Roman("Utvandrarna", minFörfattare);
minRoman.läs();  // Output: Läser romanen: Utvandrarna av Vilhelm Moberg
minFörfattare.skrivBok();  // Output: Vilhelm Moberg skriver en ny bok.
```


> ***Polymorfism*** gör det möjligt för objekt att behandlas som exempel på deras bas-klass snarare än deras faktiska klass. Detta förenklar interaktionen mellan olika klasser och objekt, vilket gör koden mer dynamisk och anpassningsbar.

> ***Abstraktion*** innebär att exponera endast nödvändiga detaljer och dölja implementeringsdetaljer. Genom att använda abstrakta klasser och gränssnitt kan utvecklare definiera gemensamma egenskaper och beteenden utan att avslöja komplexa implementationer

[- Modular programmering | tiny.cloud](https://www.tiny.cloud/blog/modular-programming-principle/)
[- Polymorphism vs Inheritance | shiksha.com](https://www.shiksha.com/online-courses/articles/difference-between-inheritance-and-polymorphism-blogId-153349)
[- Inheritance vs Abstraktion in OOP | medium.com](https://medium.com/nerd-for-tech/exploring-inheritance-and-abstraction-in-object-oriented-programming-1b23b68b1736)

---

## PG 1.8 Automatisering av arbetsflöde
Inom programmering och webbutveckling innebär detta att man skapar processer som automatiserar repetitiva och tidskrävande uppgifter. Detta kan omfatta allt från kodgranskning och testning till deployment och övervakning. Automatisering hjälper utvecklare att fokusera på mer komplexa och kreativa aspekter av utvecklingen, minskar risken för mänskliga fel, sparar tid och ökar därmed effektiviteten.
Automatisering kan tillämpas på flera delar av utvecklingsprocessen, inklusive bygg, testning och kodgranskning.

Genom att automatisera byggprocessen kan utvecklare skapa skript som sammanställer och optimerar JavaScript, CSS och andra resurser.
Till exempel kan man konfigurera en byggprocess som automatiskt minifierar och sammanfogar filer varje gång en ändring görs för att förbättra laddningstiden.

Testautomatisering är en annan viktig del av arbetsflödet där utvecklaren skapar och kör automatiserade tester för att snabbt identifiera buggar och säkerställa att nya ändringar inte påverkar befintlig funktionalitet. 
Dessa kan vara enhetstester, integrationstester och end-to-end-tester som körs varje gång ny kod checkas in i versionskontrollsystemet. Detta gör att eventuella felaktigheter eller buggar identifieras omedelbart efter en ändring, vilket minskar risken för att problem går obemärkt förbi och påverkar produktionen.

Automatisering kan också tillämpas på infrastrukturella uppgifter. Genom att använda skript för att konfigurera och hantera servrar kan utvecklare skapa konsekventa och reproducerbara miljöer. Till exempel kan man automatisera installationen av program och konfigureringen av tjänster, vilket minskar risken för konfigurationsfel och ser till att alla miljöer är identiska.

En annan aspekt av arbetsflödesautomatisering är hantering av kodgranskningar. Genom att använda automatiserade verktyg kan kodgranskningar genomföras snabbt och effektivt, vilket säkerställer att kodstandarder följs och att kodkvaliteten bibehålls om kontroller sker innan koden godkänns för sammanslagning.

[- Workflow automation, why? | atlassian.com](https://www.atlassian.com/agile/project-management/workflow-automation)
[- Workflow automation 2024 guide | pipefy.com](https://www.pipefy.com/blog/what-is-workflow-automation/)

---


## PG 1.9 Virtualisering av utvecklingsmiljö
Virtualisering av utvecklingsmiljö innebär att skapa isolerade och reproducerbara miljöer där utvecklare kan arbeta utan att påverka varandra eller produktionssystemet.

#### Docker
***Docker***  är ett av de mest använda verktygen för detta. Med Docker kan applikationer och deras dependencies paketeras i lättviktscontainrar. Dessa containrar är isolerade från varandra och innehåller allt som behövs för att köra applikationen, inklusive kod, runtime och bibliotek. Detta gör det enkelt att snabbt sätta upp och stänga ner utvecklingsmiljöer, vilket sparar tid och minskar risken för problem.

En ***Docker container*** är en körbar instans av en ***Docker image***, den faktiska enheten som körs i en isolerad miljö med egna processer, nätverksgränssnitt och filsystem. En ***Dockerfile*** är en textfil med instruktioner för att bygga en Docker image, som är ett exekverbart paket med allt som behövs för att köra en applikation. Till exempel, kommandot ```FROM node:14``` i en Dockerfile använder en färdig Docker image med Node.js version 14 från Docker Hub, vilket eliminerar behovet av manuell installation.

För att bygga en image används kommandot ```docker build -t emmas-app``` . i terminalen. Detta skapar en Docker image från Dockerfilen och taggar den som "emmas-app". För att starta en container från imagen används ```docker run -d -p 3000:3000 emmas-app```. Detta kör applikationen i bakgrunden och mappar port 3000 lokalt till port 3000 i containern. Det är viktigt att komma ihåg att en image inte kan ändras när den väl har skapats.

***Docker Compose*** är ett verktyg för att definiera och köra applikationer med flera containrar. Det förenklar hanteringen av hela applikationsstacken genom att definiera tjänster, nätverk och volymer i en enda YAML-konfigurationsfil. Genom att använda kommandot ```docker-compose up -d``` kan alla tjänster som definieras i docker-compose.yml startas med ett enda kommando. 

Compose-filen följer Compose-specifikationen och placeras vanligtvis i arbetskatalogen som compose.yaml. För att stoppa och ta bort tjänster används ```docker compose down```.

Eftersom varje container körs isolerat minskar risken för konflikter mellan dependencies och miljövariabler Docker-containrar kan köras på vilken plattform som helst som stödjer Docker, vilket gör det enkelt att flytta applikationer mellan olika miljöer. Containrar delar operativsystemets kärna, vilket gör dem mer resurseffektiva än traditionella virtuella maskiner. Detta leder till snabbare uppstartstider och lägre resursanvändning.

***Docker Desktop***
Docker Desktop är en enkel applikation för som låter dig bygga, dela och köra containeriserade applikationer. 
Det inkluderar *Docker Engine*, *Docker CLI*, *Docker Compose* och andra verktyg, vilket gör det enkelt att hantera containrar och bilder via ett användavänligt GUI.
 Docker Desktop minskar tiden för komplexa inställningar och uppdateras regelbundet med buggfixar och säkerhetsuppdateringar.


[Docker Desktop | docs.docker](https://docs.docker.com/desktop/)
[Docker Compose | docs.docker](https://docs.docker.com/compose/)
[Vad är Docker? | kinsta.com](https://kinsta.com/se/kunskapsbas/vad-ar-docker/#vad-r-docker)
___

## PG 1.10 Bundeling-verktyg
***Bundling-verktyg*** samlar ihop, eller "bundlar", olika resurser som JavaScript, CSS och bilder till en enda fil eller ett mindre antal filer.
Detta minskar antalet HTTP-förfrågningar som behövs för att ladda en webbsida, vilket resulterar i snabbare laddning och högre prestanda. Målet är att minska antalet filer som behöver laddas av webbläsaren och att optimera dessa filer för snabbare leverans, vilket innefatta bla minifiering, som tar bort onödiga tecken från koden, och tree shaking, som tar bort oanvänd/redundant kod.

***Minifiering***
- **Borttagning av blanksteg och radbrytningar:** Alla onödiga blanksteg, radbrytningar och tabbar tas bort för att minska filstorleken.
- **Borttagning av kommentarer:** Alla kommentarer i koden, som ofta används för att förklara eller dokumentera kod, tas bort.
- **Förkortning av variabelnamn:** Variabelnamn och funktionsnamn kan förkortas för att ytterligare minska storleken på koden.
- **Eliminering av onödig kod:** Oanvänd kod eller kod som inte bidrar till funktionaliteten kan tas bort.

***Webpack***
Webpack kan hantera JavaScript, CSS, bilder och HTML-filer. Webpack använder 'dedependecy manager' som skapar ett 'dependency tree' av alla moduler i din applikation och genererar en eller flera bundle-filer.

***Beroendehantering:*** I Webpack innebär detta att applikationen först analyseras utifrån huvudfilen (entry point) och skapar ett träd över dependencies. Detta görs genom att analysera alla *imports* och *requires* i ingångspunkten. Därefter packas alla dependencies ihop i moduler som har tillgång till dem de specifikt behöver. Slutligen skapar Webpack bundles som innehåller alla moduler och deras dependencies, vilket optimerar laddningstiden för applikationen.

***Skript och Automatisering:*** Webpack kan användas för att definiera och köra byggprocesser automatiskt genom att konfigurera regler och plugins i en konfigurationsfil. Detta gör det möjligt att automatisera uppgifter som minifiering, bundle-skapande och koddelning.

***Plugins:*** Webpack har ett system för plugins som gör det möjligt att utöka och anpassa bundling-processen ytterligare. Plugins kan användas för att optimera bundles, hantera tillgångar som bilder och fonts, generera HTML-filer och mycket mer. Detta gör Webpack flexibelt och anpassningsbart för olika typer av projekt.

Fördelen utöver den förbättrade laddningstiden är att utvecklare inte behöver hantera och inkludera varje bibliotek manuellt i varje fil, utan kan istället deklarera dependencies i sina källfiler som Webpack samlar i bundle-filer.

***Rollup:*** Rollup är ett modulärt bundling-verktyg som ofta används för att paketera JavaScript-bibliotek och -moduler. Det fokuserar på att skapa små och effektiva bundles och stödjer tree-shaking för att ta bort oanvänd kod.

***Parcel:*** Parcel är ett annat bundling-verktyg som är känt för sin snabbhet och enkelhet. Det kräver minimal konfiguration och har inbyggt stöd för många typer av filer och moderna JavaScript-funktioner.


#### Package manager
NPM (Node Package Manager) är inte ett bundling-verktyg i sig, men har en stor roll i bundling-processen genom att hantera och installera de paket och moduler som behövs för att bundling-verktygen ska fungera. 
Många bundling-verktyg som *Webpack*, *Rollup* och *Parcel* använder NPM för att installera och hantera deras plugins och dependencies.
 NPM hanterar bibliotek och moduler som används av bundling-verktyg, inklusive både huvudverktyget och dess tillägg eller plugins som kan behövas för specifika funktioner. Det kan också definiera skript i *package.json-filen* som kör bundling-processer, till exempel kommandon för att köra Webpack eller Parcel för att bygga projektet.

[Comparing JS bundlers: Rollup vs Webpack vs Parcel | kinsta.com](https://kinsta.com/blog/rollup-vs-webpack-vs-parcel/)
[- Webpack | webpack.js.org](https://webpack.js.org/concepts/)
[- 5 different bundelling tools | amplication.com](https://amplication.com/blog/5-different-tools-to-bundle-nodejs-apps)
___

## PG 1.11 Terminalinterface
Ett terminalinterface/CLI *(Command line interface)* är en typ av UI där användaren interagerar direkt med datorns OS genom att skriva kommandon i text i terminalen eller en annan kommandotolk. Till skillnad från grafiska användargränssnitt (GUI), där användaren interagerar med ikoner och visuella indikatorer, förlitar sig CLI på att användaren skriver specifika kommandon för att utföra olika uppgifter. Användaren kan redigera filer, navigera sig i filsystemet, installera- och tom skapa program.
Kommandona skrivs manuellt av användaren och blir besvarade i text-output.

Exempel på två små roliga program att köra via CLI:

***FIGLET***
FIGLET är ett program som omvandlar vanlig text till ASCII-konst.
<img src="/Img/install-figlet.png" alt="installation av figlet">
<img src="/Img/figlet-sebseb.png" alt="Hejsan Sebseb!">

***COWSAY***
COWSAY är ett program som visar text i en pratbubbla tillsammans med en ASCII-konstko eller andra djur. 
<img src="/Img/install-cowsay.png" alt="installation av Cowsay">
<img src="/Img/cow-dragon-cowsay.png" alt="cow and dragon">

Att arbeta med CLI kräver viss inlärning och minne eftersom användaren måste känna till de specifika kommandon och syntax som behövs för att utföra olika uppgifter.
Till exempel, för att navigera i filsystemet används kommandon som cd (change directory) för att byta katalog, ls (list) för att lista filer i en mapp, och mkdir (make directory) för att skapa en ny mapp.

CLI är ett verktyg som erbjuder en hög grad av kontroll och precision. För utvecklare och systemadministratörer är det ofta en nödvändighet, eftersom det möjliggör snabb och effektiv hantering av systemuppgifter. Det är också möjligt att skriva skript i kommandoradsmiljöer för att automatisera repetitiva uppgifter, vilket ökar effektiviteten och minskar risken för fel.

CLI är mycket resurseffektivt eftersom det inte kräver de grafiska resurser som ett GUI gör. Detta gör det möjligt att arbeta på fjärrsystem med begränsade resurser eller att utföra uppgifter snabbare på äldre hårdvara.

En av de största utmaningarna med att använda CLI är inlärningskurvan. Det kräver att användaren lär sig ett stort antal kommandon och dess syntax. Det finns inga visuella ledtrådar eller verktygstips, så användaren måste veta exakt vad de vill göra och hur de ska skriva kommandot. Detta kan göra felsökning svårare, särskilt om man gör ett misstag i syntaxen.

Förutom de grundläggande kommandona finns det flertal verktyg och skript som kan göra användningen av CLI smidigare och enklare. Verktyg som *grep*, *awk* och *sed* för att söka och manipulera textdata. Paket- och versionshanterare som *apt*, *yum* och *brew* gör det enkelt att installera och uppdatera programvara direkt från kommandoraden. Dessutom kan du anpassa din CLI-miljö med konfigurationsfiler som .bashrc eller .zshrc kan du anpassa hur din kommandotolk fungerar och ser ut bla genom att lägga till mappar till ens `PATH`-variabel för att kunna köra program från dessa var man än befinner sig i filsystemet.

[- CLI | freecodecamp.org](https://www.freecodecamp.org/news/how-to-use-the-cli-beginner-guide/)
[- CLI over GUI? | hostinger.com](https://www.hostinger.com/tutorials/what-is-cli)