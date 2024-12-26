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

```sh
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

Fördelarna med Node.js är många. För det första är snabbheten en stor fördel, då Node.js använder V8-motorn som kompilerar JavaScript till maskinkod, vilket gör det mycket snabbt. En annan viktig fördel är den asynkrona I/O-modellen som Node.js använder. Denna icke-blockerande modell gör det möjligt att hantera många samtidiga anslutningar effektivt, vilket är avgörande för att bygga skalbara nätverksapplikationer. Dessutom erbjuder NPM (Node Package Manager) ett stort ekosystem med ett stort antal paket som kan användas för att utöka funktionaliteten i dina applikationer.

Node.js är också känt för sin enkelhet och flexibilitet. Utvecklare kan snabbt sätta upp en server och börja utveckla applikationer utan att behöva hantera komplexa konfigurationer. Detta gör det till ett utmärkt val för både nybörjare och erfarna utvecklare. Node.js har också ett stort och aktivt community som bidrar med verktyg, bibliotek och support, vilket gör det enklare att hitta lösningar på problem och hålla sig uppdaterad med de senaste trenderna och bästa praxis.

En annan fördel med Node.js är dess förmåga att hantera realtidsapplikationer. Tack vare dess asynkrona natur och event-drivna arkitektur är Node.js idealiskt för applikationer som kräver snabb och effektiv hantering av realtidsdata, såsom chattapplikationer, spel och live-streaming-tjänster.

Sammanfattningsvis är Node.js ett verktyg som används av många stora företag och organisationer världen över för att bygga skalbara och högpresterande nätverksapplikationer. Dess snabbhet, asynkrona I/O-modell, stora ekosystem och enkelhet gör det till ett utmärkt val för utvecklare som vill skapa moderna och effektiva applikationer

För mer information om Node.js och dess fördelar, se följande källor:

1. [Node.js officiella webbplats](https://nodejs.org/en/)
2. [NPM (Node Package Manager)](https://www.npmjs.com/)
3. [Mozilla Developer Network (MDN) Web Docs - Node.js](https://developer.mozilla.org/en-US/docs/Learn/Server-side/Node_server_without_framework)
4. [W3Schools Node.js Tutorial](https://www.w3schools.com/nodejs/)


## AJ 1.2 Express
Beskriv rubriken här

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

