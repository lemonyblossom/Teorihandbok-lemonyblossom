# Teorihandboken - Avancerad JavaScript (AJ)
Studerande: Emma Jensen

## AJ 1.1 Node.js
Node.js är en open source-plattform som låter JavaScript köras på serversidan, alltså utanför webbläsaren.
Den skapades 2009 av Ryan Dahl och har sedan dess förändrat hur man bygger webbapplikationer. Istället för att bara använda JavaScript för att skapa interaktivitet i webbläsare, kan Node.js användas för att bygga allt från enkla webbservrar till stora, komplexa applikationer. Grunden i Node.js är V8, en JavaScript-motor från Google som även används i Chrome.

Node.js är byggt på enkelhet och hög prestanda, med fokus på asynkronitet och event-driven programmering. Med andra ord försöker Node.js göra så mycket som möjligt samtidigt, utan att behöva vänta på att enskilda processer blir klara.

I en vanlig servermiljö kan varje request blockera servern tills den är färdig, men i Node.js hanteras varje request i bakgrunden medan nästa uppgift redan påbörjas. Det gör Node.js särskilt användbart för applikationer som hanterar många samtidiga användare, som realtidschat eller streamingtjänster.

Ett annat kraftfullt verktyg i Node.js är npm (Node Package Manager), där man kan hitta ett enormt bibliotek av paket och moduler att integrera i sina projekt. Det förenklar utvecklingsprocessen avsevärt. Node.js är också perfekt för att skapa RESTful API:er, vilket är en standard för att låta olika delar av en applikation prata med varandra. Sammanfattningsvis har Node.js revolutionerat serverside-programmering med JavaScript.

## AJ 1.2 Express
Express är ett minimalistiskt och flexibelt ramverk för Node.js, som gör det enklare att skapa webbapplikationer och API:er. Det erbjuder smarta funktioner för att hantera HTTP-förfrågningar, routing och middleware, vilket gör det till ett av de mest populära verktygen för backend-utveckling.

Express bygger på ett modulärt sätt att jobba, där man lägger till funktioner med hjälp av middleware. Middleware är små byggstenar som hanterar olika steg av en request, som att logga data, autentisera användare eller hantera formulär.

Exempel på hur man kan använda Express:
```JS
const express = require('express');
const app = express();

// Middleware
app.use(express.json());

// Routing
app.get('/', (req, res) => {
    res.send('Hej från Express!');
});

app.post('/data', (req, res) => {
    res.send(`Data mottagen: ${JSON.stringify(req.body)}`);
});

app.listen(3000, () => {
    console.log('Servern körs på port 3000');
});
```

En stor fördel med Express är att det är så flexibelt. Det passar lika bra för enkla webbplatser som för avancerade RESTful API:er. Med stöd för mallmotorer som Pug eller EJS kan man också skapa dynamiska sidor smidigt. Med  Express och Node.js-ekosystemet kan man snabbt utveckla allt från små till riktigt stora projekt

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


## AJ 1.4 Typningssystem för Javascript (ex TypeScript, Flow)
JavaScript är dynamiskt typat, vilket ibland kan ställa till problem. För att undvika överraskningar använder man typningssystem som TypeScript eller Flow, som lägger till statiska typer och gör koden mer förutsägbar.

TypeScript

TypeScript är ett superset av JavaScript som inför statiska typer och kompileras ner till vanligt JavaScript. Det gör att man får bättre verktygsstöd, som autokomplettering och felkontroll direkt i editorn.

function greet(name: string): string {
    return `Hej, ${name}!`;
}

console.log(greet('Emma'));

TypeScript är särskilt användbart i större projekt med flera utvecklare, eftersom det hjälper till att strukturera och underhålla koden bättre. Man kan också använda gränssnitt och generiska typer för att skapa modulära lösningar.

Flow

Flow är ett annat verktyg som analyserar JavaScript-kod för att hitta typfel. Det kräver inga större ändringar i koden och fungerar bra för gradvis införande.

```js
// @flow
function square(n: number): number {
    return n * n;
}

console.log(square(4));
```

Med både TypeScript och Flow blir koden mer robust och lättare att jobba med, särskilt i större team eller långsiktiga projekt. Valet mellan dessa verktyg handlar oftast om personliga preferenser och projektets behov.


## AJ 1.5 Funktionell programmering i JavaScript
Beskriv rubriken här

## AJ 1.6 Avancerad funktionalitet i ES.next
Beskriv rubriken här

## AJ 1.7 JavaScript i integrerade system
Beskriv rubriken här

## AJ 1.8 Native bundeling av JavaScript för olika operativsystem och enheter
Beskriv rubriken här

