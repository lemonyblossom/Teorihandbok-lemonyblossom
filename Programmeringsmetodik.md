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
# Byt till en feature-branch
git checkout feature-branch
````
````
# Skapa en ny branch och byta till den
git checkout -b new-feature-branch
````
````
# Push ändringar till den delade feature-branchen
git push origin feature-branch
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


## PG 1.3 Testdriven utveckling
Testdriven utveckling innefattar att använda sig av utvecklingsmetodik där tester skrivs innan själva koden skrivs. Därmed definieras varje funktionalitet genom tester som initialt misslyckas, därefter utvecklas funktionen för att klara testet.

Ett enhetstest för en specifik funktion, som ej finns än, skrivs av en utvecklare som sedan körs och misslyckas, Sedan skrivs funktionen baserat på testet för att klara av det. Testet körs igen och förväntas gå igenom utan misslyckande och när funktionen beter sig som väntat så refaktoreras koden vid behov för att förbättra kodstrukturen. 
Detta tillvägagångssätt gör att vi kan säkerställa att varje enkild funktion beter sig som förväntat.

#### Jest
Jest är ett testverktyg för JavaScript och TypeScript, utvecklat av Facebook. Det används för att skriva enhetstester och integrera tester för att säkerställa kodkvalitet med hjälp av funktioner som snapshot-testning, parallell körning av tester och inbyggd support för mockning av moduler

Exempel på test Jest för Javascript:

Test som väntas misslyckas då funktinalitet saknas.
```js
const { add } = require('./calculator');

test('adds 2 + 3 to equal 5', () => {
    
    expect(add(2, 3)).toBe(5);
});

// Detta test kommer att misslyckas eftersom funktionen 'add' ännu inte är definierad.
```

```js
function add(a, b) {
    return a + b;
}

module.exports = { add };

//Här har koden skrivits som förväntas passera testet ovan
```

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
```js
function add(a, b) {
    return a + b;
}

module.exports = { add };
```


## PG 1.4 Deploy och staging
**Deploying** innebär att föra över applikationen från utvecklingsmiljön till produktionsmiljön, där den blir tillgänglig för användare.Denna process är avgörande för att säkerställa att applikationen fungerar korrekt och pålitligt under verkliga förhållanden.

Processen involverar att bygga applikationen, köra tester, och sedan flytta den till produktionsservrar.

**Staging** är en mellanliggande miljö där applikationen testas för att säkerställa att den fungerar korrekt innan den deployas till produktion.

 Stagingmiljön är en kopia av produktionsmiljön och används för att simulera hur applikationen kommer att bete sig i produktion. Detta inkluderar att köra applikationen med samma databaser, konfigurationer och tjänster som i produktionsmiljön.

Den används för att utföra sista minuten-testning i syfte att identifiera och åtgärda buggar eller andra problem innan de når användarna. Detta hjälper att förebygga risken för driftstopp och andra oväntade problem som kanske inte uppstår i utvecklingsmiljön, men som kan påverka användarna i den färdiga produkten.

Det är också viktigt att följa best practise vid deployment, vilket inkluderar att använda versionskontroll, utföra kontinuerlig integration och kontinuerlig leverans (CI/CD), och att ha dokumenterade strategier för rollback på plats ifall något går fel.

Sammantaget bidrar en väl utförd deployment till en smidigare och säkrare övergång till produktion, vilket resulterar i en bättre användarupplevelse och minskad stress för utvecklarna.


## PG 1.5 Debugging
Beskriv rubriken här

## PG 1.6 Dokumentation
Beskriv rubriken här

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

