# Teorihandboken - Avancerad JavaScript (AJ)
Studerande: Emma Jensen

## AJ 1.1 Node.js
Node.js är en open source-plattform som låter JavaScript köras på serversidan, alltså utanför webbläsaren. Den skapades 2009 av Ryan Dahl och har sedan dess förändrat hur man bygger webbapplikationer. Istället för att bara använda JavaScript för att skapa interaktivitet i webbläsare, kan Node.js användas för att bygga allt från enkla webbservrar till stora, komplexa applikationer. Grunden i Node.js är V8, en JavaScript-motor från Google som även används i Chrome.

Node.js är byggt på enkelhet och hög prestanda, med fokus på asynkronitet och event-driven programmering. Med andra ord försöker Node.js göra så mycket som möjligt samtidigt, utan att behöva vänta på att enskilda processer blir klara.

I en vanlig servermiljö kan varje request blockera servern tills den är färdig, men i Node.js hanteras varje request i bakgrunden medan nästa uppgift redan påbörjas. Det gör Node.js särskilt användbart för applikationer som hanterar många samtidiga användare, som realtidschat eller streamingtjänster.

Ett annat verktyg i Node.js är npm (Node Package Manager), där man kan hitta ett enormt bibliotek av paket och moduler att integrera i sina projekt. Det förenklar utvecklingsprocessen avsevärt. Node.js är också perfekt för att skapa RESTful API:er, vilket är en standard för att låta olika delar av en applikation prata med varandra.

Node.js har också ett stort och aktivt community som bidrar med en mängd olika moduler och verktyg. Detta gör det enkelt att hitta lösningar på problem och att få hjälp när man stöter på hinder i utvecklingsprocessen. Dessutom finns det många resurser, som dokumentation, tutorials och kurser, som kan hjälpa både nybörjare och erfarna utvecklare att lära sig och förbättra sina färdigheter i Node.js.

En annan fördel med Node.js är dess höga prestanda. Eftersom Node.js är byggt på V8-motorn, som är känd för sin snabbhet och effektivitet, kan Node.js-applikationer hantera många samtidiga anslutningar med låg latens. Detta gör det möjligt att bygga skalbara och responsiva applikationer som kan hantera stora mängder trafik.

Node.js är också plattformsoberoende, vilket innebär att det kan köras på olika operativsystem som Windows, macOS och Linux. Detta gör det enkelt att utveckla och distribuera applikationer på olika plattformar utan att behöva göra några större ändringar i koden.

Sammanfattningsvis har Node.js revolutionerat serverside-programmering med JavaScript och möjliggjort utveckling av både enkla och avancerade backend-lösningar. Med dess fokus på asynkronitet, hög prestanda och ett stort ekosystem av moduler och verktyg, är Node.js ett kraftfullt verktyg för att bygga moderna webbapplikationer.Node.js är en open source-plattform som låter JavaScript köras på serversidan, alltså utanför webbläsaren. Den skapades 2009 av Ryan Dahl och har sedan dess förändrat hur man bygger webbapplikationer. Istället för att bara använda JavaScript för att skapa interaktivitet i webbläsare, kan Node.js användas för att bygga allt från enkla webbservrar till stora, komplexa applikationer. Grunden i Node.js är V8, en JavaScript-motor från Google som även används i Chrome.

Node.js är byggt på enkelhet och hög prestanda, med fokus på asynkronitet och event-driven programmering. Med andra ord försöker Node.js göra så mycket som möjligt samtidigt, utan att behöva vänta på att enskilda processer blir klara.

I en vanlig servermiljö kan varje request blockera servern tills den är färdig, men i Node.js hanteras varje request i bakgrunden medan nästa uppgift redan påbörjas. Det gör Node.js särskilt användbart för applikationer som hanterar många samtidiga användare, som realtidschat eller streamingtjänster.

Ett annat verktyg i Node.js är npm (Node Package Manager), där man kan hitta ett enormt bibliotek av paket och moduler att integrera i sina projekt. Det förenklar utvecklingsprocessen avsevärt. Node.js är också perfekt för att skapa RESTful API:er, vilket är en standard för att låta olika delar av en applikation prata med varandra.

Node.js har också ett stort och aktivt community som bidrar med en mängd olika moduler och verktyg. Detta gör det enkelt att hitta lösningar på problem och att få hjälp när man stöter på hinder i utvecklingsprocessen. Dessutom finns det många resurser, som dokumentation, tutorials och kurser, som kan hjälpa både nybörjare och erfarna utvecklare att lära sig och förbättra sina färdigheter i Node.js.

En annan fördel med Node.js är dess höga prestanda. Eftersom Node.js är byggt på V8-motorn, som är känd för sin snabbhet och effektivitet, kan Node.js-applikationer hantera många samtidiga anslutningar med låg latens. Detta gör det möjligt att bygga skalbara och responsiva applikationer som kan hantera stora mängder trafik.

Node.js är också plattformsoberoende, vilket innebär att det kan köras på olika operativsystem som Windows, macOS och Linux. Detta gör det enkelt att utveckla och distribuera applikationer på olika plattformar utan att behöva göra några större ändringar i koden.

Sammanfattningsvis har Node.js revolutionerat serverside-programmering med JavaScript och möjliggjort utveckling av både enkla och avancerade backend-lösningar. Med dess fokus på asynkronitet, hög prestanda och ett stort ekosystem av moduler och verktyg, är Node.js ett kraftfullt verktyg för att bygga moderna webbapplikationer.

---

## AJ 1.2 Express
Express är ett minimalistiskt och flexibelt ramverk för Node.js, som gör det enklare att skapa webbapplikationer och API:er. Genom att erbjuda funktioner för att hantera HTTP-förfrågningar, routing och middleware, förenklar Express utvecklingsprocessen och gör det möjligt att snabbt bygga både enkla och avancerade applikationer. Ramverket är populärt bland backend-utvecklare tack vare sin modularitet och höga anpassningsbarhet.

En grundläggande byggsten i Express är användningen av middleware. Middleware är funktioner som körs under behandlingen av en HTTP-förfrågan och kan användas för att hantera olika uppgifter. Det kan vara allt från att logga requests, autentisera användare eller bearbeta inkommande data innan den når själva applikationslogiken. Eftersom middleware är modulärt byggt kan utvecklare enkelt lägga till nya funktioner eller anpassa befintliga utan att behöva omstrukturera hela applikationen. Denna flexibilitet gör Express till ett mycket skalbart ramverk.

En viktig aspekt av moderna webbapplikationer är autentisering och säkerhet. I Express kan autentisering hanteras effektivt med hjälp av middleware som kontrollerar användarens identitet vid varje begäran. En vanlig metod för autentisering är användning av JSON Web Tokens (JWT), där användare loggar in och får en token som kan användas för att autentisera framtida förfrågningar.

Exempel på hur man implementerar autentisering med JWT i Express:
```js
const express = require('express');
const jwt = require('jsonwebtoken');
const app = express();

// Middleware för att skydda routes
const verifyToken = (req, res, next) => {
    const token = req.header('Authorization');
    if (!token) return res.status(401).send('Access Denied');
    
    jwt.verify(token, 'secretkey', (err, decoded) => {
        if (err) return res.status(403).send('Invalid Token');
        req.user = decoded;
        next();
    });
};

// Route för inloggning och tokengenerering
app.post('/login', (req, res) => {
    const user = { id: 1, name: 'John Doe' }; // Här kan du hämta användardata från en databas
    const token = jwt.sign(user, 'secretkey');
    res.json({ token });
});

// Skyddad route
app.get('/dashboard', verifyToken, (req, res) => {
    res.send('Välkommen till din dashboard!');
});

app.listen(3000, () => {
    console.log('Servern körs på port 3000');
});
```
I exemplet använder vi JWT för att skapa och verifiera tokens. När användaren loggar in, genereras en token som skickas tillbaka till klienten. För skyddade routes, som exempelvis "/dashboard", måste användaren skicka med sin token i begäran för att få tillgång. Middleware-funktionen ```verifyToken``` kontrollerar om token är giltig innan användaren får åtkomst till den skyddade resursen.

För att ytterligare stärka säkerheten kan man implementera CORS (Cross-Origin Resource Sharing). 
CORS är en mekanism som tillåter eller blockerar requests från externa domäner, vilket kan vara användbart för att förhindra att andra webbplatser gör otillåtna anrop till din server.


Exempel på hur man implementerar CORS i Express:
```js
const express = require('express');
const cors = require('cors');
const app = express();

// Aktivera CORS för alla domäner
app.use(cors());

// Alternativt, tillåt endast specifika domäner
 app.use(cors({
origin: 'https://enspecifikdoman.com',
 }));

app.get('/', (req, res) => {
    res.send('CORS är aktiverat!');
});

app.listen(3000, () => {
    console.log('Servern körs på port 3000');
});
```


Sammanfattningsvis är säkerhet en avgörande del av alla webbapplikationer, och Express gör det lätt att implementera autentisering, skydda rutter och lägga till säkerhetsåtgärder som CORS. Genom att använda middleware kan du snabbt och effektivt hantera dessa uppgifter, vilket gör att din applikation blir både säker och skalbar.

---

## AJ 1.3 Progressive Web Apps
Progressive Web Apps (PWA) är en typ av webbapplikation som kombinerar det bästa från webb och mobilappar. De använder moderna teknologier för att ge offline-stöd, push-notiser och möjligheten att installera appen direkt på enhetens hemskärm.

De viktigaste egenskaperna hos en PWA är:

Responsivitet - De fungerar lika bra på olika enheter och skärmstorlekar.

Offline-funktionalitet - Genom Service Workers kan resurser cachelagras lokalt.

Installationsbar - Man kan lägga till appen på hemskärmen utan att använda en appbutik.

För att skapa en PWA använder man sig av teknologier som Service Workers och manifestfiler. Manifestet innehåller metadata som namn, ikoner och startadress, medan Service Workers tar hand om saker som caching och bakgrundsprocesser.

Ett exempel på en enkel Service Worker:
```js
self.addEventListener('install', event => {
    event.waitUntil(
        caches.open('v1').then(cache => {
            return cache.addAll([
                '/',
                '/index.html',
                '/styles.css',
                '/script.js'
            ]);
        })
    );
});

self.addEventListener('fetch', event => {
    event.respondWith(
        caches.match(event.request).then(response => {
            return response || fetch(event.request);
        })
    );
});
```

PWA är ett smart val för företag som vill förbättra användarupplevelsen utan att behöva utveckla separata mobil- och webbappar. Tack vare snabb laddning och offline-stöd är PWA ett framtidssäkert sätt att skapa moderna applikationer. Twitter och Starbucks är exempel på företag som lyckats väl med sina PWA-satsningar.

---

## AJ 1.4 Typningssystem för Javascript (ex TypeScript, Flow)
JavaScript är dynamiskt typat, vilket ibland kan ställa till problem. För att undvika överraskningar använder man typningssystem som TypeScript eller Flow, som lägger till statiska typer och gör koden mer förutsägbar.

#### TypeScript

TypeScript är ett superset av JavaScript som inför statiska typer och kompileras ner till vanligt JavaScript. Det gör att man får bättre verktygsstöd, som autokomplettering och felkontroll direkt i editorn.

function greet(name: string): string {
    return `Hej, ${name}!`;
}

console.log(greet('Emma'));

TypeScript är särskilt användbart i större projekt med flera utvecklare, eftersom det hjälper till att strukturera och underhålla koden bättre. Man kan också använda gränssnitt och generiska typer för att skapa modulära lösningar.

#### Flow

Flow är ett annat verktyg som analyserar JavaScript-kod för att hitta typfel. Det kräver inga större ändringar i koden och fungerar bra för gradvis införande.

```js
// @flow
function square(n: number): number {
    return n * n;
}

console.log(square(4));
```

Med både TypeScript och Flow blir koden mer robust och lättare att jobba med, särskilt i större team eller långsiktiga projekt. Valet mellan dessa verktyg handlar oftast om personliga preferenser och projektets behov.

---


## AJ 1.5 Funktionell programmering i JavaScript

Funktionell programmering är ett programmeringsmönster där man behandlar beräkningar som t.ex. uträkningar av matematiska funktioner och undviker förändringar av tillstånd och data. JavaScript stödjer funktionell programmering genom att behandla funktioner som vanliga värden, higher order functions och immutable data.

Ett exempel på en higher order function är `map`, som tar en funktion som argument och applicerar den på varje element i en array:

```js
const numbers = [1, 2, 3, 4];
const squared = numbers.map(n => n * n);
console.log(squared); // [1, 4, 9, 16]
```
Genom att använda funktionell programmering kan man skriva mer deklarativ och readable kod, vilket underlättar underhåll och testning. 


Funktionell programmering främjar också immutabilitet, vilket innebär att data inte förändras efter att den har skapats. Detta kan minska buggar och göra koden mer förutsägbar på flera sätt:
>
> **Ingen oavsiktlig förändring av data:** När data är immutable kan man vara säker på att den inte kommer att ändras av misstag någonstans i koden. Detta minskar risken för oavsiktliga sidoeffekter som kan leda till svårfunna buggar.
>
>**Enklare att förstå och resonera om koden:** När data är immutable är det lättare att förstå hur data flödar genom applikationen. Man kan vara säker på att en viss variabel alltid har samma värde efter att den har tilldelats, vilket gör koden mer förutsägbar och därför lättare att förutspå.
>
>**Enklare att testa:** Immutabla data gör det enklare att skriva enhetstester eftersom man kan vara säker på att testdata inte förändras under testets gång. Detta leder till mer pålitliga tester och enklare felsökning.
>
>**Tråd-säkerhet:** I miljöer där flera trådar kan komma åt samma data samtidigt, kan immutabilitet förhindra race conditions och andra trådrelaterade buggar eftersom data inte kan ändras av en tråd medan en annan tråd läser den.
>
   > *<small>Race conditions är fel som uppstår i flertrådade system när flera trådar eller processer samtidigt försöker ändra delad data. Detta kan leda till oförutsägbara resultat och svårfunna buggar eftersom utfallet beror på den exakta tidpunkten för exekveringen.</small>*
>
>**Förutsägbara funktioner:** Funktioner som arbetar med immutabel data är ofta pure functions, vilket innebär att de alltid returnerar samma resultat givet samma indata och inte har några biverkningar. Detta gör dem enklare att förstå, testa och felsöka.
>
>Sammanfattningsvis bidrar immutabilitet till att minska buggar och göra koden mer förutsägbar genom att eliminera oavsiktliga förändringar av data, göra koden lättare att förstå och resonera om, förenkla testning och förbättra tråd-säkerhet.

En annan viktig aspekt av funktionell programmering är användningen av pure functions/ rena funktioner. En *ren* funktion är en funktion som alltid returnerar samma resultat givet samma indata och inte har några biverkningar. 
Detta gör det enklare att testa och felsöka koden.

```js
function add(a, b) {
    return a + b;
}
console.log(add(2, 3)); // 5
```
Higher order functions är funktioner som antingen tar en eller flera funktioner som argument eller returnerar en funktion. Förutom map finns det andra higher order functions som *filter* och *reduce*.

*filter* används för att skapa en ny array med alla element som uppfyller ett visst villkor:

```js
const numbers = [1, 2, 3, 4, 5];
const evenNumbers = numbers.filter(n => n % 2 === 0);
console.log(evenNumbers); // [2, 4]
```

*reduce* används för att reducera en array till ett enda värde genom att applicera en funktion på varje element i arrayen:

```js
const numbers = [1, 2, 3, 4];
const sum = numbers.reduce((acc, n) => acc + n, 0);
console.log(sum); // 10
```



## AJ 1.6 Avancerad funktionalitet i ES.next
Beskriv rubriken här

## AJ 1.7 JavaScript i integrerade system
Beskriv rubriken här

## AJ 1.8 Native bundeling av JavaScript för olika operativsystem och enheter
Beskriv rubriken här

