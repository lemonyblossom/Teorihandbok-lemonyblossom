# Teorihandboken - Avancerad JavaScript (AJ)
Studerande: Emma Jensen

## AJ 1.1 Node.js
Node.js är en open source-plattform som låter JavaScript köras på serversidan, alltså utanför webbläsaren.
Den skapades 2009 av Ryan Dahl och har sedan dess förändrat hur man bygger webbapplikationer. Istället för att bara använda JavaScript för att skapa interaktivitet i webbläsare, kan Node.js användas för att bygga allt från enkla webbservrar till stora, komplexa applikationer. Grunden i Node.js är V8, en JavaScript-motor från Google som även används i Chrome.

Node.js är byggt på enkelhet och hög prestanda, med fokus på asynkronitet och event-driven programmering. Med andra ord försöker Node.js göra så mycket som möjligt samtidigt, utan att behöva vänta på att enskilda processer blir klara.

I en vanlig servermiljö kan varje request blockera servern tills den är färdig, men i Node.js hanteras varje request i bakgrunden medan nästa uppgift redan påbörjas. Det gör Node.js särskilt användbart för applikationer som hanterar många samtidiga användare, som realtidschat eller streamingtjänster.

Ett annat kraftfullt verktyg i Node.js är npm (Node Package Manager), där man kan hitta ett enormt bibliotek av paket och moduler att integrera i sina projekt. Det förenklar utvecklingsprocessen avsevärt. Node.js är också perfekt för att skapa RESTful API:er, vilket är en standard för att låta olika delar av en applikation prata med varandra. Sammanfattningsvis har Node.js revolutionerat serverside-programmering med JavaScript.

---

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

