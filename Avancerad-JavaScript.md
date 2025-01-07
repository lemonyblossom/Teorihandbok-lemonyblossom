# Teorihandboken - Avancerad JavaScript (AJ)
Studerande: Emma Jensen

## AJ 1.1 Node.js
Node.js är en plattform som gör det möjligt att köra JavaScript på serversidan istället för enbart i webbläsaren. Den släpptes 2009 av Ryan Dahl och har sedan dess blivit väldigt populär bland utvecklare. Till skillnad från vanliga program som körs i en webbläsare, används Node.js för att bygga både små och stora webbapplikationer.
Grunden i Node.js är en snabb JavaScript-motor som kallas V8, vilken också används i webbläsaren Chrome.

En av de största fördelarna med Node.js är att den är byggd för att vara snabb och effektiv. Den använder sig av asynkron programmering, vilket betyder att den kan hantera många saker samtidigt utan att vänta på att varje uppgift ska bli klar.
I traditionella system kan varje begäran till servern blockera resten av arbetet tills den är klar, men med Node.js kan flera begärningar hanteras samtidigt, vilket gör systemet mycket snabbare och mer effektivt.

Node.js kommer också med ett stort ekosystem genom npm (Node Package Manager), vilket är en samling av miljontals paket och moduler som gör det enklare att utveckla applikationer.
Det betyder att utvecklare inte behöver bygga allt från grunden, utan kan använda färdiga lösningar och verktyg.

En annan fördel är att Node.js är plattformsoberoende. Det fungerar på olika operativsystem som Windows, macOS och Linux, vilket gör det enkelt att utveckla och distribuera applikationer på flera plattformar utan stora ändringar i koden.

Sammanfattningsvis är Node.js en effektiv och flexibel plattform som gör det enklare att bygga skalbara och snabbare webbapplikationer. Den används av många stora företag och utvecklare världen över och erbjuder ett enkelt sätt att skapa både små och stora lösningar.

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
    const user = { id: 1, name: 'Lemony Blossom' }; // Här hämtas användardata från en databas
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

// Eller tillåt endast specifika domäner
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


Sammanfattningsvis är säkerhet en avgörande del av alla webbapplikationer, och Express gör det lätt att implementera autentisering, skydda rutter och lägga till säkerhetsåtgärder som CORS. Genom att använda middleware kan man snabbt och effektivt hantera dessa uppgifter, vilket gör att applikatioenn blir både säker och skalbar.

---

## AJ 1.3 Progressive Web Apps
Progressive Web Apps (PWA) är en typ av webbapplikation som kombinerar det bästa från webb och mobilappar. De använder moderna teknologier för att ge offline-stöd, push-notiser och möjligheten att installera appen direkt på enhetens hemskärm.

De viktigaste egenskaperna hos en PWA är:

- Responsivitet - De fungerar lika bra på olika enheter och skärmstorlekar.
- Offline-funktionalitet - Genom Service Workers kan resurser cachelagras lokalt.
- Installationsbar - Man kan lägga till appen på hemskärmen utan att använda en appbutik.

För att skapa en PWA använder man sig av teknologier som Service Workers och manifestfiler. Manifestet innehåller metadata som namn, ikoner och startadress, medan Service Workers tar hand om saker som caching och bakgrundsprocesser.

PWA ger också en snabbare användarupplevelse, vilket är avgörande för att hålla användare engagerade och minska risken att användare lämnar appen. 
Eftersom PWA:er fungerar offline eller med begränsad nätverksåtkomst tack vare cachelagring genom Service Workers, kan användare fortsätta interagera med appen även om de inte har en aktiv internetanslutning. Detta gör det särskilt användbart för användare i områden med svaga eller instabila nätverksanslutningar.

En annan stor fördel med PWA är att de stödjer push-notiser, vilket ger företag möjlighet att återengagera användare genom att skicka påminnelser och uppdateringar. Push-notiser kan hjälpa till att öka användaraktiviteten och påminna användarna om att återvända till appen.

PWA:er fungerar också väl på alla typer av enheter, vilket innebär att de kan anpassas till både smartphones, surfplattor och stationära datorer. Detta gör det möjligt för företag att erbjuda en enhetlig upplevelse oavsett plattform.

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

PWA är ett smart val för företag som vill förbättra användarupplevelsen utan att behöva utveckla separata mobil- och webbappar. Tack vare snabb laddning och offline-stöd är PWA ett sätt att skapa moderna applikationer som är långvarigt hållbara. 

---

## AJ 1.4 Typningssystem för Javascript (ex TypeScript, Flow)
JavaScript är ett dynamiskt typat språk, vilket innebär att man inte behöver specificera datatyper för variabler. Det gör språket väldigt flexibelt, men kan också leda till problem, särskilt när man arbetar med större projekt. Eftersom typer inte är fasta kan det vara svårt att veta vilka typer av data en funktion eller variabel ska hantera, och det kan orsaka fel som inte upptäcks förrän koden körs. För att förbättra detta finns det statiska typningssystem som TypeScript och Flow, som gör att utvecklare kan definiera och kontrollera datatyper redan under utvecklingen.

#### TypeScript
TypeScript är ett superset av JavaScript, vilket betyder att det är baserat på JavaScript men med tillägg av funktioner, som statisk typning. TypeScript används för att få mer förutsägbar kod och för att upptäcka fel tidigare i utvecklingsprocessen. När du använder TypeScript skriver du typdeklarationer för funktioner och variabler, och dessa kontrolleras vid kompilering. Om något inte stämmer med typerna får du ett felmeddelande direkt i editorn. Detta minskar risken för buggar som kan vara svåra att hitta i stora kodbaser.

```ts
function greet(name: string): string {
    return `Hej, ${name}!`;
}

console.log(greet('Lemony Blossom')); //korrekt
console.log(greet(123)); // fel, inkorrekt typat
```

TypeScript är särskilt användbart i större team och projekt, där många utvecklare samarbetar och där det är viktigt att ha en tydlig struktur och typdefinition. TypeScript erbjuder dessutom funktioner som gränssnitt (interfaces) och generiska typer, vilket gör koden både mer flexibel och återanvändbar.

#### Flow
Flow är ett annat statiskt typningssystem, utvecklat av Facebook. Till skillnad från TypeScript är Flow inte ett superset av JavaScript, vilket betyder att du kan använda Flow utan att ändra på JavaScript-syntaxen. Det gör Flow enklare att införa gradvis i existerande projekt. Med Flow kan du lägga till typkontroller utan att behöva skriva om hela koden. Typdefinitionerna i Flow görs ofta via kommentarer i koden, vilket innebär att du inte måste ändra på själva kodens struktur.

Flow använder annoteringar i form av kommentarer för att specificera typer:

```js
// @flow
function square(n: number): number {
    return n * n;
}

console.log(square(4)); // korrekt
console.log(square('a')); // fel
```

Flow är bra för utvecklare som vill ha ett mer flexibelt sätt att införa typkontroll i sina JavaScript-projekt. Eftersom Flow inte kräver att du skriver om stora delar av din kodbas, är det ett bra alternativ om du har ett pågående projekt och vill förbättra kodens kvalitet utan att behöva göra omfattande förändringar.

#### Sammanfattning
Både TypeScript och Flow hjälper till att förbättra kodens förutsägbarhet och felsökning, men de gör det på lite olika sätt. TypeScript kräver att du skriver typdeklarationer och kan ge mer detaljerad typkontroll, vilket gör det bra för större projekt och team. Flow är enklare att införa i befintliga projekt och fungerar bra om du vill ha ett mer gradvis tillvägagångssätt för att förbättra kodens typkontroll. Båda verktygen erbjuder fördelar som snabbare felsökning, bättre autokomplettering i editorer och en mer robust kodbas.

---


## AJ 1.5 Funktionell programmering i JavaScript
Funktionell programmering är en stil inom programmering där man fokuserar på att använda funktioner för att lösa problem och undviker att förändra data eller tillstånd. Istället för att hela tiden uppdatera värden och objekt, behandlar man data som "oföränderlig", vilket kan göra koden enklare att förstå och underhålla. JavaScript stödjer funktionell programmering genom att låta funktioner vara första klassens objekt, vilket innebär att de kan användas precis som vanliga variabler. Man kan till exempel skicka funktioner som argument till andra funktioner eller få tillbaka funktioner som resultat

#### Higher order functions
En viktig del av funktionell programmering är higher order functions (HOF). En HOF är en funktion som antingen tar en annan funktion som argument eller returnerar en funktion. Ett vanligt exempel på en HOF i JavaScript är map. Den tar en funktion som argument och applicerar den på varje element i en array, vilket gör det enkelt att manipulera data utan att behöva skriva komplicerad looplogik.

Ett exempel på en higher order function är `map`, som tar en funktion som argument och applicerar den på varje element i en array:

```js
const numbers = [1, 2, 3, 4];
const squared = numbers.map(n => n * n);
console.log(squared); // [1, 4, 9, 16]
```
Andra exempel på **HOF** är funktionerna *filter* och *reduce*.

#### Immutabilitet
En annan viktig princip inom funktionell programmering är immutabilitet, vilket betyder att data inte ska ändras när den väl är skapad. Istället för att uppdatera ett objekt, skapar man nya objekt med de förändringar man vill ha. Immutabilitet har flera fördelar, bland annat:

>**Mindre risk för buggar** 
När data inte kan ändras oavsiktligt blir det lättare att följa och förstå flödet i koden.

>**Enklare att testa** 
Eftersom data inte förändras kan man vara säker på att tester inte påverkas av oönskade sidoeffekter.

>**Tråd-säkerhet** 
I flertrådade miljöer, där flera trådar kan försöka komma åt samma data samtidigt, förhindrar immutabilitet att data ändras av en tråd medan en annan läser det.

#### Pure functions
Funktionell programmering uppmuntrar också användningen av pure functions, vilket är funktioner som alltid returnerar samma resultat om de får samma indata. En ren funktion har ingen inverkan på något annat än dess resultat – den har inga biverkningar. Detta gör funktioner förutsägbara och enkla att testa.
```js
function add(a, b) {
    return a + b;
}
console.log(add(2, 3)); // 5
```

Eftersom rena funktioner inte påverkar någon annan del av programmet, blir de lättare att förstå, felsöka och testa. De gör det också enklare att återanvända kod på olika ställen i applikationen.

#### Exempel på högre ordningens funktioner
Som nämnts tidigare finns det flera vanliga *HOF* i JavaScript:

```filter``` Skapar en ny array med de element som uppfyller ett specifikt villkor.
```js
const numbers = [1, 2, 3, 4, 5];
const evenNumbers = numbers.filter(n => n % 2 === 0);
console.log(evenNumbers); // [2, 4]
```

```reduce``` Reducerar en array till enbart ett värde, till exempel genom att summera alla värden i en array.
```js
const numbers = [1, 2, 3, 4];
const sum = numbers.reduce((acc, n) => acc + n, 0);
console.log(sum); // 10
```
Dessa funktioner används när man arbetar med data och behöver göra transformationer på den utan att påverka den ursprungliga datan. 
De gör koden mer deklarativ, vilket innebär att den blir mer readable.

#### Sammanfattning
Funktionell programmering i JavaScript handlar om att skriva kod på ett sätt som gör den mer förutsägbar, testbar och underhållbar. Genom att använda funktioner som första klassens objekt, skriva rena funktioner, och använda högre ordningens funktioner som ```map```, ```filter``` och ```reduce```, kan utvecklare skapa kod som är både effektiv och lätt att förstå.
 Immutabilitet och pure functions gör att koden blir mindre benägen att innehålla buggar och mer förutsägbar, vilket är en stor fördel när man jobbar med större applikationer.

---

## AJ 1.6 Avancerad funktionalitet i ES.next
ES.next, eller ECMAScript 6 och senare versioner, har introducerat många nya funktioner som gör JavaScript mer kraftfullt och lättare att använda.
Dessa nya funktioner förbättrar både kodens läsbarhet och underhållbarhet och gör det möjligt för utvecklare att skriva mer expressiv och effektiv kod.

#### Arrow functions
En av de mest populära och ofta använda funktionerna i ES6 är arrow functions, som gör att funktioner kan skrivas på ett mer kortfattat sätt.De förenklar syntaxen och gör det lättare att läsa och skriva funktioner.

I traditionella funktioner måste man använda function-nyckelordet, men med arrow functions kan man skriva funktioner på en rad:

```js
// Traditionell funktion
const add = function(a, b) {
    return a + b;
};

// Arrow function
const add = (a, b) => a + b;
console.log(add(2, 3)); // 5
```
Arrow functions har även en annan viktig fördel: de binder inte sitt eget ```this```-värde, vilket kan förenkla hanteringen av funktioner som används i objekt och klasser.

####  Destructuring
Destructuring är en funktion i ES6 som gör att man kan extrahera värden från objekt eller arrayer på ett mer intuitivt sätt, vilket gör koden mer readable.

*Exempel för obejkt:*
```js
const person = {
    name: 'Lemony Blossom',
    age: 31,
    occupation: 'developer student'
};

const { name, age } = person;
console.log(name); // Lemony Blossom
console.log(age);  // 31
```

*Exempelt för arrayer*
```js
const numbers = [1, 2, 3, 4];
const [first, second] = numbers;
console.log(first);  // 1
console.log(second); // 2
```

Destructuring är användbart när man har komplexa objekt eller arrayer och vill extrahera specifika värden utan att behöva skriva upprepade referenser.

####  Template literals (Mallsträngar)
Template literals gör string handling mycket enklare och mer flexibel.
Med det kan man enkelt infoga variabler eller expressions i en string, utan att behöva använda string-concatenations eller +-operators.

```js
const name = 'Lemony Blossom';
const age = 31;

// Traditionellt
const greeting = 'Hello, my name is ' + name + ' and I am ' + age + ' years old.';

// Med template literals
const greeting = `Hello, my name is ${name} and I am ${age} years old.`;
console.log(greeting); // Hello, my name is Lemony Blossom and I am 31 years old.
```
Template literals gör koden mycket lättare att läsa, särskilt när man arbetar med längre strings som innehåller variabler och expressions.

#### Spread och Rest Operators
**Spread operator** (```...```) gör det enkelt att kopiera och kombinera objekt eller arrayer, medan rest operator används för att samla argument till en funktion eller för att extrahera en del av ett objekt eller array.

*Spread operator- för arrays och objekt*
```js
const arr1 = [1, 2, 3];
const arr2 = [...arr1, 4, 5]; // copy arr1 och addera new element
console.log(arr2); // [1, 2, 3, 4, 5]

const obj1 = { a: 1, b: 2 };
const obj2 = { ...obj1, c: 3 }; // copy obj1 och addera new key
console.log(obj2); // { a: 1, b: 2, c: 3 }
```
*Rest operator - för funktioner och objekt*

```js
// För funktioner
function sum(...numbers) {
    return numbers.reduce((acc, num) => acc + num, 0);
}

console.log(sum(1, 2, 3, 4)); // 10

// För objekt
const { a, ...rest } = { a: 1, b: 2, c: 3 };
console.log(a); // 1
console.log(rest); // { b: 2, c: 3 }
```
Både **spread** och **rest** gör hantering av data mycket mer flexibel och lättförståelig, särskilt i situationer där man behöver kombinera eller extrahera delar av objekt eller arrayer.

#### Klasser och Inheritance (Arv)
ES6 introducerade ett mer strukturerat sätt att arbeta med objektorienterad programmering genom *klasser*.
Med klasser kan du definiera objekt och dess beteenden på ett mer organiserat sätt än tidigare

```js
class Appliance {
    constructor(name) {
        this.name = name;
    }

    turnOn() {
        console.log(`${this.name} is now on.`);
    }
}

class Toaster extends Appliance {
    turnOn() {
        console.log(`${this.name} is toasting bread.`);
    }
}

const toaster = new Toaster('Philips Toaster');
toaster.turnOn(); // Philips Toaster is toasting bread.
```
Genom att använda klasser kan vi definiera funktioner som delar egenskaper med andra objekt, vilket gör det lättare att skapa komplexa applikationer.

#### Async/Await (Asynkrona funktioner)
Att hantera asynkron kod har länge varit en utmaning i JavaScript, men med async/await blir det betydligt enklare. async gör en funktion asynkron, och await används för att vänta på att en asynkron operation ska slutföras innan koden fortsätter.

```js
function fetchData() {
    return new Promise(resolve => {
        setTimeout(() => {
            resolve('Data fetched');
        }, 2000);
    });
}

async function getData() {
    const result = await fetchData();
    console.log(result);
}

getData(); // Data fetched
```
Med ```async/await``` ser koden ut att köras sekventiellt, vilket gör den mer linjär och lättare att följa. Trots detta sker de långsamma operationerna (som nätverksanrop eller databaskopplingar) faktiskt asynkront i bakgrunden. 
Det innebär att JavaScript inte blockerar hela programflödet medan det väntar på att en långsam process ska avslutas, vilket gör att andra uppgifter kan fortsätta köras samtidigt.




#### Sammanfattning
ES.next har gjort JavaScript mer flexibel och lättare att använda.
Arrow-functions, destructuring, template literals, spread och rest operators, klasser och async/await har alla bidragit till att göra koden mer läsbar och lättare att underhålla.
Genom att använda dessa funktioner kan utvecklare skriva kod som är mer uttrycksfull och effektiv, vilket leder till att utvecklingsprocessen blir enklare och snabbare.

---

## AJ 1.7 JavaScript i integrerade system
JavaScript är inte bara till för webbsidor och appar. Det används också i integrerade system, där hårdvara och mjukvara samverkar. 
Dessa system finns överallt, från smarta hem till industriella tillämpningar. Internet of Things (IoT) är ett av de vanligaste områdena där JavaScript spelar en stor roll. 
IoT-enheter inkluderar saker som termometrar, lampor eller sensorer som skickar data till internet och kan styras via appar eller servrar. Ett exempel är en smart termostat som justerar temperaturen automatiskt eller via fjärrstyrning

Med Node.js kan utvecklare bygga program som kommunicerar med sensorer och andra enheter. JavaScript gör det enkelt att hantera data från enheter och skicka information vidare till en server eller annan enhet. Ett exempel kan vara en temperatursensor som kontinuerligt skickar mätvärden till en server för att övervaka klimatet i ett rum.

JavaScript används också för att skapa gränssnitt där du kan styra smarta hem-enheter, som lampor och lås, från en app eller webbsida. Genom protokoll som MQTT kan enheter kommunicera med varandra eller med en central server, vilket gör det möjligt att automatisera uppgifter, som att tända lampor när det blir mörkt eller låsa dörrar när ingen är hemma.

| Enhet                  | Funktion                                                                                 | Exempel                        | JavaScript-användning                                                                                                                                             |
|------------------------|-----------------------------------------------------------------------------------------|--------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Smarta lampor**      | Tända, släcka eller ändra ljusstyrka och färg via en app eller röststyrning.            | Philips Hue, IKEA TRÅDFRI      | Med bibliotek som `node-hue-api` kan du kontrollera Philips Hue-lampor direkt från en Node.js-applikation.                                                       |
| **Smarta termostater** | Justera hemmets temperatur automatiskt baserat på tid, närvaro eller väder.             | Nest, Ecobee                   | Termostater kan styras via API:er för att ändra temperaturen, läsa av energiförbrukning eller skapa automatiska regler.                                          |
| **Smarta högtalare**   | Spela musik, svara på frågor och styra andra enheter via röststyrning.                  | Amazon Echo, Google Nest       | Bygg egna röststyrda funktioner eller integrationer med enheter som Alexa genom AWS Lambda eller Alexa Skills Kit i JavaScript.                                  |
| **Smarta lås**         | Lås och lås upp dörrar via app, röststyrning eller ge tillfälliga koder till gäster.    | August Smart Lock, Yale Assure | Kontrollera lås med hjälp av deras API:er för att ge fjärråtkomst eller logga användning.                                                                         |
| **Övervakningskameror**| Spela in och strömma video från hemmet för att öka säkerheten.                          | Ring, Arlo, Nest Cam           | Integrera kameror med smarta system för att skicka notifieringar eller hantera videoströmmar via Node.js.                                                        |
| **Smarta uttag**       | Kontrollera eluttag via en app för att slå av och på anslutna apparater.                | TP-Link Kasa, Belkin Wemo      | Programmera scheman för uttag eller kontrollera energiförbrukning med bibliotek och API:er.                                                                      |
| **Robotdammsugare**    | Automatisk städning av golv, som kan schemaläggas eller styras via en app.              | iRobot Roomba, Roborock        | Anpassa städscheman eller hantera kartor och rutter med tredjepartsbibliotek.                                                                                     |
| **Smarta kylskåp**     | Visa innehållet i kylskåpet, spåra utgångsdatum eller skapa inköpslistor.               | Samsung Family Hub             | Integrera kylskåpet med andra enheter i hemmet via IoT-protokoll som MQTT.                                                                                       |
| **Smarta bevattningssystem** | Styr och schemalägg vattning för trädgården baserat på väder och tid.              | Rachio, Gardena Smart System   | Automatisera bevattning baserat på sensordata som fuktighet och temperatur.                                                                                       |
| **Smarta väderstationer** | Mät temperatur, luftfuktighet och andra väderförhållanden i realtid.                 | Netatmo, Ambient Weather       | Logga väderdata till en databas eller skapa grafer med hjälp av JavaScript-bibliotek.                                                                             |


En av de stora fördelarna med JavaScript är att det fungerar på många plattformar, från enkla mikrokontrollerkort som Arduino till mer avancerade enheter som Raspberry Pi. Dess stora bibliotek av verktyg gör att utvecklare kan bygga både små och stora lösningar på kort tid. Det används därför i allt från hobbyprojekt till komplexa system inom smarta hem och IoT.


#### Arduino - JS
Arduino är en enkel mikrokontrollerplattform (kombination av hårdvarukort och mjukvara) som används för att styra elektronik som lysdioder, motorer och sensorer. Den är särskilt populär för nybörjare och hobbyprojekt tack vare sin användarvänlighet.

Med JavaScript och bibliotek som Johnny-Five kan du programmera Arduino via Node.js. Detta gör det möjligt att hantera hårdvara smidigt och bygga automatiserade system.

**IoT-användning:** Arduino används inom IoT för att hantera uppgifter som att skicka mätdata från sensorer eller styra olika typer av enheter, exempelvis smarta lås eller belysningssystem. Den kan kommunicera med andra system via protokoll som Wi-Fi, Bluetooth eller LoRa, beroende på vilka moduler som används.

Ett vanligt exempel är att använda Arduino för att läsa av data från en temperatur- eller fuktsensor och skicka informationen vidare till en server. En annan typisk användning är att styra en ventil baserat på fuktnivån i jorden, vilket gör den särskilt användbar för smart jordbruk eller miljöövervakning.

#### Raspberry Pi - Js
Raspberry Pi är en inbäddad datorplattform, vilket innebär att den är en komplett dator i miniatyrformat. Den hanterar både mjukvara och hårdvara och kör ett operativsystem (vanligtvis Linux). Detta gör den väl lämpad för mer komplexa IoT-applikationer där beräkningskraft, nätverksanslutning och multitasking är viktigt.

Raspberry Pi används ofta som en hubb för att hantera och styra flera IoT-enheter, bearbeta data lokalt och integrera med molntjänster.


**IoT användning:** Ett vanligt användningsområde är att köra en webbserver för att hantera och visualisera data från anslutna sensorer och enheter. Raspberry Pi kan även bearbeta mer avancerad data, som bildanalys från en kamera för tillämpningar som ansiktsigenkänning eller rörelsedetektering.

En annan vanlig användning är att fungera som en hubb som samlar in data från flera sensorer och vidarebefordrar informationen till en molntjänst för ytterligare analys eller lagring.


## AJ 1.8 Native bundeling av JavaScript för olika operativsystem och enheter
Beskriv rubriken här

