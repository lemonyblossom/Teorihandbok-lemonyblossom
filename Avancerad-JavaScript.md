# Teorihandboken - Avancerad JavaScript (AJ)
Studerande: Emma Jensen

## AJ 1.1 Node.js

Node.js är en öppen källkod, cross-platform JavaScript runtime-miljö som körs på V8-motorn och exekverar JavaScript-kod utanför en webbläsare. Node.js möjliggör utveckling av server-side och nätverksapplikationer med JavaScript. En av de största fördelarna med Node.js är dess asynkrona, event-drivna arkitektur som gör det möjligt att hantera många samtidiga anslutningar med hög prestanda.

### Installation och grundläggande användning

För att installera Node.js, besök den officiella webbplatsen och ladda ner installationsprogrammet för ditt operativsystem. Efter installationen kan du verifiera att Node.js är korrekt installerat genom att köra följande kommando i terminalen:

```sh
node -v
```

Exempel på en enkel server skapad med node.js:

```js
const http = require('http');

const server = http.createServer((req, res) => {
    res.statusCode = 200;
    res.setHeader('Content-Type', 'text/plain');
    res.end('Hello, World!\n');
});

const port = 3000;
server.listen(port, () => {
    console.log(`Server running at http://localhost:${port}/`);
});
```

#### Fördelar med Node.js
Fördelarna med Node.js är många. För det första är snabbheten en stor fördel, då Node.js använder V8-motorn som kompilerar JavaScript till maskinkod, vilket gör det mycket snabbt. En annan viktig fördel är den asynkrona I/O-modellen som Node.js använder. Denna icke-blockerande modell gör det möjligt att hantera många samtidiga anslutningar effektivt, vilket är avgörande för att bygga skalbara nätverksapplikationer. Dessutom erbjuder NPM (Node Package Manager) ett stort ekosystem med ett stort antal paket som kan användas för att utöka funktionaliteten i dina applikationer.

Node.js är också känt för sin enkelhet och flexibilitet. Utvecklare kan snabbt sätta upp en server och börja utveckla applikationer utan att behöva hantera komplexa konfigurationer. Detta gör det till ett bra val för både nybörjare och erfarna utvecklare. Node.js har också ett stort och aktivt community som bidrar med verktyg, bibliotek och support, vilket gör det enklare att hitta lösningar på problem och hålla sig uppdaterad med de senaste trenderna och best praxis.

En annan fördel med Node.js är dess förmåga att hantera realtidsapplikationer. Tack vare dess asynkrona natur och event-drivna arkitektur är Node.js idealiskt för applikationer som kräver snabb och effektiv hantering av realtidsdata, såsom chattapplikationer, spel och live-streaming-tjänster.

Sammanfattningsvis är Node.js ett verktyg som används av många stora företag och organisationer världen över för att bygga skalbara och högpresterande nätverksapplikationer. Dess snabbhet, asynkrona I/O-modell, stora ekosystem och enkelhet gör det till ett utmärkt val för utvecklare som vill skapa moderna och effektiva applikationer

För mer information om Node.js och dess fördelar, se följande källor:

1. [Node.js officiella webbplats](https://nodejs.org/en/)
2. [NPM (Node Package Manager)](https://www.npmjs.com/)
3. [Mozilla Web Docs | Node.js](https://developer.mozilla.org/en-US/docs/Learn/Server-side/Node_server_without_framework)
4. [W3Schools | Node.js Tutorial](https://www.w3schools.com/nodejs/)

---

## AJ 1.2 Express
Express är ett minimalt och flexibelt Node.js webbramverk som erbjuder en robust uppsättning funktioner för att bygga webb- och mobilapplikationer.
Det är ett av de mest populära ramverken för Node.js och används ofta för att skapa RESTful API:er.

```sh
npm install express
```
Exempel på hur man skapar en enkel applikation med express:

```js
const express = require('express');
const app = express();
const port = 3000;

app.get('/', (req, res) => {
    res.send('Hello, World!');
});

app.listen(port, () => {
    console.log(`Server running at http://localhost:${port}/`);
});
```
#### Middleware och routing
Express använder middleware för att hantera HTTP-förfrågningar. 
Middleware är funktioner som har tillgång till request- och response-objekten och kan ändra dem eller avsluta förfrågan. 
Här är ett exempel på hur man använder middleware:

```js
app.use((req, res, next) => {
    console.log('Time:', Date.now());
    next();
});
```
Express erbjuder också ett kraftfullt routing-system som gör det enkelt att definiera olika routes för din applikation:
```js
app.get('/about', (req, res) => {
    res.send('About Page');
});
```

#### Hantering av fel
En viktig aspekt av att bygga robusta applikationer är att hantera fel på ett effektivt sätt. 
Express gör det enkelt att skapa middleware för felhantering.
```js
app.use((err, req, res, next) => {
    console.error(err.stack);
    res.status(500).send('Något gick fel!');
});
```

#### Prestandaoptimering
Express erbjuder flera sätt att optimera prestandan för dina applikationer. 
Du kan till exempel använda caching, komprimering och andra tekniker för att förbättra svarstider och minska serverbelastningen. 
Här är ett exempel på hur man använder komprimering:

```js
const compression = require('compression');
app.use(compression());
```

####Säkerhet
Säkerhet är en annan viktig aspekt av webbapplikationer. 
Express kan integreras med olika säkerhetsbibliotek för att skydda dina applikationer mot vanliga hot som XSS, CSRF och SQL-injektioner. 
Ett exempel är att använda helmet för att ställa in olika HTTP-headers för att förbättra säkerheten:
```js
const helmet = require('helmet');
app.use(helmet());
```
Express är också mycket modulärt, vilket innebär att du kan använda endast de delar du behöver och enkelt integrera andra bibliotek och verktyg. 
Detta gör det till ett utmärkt val för både små och stora projekt.

Sammanfattningsvis är Express ett mångsidigt ramverk som underlättar skapandet av skalbara och underhållbara webbapplikationer med Node.js.
Dess enkelhet, flexibilitet och stora ekosystem gör det till ett populärt val bland utvecklare världen över.

1. [Express officiella webbplats](https://expressjs.com/)
2. [NPM (Node Package Manager) | Express](https://www.npmjs.com/package/express)
3. [Mozilla Web Docs | Express](https://developer.mozilla.org/en-US/docs/Learn/Server-side/Express_Nodejs)
4. [W3Schools | Express Tutorial](https://www.w3schools.com/nodejs/nodejs_express.asp)
--- 

## AJ 1.3 Progressive Web Apps
Beskriv rubriken här

## AJ 1.4 Typningssystem för Javascript (ex TypeScript, Flow)
Beskriv rubriken här

## AJ 1.5 Funktionell programmering i JavaScript
Beskriv rubriken här

## AJ 1.6 Avancerad funktionalitet i ES.next
Beskriv rubriken här

## AJ 1.7 JavaScript i integrerade system
Beskriv rubriken här

## AJ 1.8 Native bundeling av JavaScript för olika operativsystem och enheter
Beskriv rubriken här

