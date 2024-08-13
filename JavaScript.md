# Teorihandboken - JavaScript (JS)
Studerande: Emma Jensen

## JS 1.1 JavaScript / ECMAScript
*JavaScript* är ett dynamiskt, prototypbaserat skriptspråk som används för att skapa interaktiva funktioner på webbsidor. Det används främst för att förbättra användarupplevelsen genom att möjliggöra dynamisk innehållsuppdatering, validering av formulär och interaktiva element som menyer och animationer.
****
 *ECMAScript* är den standardiserade specifikationen för JavaScript. Den styr språkkonstruktion, syntax och grundläggande funktionalitet. *ECMA International*, en standardiseringsorganisation, underhåller ECMAScript-standarden. Viktiga versioner inkluderar ECMAScript 5 (ES5), som introducerade strikta lägen och förbättrade inbyggda metoder, och ECMAScript 6 (ES6), även kallad ES2015, som introducerade betydande nya funktioner som klasser, moduler, let och const, arrow functions med mera.

För att använda ECMAScript-standarder i praktiken, börjar man ofta med att konfigurera en JavaScript-miljö som stöder den önskade versionen av ECMAScript. Moderna webbläsare har stöd för de flesta funktioner i ES6 och senare versioner, men för att säkerställa kompatibilitet kan utvecklare använda transpilers som Babel. Babel omvandlar ES6+ kod till ES5, vilket stöds av äldre webbläsare.

Här är ett exempel på hur man kan skriva och använda en enkel ES6-funktion:

```js
// ES6+ syntax 
const greet = (name) => {
    return `Hej, ${name}!`;
};

console.log(greet('Sebbe')); // Output: Hej, Sebbe!
```

För att säkerställa att koden följer ECMAScript-standarden, kan utvecklare använda verktyg som linters och kodformatörer. ESLint är ett verktyg som hjälper till att identifiera och åtgärda kod som inte följer standarden.

```
// Install ESLint
// npm install eslint --save-dev

// Initialize ESLint configuration
// npx eslint --init
```

***Internt JavaScript*** skrivs direkt i HTML-dokumentet inom ```<script>``` -taggar. Detta är praktiskt för mindre skript eller för att snabbt testa kod.


```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Internt JavaScript</title>
    <script>
        function showMessage() {
            alert('Hej från internt JavaScript!');
        }
    </script>
</head>
<body>
    <button onclick="showMessage()">Klicka här</button>
</body>
</html>
```
Detta hade visats på webb som: 
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Internt JavaScript</title>
    <script>
        function showMessage() {
            alert('Hej från internt JavaScript!');
        }
    </script>
</head>
<body>
    <button onclick="showMessage()">Klicka här</button>
    <br>
</body>
</html>
Msg: 'Hej från internt JavaScript!'
<br><br>

***Externt JavaScript*** skrivs i separata .js-filer och inkluderas i HTML-dokumentet med hjälp av <script src="path/to/file.js"></script>. Detta är praktiskt för att hålla HTML-koden ren och för att återanvända skript över flera sidor.

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Externt JavaScript</title>
    <script src="script.js"></script>
</head>
<body>
    <button onclick="showMessage()">Klicka här</button>
</body>
</html>

```

```js
function showMessage() {
    alert('Hej från externt JavaScript!');
}
````

Detta hade visats på webb som:
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Externt JavaScript</title>
    <script src="script.js"></script>
</head>
<body>
    <button onclick="showMessage()">Klicka här</button>
    <br>
</body>
</html>
Msg: 'Hej från externt JavaScript!'
<br><br>

JavaScript skiljer sig från många andra programmeringsspråk eftersom det är ett tolkat språk, vilket innebär att koden körs direkt av webbläsaren utan att behöva kompileras. Detta gör det snabbt och flexibelt, men kan också leda till problem med prestanda och säkerhet om det inte används korrekt. Med moderna JavaScript-motorer som V8 (som används i Google Chrome och Node.js) har prestanda och möjligheterna för språket förbättrats avsevärt.

Att skriva JavaScript-kod som följer ECMAScript-standarden innebär att använda den syntax och de funktioner som standarden föreskriver. För utvecklare innebär detta att man kan skriva kod som fungerar konsekvent över olika plattformar och webbläsare, vilket i sin tur förbättrar både utvecklingsupplevelsen och slutanvändarens upplevelse.

JavaScript och ECMAScript utvecklas ständigt, med nya versioner som släpps regelbundet för att förbättra språkets funktionalitet och prestanda. Detta gör det möjligt för utvecklare att dra nytta av de senaste teknologierna och bästa praxis för att bygga moderna webbapplikationer. Med de senaste uppdateringarna i ECMAScript-standarderna kan utvecklare utnyttja nya funktioner som async/await för asynkron programmering, decorators för metaprogrammering och mycket mer.

**Summering**: Sammanfattningsvis är ECMAScript en viktig del av JavaScript som definierar hur språket fungerar och utvecklas. Genom att följa ECMAScript-standarderna kan utvecklare skapa robusta, effektiva och framtidssäkra webbapplikationer.

---


## JS 1.2 JavaScript-ramverk och -bibliotek
JavaScript-ramverk och -bibliotek är verktyg som gör det enklare att utveckla webbapplikationer. Ramverk ger en struktur och riktlinjer för hur man bygger applikationer, medan bibliotek innehåller färdiga funktioner och komponenter för att lösa specifika problem.


#### Ramverk 
***Angular:*** Utvecklat av Google och är super för att bygga stora, dynamiska applikationer. 
Angular använder TypeScript, vilket innebär att du får en hel del stöd av typen och kan undvika vissa typer av buggar. 
Den har tvåvägsdatabindning, vilket betyder att när du ändrar något i modellen så uppdateras vyn automatiskt och vice versa. 
Du bygger applikationer med komponenter, vilket gör det lätt att återanvända delar av koden.


***React:*** Skapat av Facebook och är perfekt för att bygga användargränssnitt.
 React delar upp applikationen i små delar som kallas komponenter, vilket gör koden mer hanterbar. 
 Det använder enkelriktad datatrafik, så data flödar i en riktning, vilket kan göra det lättare att förstå hur data rör sig genom din applikation. 
 React använder en virtuell DOM *(JS 1.5)* som gör att uppdateringar blir snabba och effektiva.

***Vue.js*** är ett progressivt ramverk, vilket betyder att du kan införa det gradvis i ett projekt. Vue kombinerar det bästa av Angular och React, och är både flexibelt och lätt att lära sig pga sin enkla syntax, och är bra för både små och stora projekt.



#### Bibliotek
***jQuery*** gör det enkelt att välja och manipulera DOM-element. Med jQuery kan du skriva kort och koncis kod, vilket gör den lätt att läsa och underhålla.
Det hjälper också till med att hantera skillnader mellan olika webbläsare, så att din kod fungerar överallt. 
jQuery gör det också enkelt att binda och hantera events som click, mouseover och keypress. 
Dessutom kan du skapa både enkla och komplexa animationer för att förbättra användarupplevelsen. 
En av de bästa sakerna med jQuery är hur det förenklar asynkrona HTTP requests med AJAX, vilket gör det lättare att ladda och skicka data utan att behöva ladda om sidan.

---

## JS 1.3 Promises
Promises inom JavaScript hanterar asynkrona operationer. En promise representerar ett värde som kanske inte är tillgängligt ännu men som kommer att vara det i framtiden. En promise kan befinna sig i ett av tre tillstånd: väntande (pending), uppfylld (fulfilled) eller avvisad (rejected).

När en promise skapas, utförs den asynkrona operationen. Beroende på resultatet övergår promisen till antingen uppfylld eller avvisad. När tillståndet ändras, exekveras motsvarande hanterare som har bundits till promisen. Den största fördelen med att använda promises är att de gör koden mer läsbar och underhållbar jämfört med traditionella callback-funktioner Callback-funktioner kan ofta leda till vad som kallas "callback hell", där kodens indragningar blir så djupt nästlade att den blir svår att läsa och förstå.

En promise skapas med hjälp av Promise-konstruktorn, som tar en funktion med två parametrar: resolve och reject. 

```js
let myPromise = new Promise((resolve, reject) => {
    let success = true; 
    if (success) {
        resolve("Operationen lyckades!");
    } else {
        reject("Operationen misslyckades!");
    }
});
```
myPromise.then((message) => {
    console.log(message);
}).catch((error) => {
    console.log(error);
});
```


## JS 1.4 OOP i JavaScript
Objektorienterad programmering (OOP) i JavaScript innebär att man organiserar koden i objekt som innehåller både data och funktioner. JavaScript använder en prototypbaserad arvmodell, vilket skiljer sig från klassbaserade språk som Java eller C++. I en prototypbaserad modell ärver objekt direkt från andra objekt.

Med ES6 introducerades klasser till prototypbaserat arv, vilket gör det enklare att definiera och arbeta med objektorienterade strukturer. Klasser i JavaScript är faktiskt funktioner som fungerar som konstruktörer för objekt och kan definiera både instansmetoder och statiska metoder.

En klass definieras med nyckelordet class, och en konstruktor definieras med nyckelordet constructor. Här är ett exempel på hur man definierar och använder en klass i JavaScript:

```js
class Person {
    constructor(name, age) {
        this.name = name;
        this.age = age;
    }

    greet() {
        console.log(`Hej, jag heter ${this.name} och jag är ${this.age} år gammal.`);
    }

    static species() {
        return 'Homo sapiens';
    }
}

let person1 = new Person('Alice', 30);
person1.greet();
console.log(Person.species());
```
I exemplet definieras en klass Person med en konstruktor som tar två parametrar: name och age. En instansmetod greet definieras också, som skriver ut en hälsning. Den statiska metoden species kan anropas direkt på klassen utan att skapa en instans.

Inkapsling innebär att samla data och metoder som manipulerar denna data inom samma enhet, eller klass. Detta gör koden mer modulär och lättare att underhålla eftersom detaljerna i en klass kan döljas från omvärlden och bara relevanta delar exponeras.

Polymorfism gör det möjligt för objekt att behandlas som exempel på deras bas-klass snarare än deras faktiska klass. Detta förenklar interaktionen mellan olika klasser och objekt, vilket gör koden mer dynamisk och anpassningsbar.

Abstraktion innebär att exponera endast nödvändiga detaljer och dölja implementeringsdetaljer. Genom att använda abstrakta klasser och gränssnitt kan utvecklare definiera gemensamma egenskaper och beteenden utan att avslöja komplexa implementationer. Detta leder till tydligare och mer fokuserad kod, där endast relevanta delar av en klass eller ett objekt är synliga för användaren.

exempel på inkapsling och polymorfism:

```js
class Animal {
    constructor(name) {
        this.name = name;
    }

    speak() {
        console.log(`${this.name} makes a noise.`);
    }
}

class Dog extends Animal {
    speak() {
        console.log(`${this.name} barks.`);
    }
}

class Cat extends Animal {
    speak() {
        console.log(`${this.name} meows.`);
    }
}

let dog = new Dog('Rex');
let cat = new Cat('Whiskers');

dog.speak(); // Output: Rex barks.
cat.speak(); // Output: Whiskers meows.

function makeAnimalSpeak(animal) {
    animal.speak();
}

makeAnimalSpeak(dog); // Output: Rex barks.
makeAnimalSpeak(cat); // Output: Whiskers meows.
```

Ovan har vi en bas-klass Animal och två subklasser Dog och Cat som overrides metoden speak. Funktionen makeAnimalSpeak accepterar vilket djur som helst och anropar dess speak-metod.


## JS 1.5 DOM-manipulation
Document Object Model (DOM) är en programmeringsgränssnitt för HTML och XML-dokument. Det representerar dokumentet som en trädstruktur där varje nod är en del av dokumentet, såsom element, attribut och text.
DOM gör det möjligt för programmerare att interagera med och manipulera dokumentets struktur, stil och innehåll dynamiskt.

JavaScript används för att manipulera DOM för att dynamiskt uppdatera innehållet och utseendet på en webbsida. 

Genom att använda metoder som getElementById, querySelector, appendChild och removeChild kan utvecklare lägga till, ändra eller ta bort element från dokumentet.

*Hämta ett element med `getElementById `och ändra dess innehåll:*
```js
let element = document.getElementById('myElement');
element.innerHTML = 'Nytt innehåll';
```
*Lägg till ett nytt element med `createElement` och `appendChild`:*

```js
let newElement = document.createElement('div');
newElement.innerHTML = 'Jag är ett nytt element';
document.body.appendChild(newElement);
```

*Ta bort ett element med `removeChild`*
```js
let parentElement = document.getElementById('parentElement');
let childElement = document.getElementById('childElement');
parentElement.removeChild(childElement);
```
DOM-manipulation gör det möjligt att skapa dynamiska och interaktiva webbsidor, där innehåll kan uppdateras utan att hela sidan behöver laddas om. Detta förbättrar användarupplevelsen genom att ge snabb och responsiv interaktion.

Ett vanligt användningsområde för DOM-manipulation är att hantera händelser som från användaren. Genom att binda event listeners till element kan utvecklare skapa interaktivitet på sina webbsidor.

*Här binder vi ett click event till en knapp med id myButton. När knappen klickas visas en alert.*
```js 
let button = document.getElementById('myButton');
button.addEventListener('click', () => {
    alert('Button was clicked!');
});
```

Modern JavaScript erbjuder också verktyg som gör DOM-manipulation enklare och mer effektiv. Exempel på sådana verktyg är jQuery och moderna ramverk som React och Vue.js.
Dessa verktyg och ramverk tar bort mycket av den komplexitet som kommer med direkt DOM-manipulation och erbjuder mer deklarativa sätt att bygga användargränssnitt.

***jQuery*** är ett JavaScript-bibliotek som gör det enklare att välja och manipulera DOM-element. Med jQuery kan du skriva kort och koncis kod, vilket gör den lätt att läsa och underhålla.
 Det hjälper också till med att hantera skillnader mellan olika webbläsare, så att koden fungerar överallt.

 ```js
 // Ändra innehållet i ett element 
$('#myElement').html('Nytt innehåll');

// Lägg till ett nytt element
$('<div>Jag är ett nytt element</div>').appendTo('body');

// Ta bort ett element
$('#childElement').remove();
```


## JS 1.6 HTTP-requests
HTTP-requests gör det möjligt att hämta data från och skicka data till en server.  Detta kan göras med hjälp av XMLHttpRequest-objektet eller Fetch API för att skapa dynamiska och interaktiva webbapplikationer som kan kommunicera med backend-tjänster utan att behöva ladda om sidan.

*XMLHttpRequest* (XHR) är ett gammalt men bra verktyg för att göra HTTP-förfrågningar. Här är ett exempel på hur man använder XMLHttpRequest för att hämta data från en server:
```js
let xhr = new XMLHttpRequest();
xhr.open('GET', 'https://api.example.com/data', true);
xhr.onload = function() {
    if (xhr.status === 200) {
        console.log(xhr.responseText);
    } else {
        console.error('Ett fel uppstod: ' + xhr.status);
    }
};
xhr.send();
```
*Här skapas en ny XMLHttpRequest, öppnas en GET-förfrågan till en API-endpoint, och skickas förfrågan. När svaret har laddats, loggas det ut i konsolen om statuskoden är 200 (OK).*

*Fetch API* är ett modernt gränssnitt som ger ett enklare och mer kraftfullt sätt att göra HTTP-förfrågningar. Det returnerar en promise som löser upp till svaret från servern, vilket gör det lättare att arbeta med asynkrona operationer.
```jsfetch('https://api.example.com/data')
    .then(response => {
        if (!response.ok) {
            throw new Error('Nätverksresponsen var inte OK');
        }
        return response.json();
    })
    .then(data => {
        console.log(data);
    })
    .catch(error => {
        console.error('Det uppstod ett problem med fetch operationen:', error);
    });
```
*Här skickas en GET-förfrågan till en API-endpoint, svaret konverteras till JSON, och loggas. Om det uppstår ett fel, fångas det med catch och loggar ett felmeddelande.*

***Async/await*** används för att hantera asynkrona operationer som gör koden mer läsbar och lättare att skriva. Det är ett syntactic sugar[^1] över promises som ger ett strukturerat sätt att skriva asynkron kod.

[^1]: *"Syntactic sugar"* är syntax i ett programmeringsspråk som gör koden lättare att läsa och skriva utan att tillföra nya funktioner.

```js
async function fetchData() {
    try {
        let response = await fetch('https://api.superbradata.com/data');
        if (!response.ok) {
            throw new Error('Nätverksresponsen inte OK');
        }
        let data = await response.json();
        console.log(data);
    } catch (error) {
        console.error('Det uppstod ett problem med fetch operationen:', error);
    }
}

fetchData();
```
*Här definieras en asynkron funktion fetchData som använder await för att vänta på att fetch-operationen och JSON-konverteringen ska slutföras innan resultatet loggas. Felsökning hanteras med en try...catch-block.*

Med HTTP-förfrågningar kan utvecklare bygga applikationer som interagerar med externa tjänster, API
och servrar för att hämta och skicka data, vilket möjliggör dynamiska och data-drivna applikationer.

## JS 1.7 Lexical scope
Lexical scope i JavaScript hänvisar till hur variabler och block är organiserade och åtkomliga i koden. 
Scope definieras av kodens struktur och avgör varifrån variabler kan nås.

## JS 1.8 Event handling
Beskriv rubriken här

## JS 1.9 Prototype inheritance
Beskriv rubriken här

## JS 1.10 Higher-order functions
Beskriv rubriken här

## JS 1.11 Single-thread programming
Beskriv rubriken här

## JS 1.12 OAuth från frontend
Beskriv rubriken här

## JS 1.13 Websockets
Beskriv rubriken här

