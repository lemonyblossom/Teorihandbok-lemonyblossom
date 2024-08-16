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
```

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

JavaScript och ECMAScript utvecklas ständigt, med nya versioner som släpps regelbundet för att förbättra språkets funktionalitet och prestanda. Med de senaste uppdateringarna i ECMAScript-standarderna kan utvecklare utnyttja nya funktioner som async/await för asynkron programmering, decorators för metaprogrammering och mycket mer.

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

myPromise.then((message) => {
    console.log(message);
}).catch((error) => {
    console.log(error);
});
```

---

## JS 1.4 OOP i JavaScript
Objektorienterad programmering (OOP) i JavaScript innebär att man organiserar koden i objekt som innehåller både data och funktioner. JavaScript använder en prototypbaserad arvmodell, vilket skiljer sig från klassbaserade språk som Java eller C++. I en prototypbaserad modell ärver objekt direkt från andra objekt.
 Det här skiljer sig från klassbaserade språk som Java eller C++, där arv sker genom klasser.

Med ES6 introducerades klasser till JavaScript, vilket ger en mer strukturerad syntax för att definiera och arbeta med objektorienterade strukturer.

En klass definieras med nyckelordet `class`, och en konstruktor definieras med nyckelordet `constructor`. Här är ett exempel på hur man definierar och använder en klass i JavaScript:

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

let person1 = new Person('Emma', 30);
person1.greet();
console.log(Person.species());
```
*Här definieras en klass Person med en konstruktor som tar två parametrar: name och age. En instansmetod greet definieras också, som skriver ut en hälsning. Den statiska metoden species kan anropas direkt på klassen utan att skapa en instans.*

Inkapsling innebär att samla data och metoder som manipulerar denna data inom samma enhet, eller klass. Detta gör koden mer modulär och lättare att underhålla eftersom detaljerna i en klass kan döljas från omvärlden och bara relevanta delar exponeras.

Polymorfism gör det möjligt för objekt att behandlas som exempel på deras bas-klass snarare än deras faktiska klass och förenklar interaktionen mellan olika klasser och objekt, vilket gör koden mer dynamisk och anpassningsbar.

Abstraktion innebär att exponera endast nödvändiga detaljer och dölja implementeringsdetaljer. Genom att använda abstrakta klasser och gränssnitt kan utvecklare definiera gemensamma egenskaper och beteenden utan att avslöja komplexa implementationer. Detta leder till tydligare och mer fokuserad kod.
exempel på inkapsling och polymorfism:

```js
class Vehicle {
    constructor(type) {
        this.type = type;
    }

    move() {
        console.log(`${this.type} is moving.`);
    }
}

class Car extends Vehicle {
    move() {
        console.log(`The car is driving.`);
    }
}

class Boat extends Vehicle {
    move() {
        console.log(`The boat is sailing.`);
    }
}

let car = new Car('Car');
let boat = new Boat('Boat');

car.move(); // Output: The car is driving.
boat.move(); // Output: The boat is sailing.

```

---

## JS 1.5 DOM-manipulation
Document Object Model (DOM) är en programmeringsgränssnitt för HTML och XML-dokument. Det representerar dokumentet som en trädstruktur där varje nod är en del av dokumentet, såsom element, attribut och text.
DOM gör det möjligt för programmerare att interagera med och manipulera dokumentets struktur, stil och innehåll dynamiskt.

JavaScript används för att manipulera DOM för att uppdatera innehållet och utseendet på en webbsida. 

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
DOM-manipulation gör det möjligt att skapa dynamiska och interaktiva webbsidor, där innehåll kan uppdateras utan att hela sidan behöver laddas om. Det förbättrar användarupplevelsen genom att ge snabb och responsiv interaktion.

Ett vanligt användningsområde för DOM-manipulation är att hantera händelser som från användaren. Genom att binda event listeners till element kan utvecklare skapa interaktivitet på sina webbsidor *(JS 1.8)*


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

---

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

---

## JS 1.7 Lexical scope
Lexical scope i JavaScript hänvisar till hur variabler och block är organiserade och åtkomliga i koden. 
Scope definieras av kodens struktur och avgör varifrån variabler kan nås. 

I JavaScript finns två huvudtyper av scope: globalt scope och lokalt scope och det har, som namnen tyder på, olika stora omfång.

Variabler som deklareras utanför en funktion har global scope och kan nås var som helst i koden. 
Dessa variabler finns i det globala objektet (window i webbläsare eller global i Node.js).

Variabler som deklareras inuti en funktion har lokatl scope och kan endast nås inom den funktionen och hjälper till att undvika att namn krockar och att hålla koden organiserad.

```js
let globalVar = 'Global variabel, hejhej!';

function lilpFunction() {
    let localVar = 'Lokal Variabel, hejhej!';
    console.log(globalVar); // 'Global variable, hejhej!'
    console.log(localVar);  // 'Local Variable, hejhej!'
}

lilpFunction();
console.log(localVar); // ReferenceError: localVar is not defined
```
*Här är globalVar global och kan nås både inom och utanför funktionen lilpFunction. localVar är lokal för lilpFunction och kan inte nås utanför den funktionen.*

Med *ES6* introducerades *block-scope* variabler med `let` och `const`. Dessa variabler är endast tillgängliga inom det block där de deklareras, vilket ger en mer granular kontroll över variablers livstid och tillgänglighet.

```js
function blockScopeExample() {
    if (true) {
        let blockVar = 'Ett block-scope';
        const blockConst = 'Också ett block-scope';
        console.log(blockVar); // 'Ett block-scope'
        console.log(blockConst); // 'Också ett block-scope'
    }
    console.log(blockVar); // ReferenceError: blockVar is not defined
    console.log(blockConst); // ReferenceError: blockConst is not defined
}

blockScopeExample();
```
*blockVar och blockConst är endast tillgängliga inom if-blocket där de deklareras och kan inte nås utanför det.*

##### Note to self
- Undvik att deklarera för många globala variabler. Globala variabler kan lätt orsaka namnkollisioner och svårare felsökning eftersom de är tillgängliga överallt i koden. Använd istället lokala och block-scoped variabler för att begränsa variablernas synlighet.

- Med let och const från ES6 kan du deklarera variabler med block-scope. Det ger bättre kontroll över variablers tillgänglighet och hjälper till att undvika oavsiktliga variabelöverskrivningar.

- Variabler deklarerade med var har funktion-scope, vilket kan leda till oväntade beteenden om de används inom block som if eller loopar. Använd let och const för att undvika dessa problem.

- Deklarera variabler så nära deras användning som möjligt och använd meningsfulla namn, vilket gör koden mer läsbar och underlättar underhåll.

- När funtioiner defineras inom andra funktioner, kom ihåg att den inre funktionen har tillgång till variablerna i den yttre funktionen. Detta kan vara effektivt men kan också leda till komplexa beroenden om det inte hanteras korrekt.

---

## JS 1.8 Event handling
Event handling refererar till processen att fånga och reagera på händelser som sker i webbläsaren.
Händelser kan vara allt från användarinteraktioner som klick och tangenttryckningar till systemhändelser som laddning av en sida eller ändringar i dokumentets tillstånd.
I JavaScript kan händelser hanteras genom att binda event listeners till HTML-element. 

Det här hanteras vanligtvis med metoden addEventListener, som tillåter utvecklare att specifikt definiera vilken typ av händelse de vill lyssna på och vilken funktion som ska köras när händelsen inträffar.

*Ett click event binds till en knapp med id knappKnapp. Klick visar en alert.*
```js 
let button = document.getElementById('knappKnapp');
button.addEventListener('click', () => {
    alert('Button was clicked!');
});
```

Det finns många händelser som kan fångas upp i Javascrirpt, såsom click (ovan), mouseover, mouseout, keydown, keyup, submit, och många fler.
För var händelse finns specifika egenskaper och metoder som kan användas för att få detaljerad information om händelsen.

Något man kan göra med händelsehantering är att ändra stil eller innehåll på en sida som svar på användarens interaktioner.
Här är ett exempel på hur man ändrar bakgrundsfärgen på ett element när muspekaren förs över det och återställer färgen när muspekaren lämnar elementet:

```js
let element = document.getElementById('myElement');
element.addEventListener('mouseover', () => {
    element.style.backgroundColor = 'pink';
});
element.addEventListener('mouseout', () => {
    element.style.backgroundColor = '';
});
```

##### Viktigt att tänka på vid event handling
Se till att undvika minnesläckor genom att ta bort event listeners när de inte längre behövs. Använd removeEventListener för att avregistrera händelser och var försiktig med att skapa för många listeners på samma element för att undvika prestandaproblem.

Prestandaproblem kan uppstå vid event handling på grund av:

**För många event listeners**: Att lägga till många listeners, särskilt på händelser som mousemove eller scroll, kan göra webbläsaren långsam.

**Komplexa event handlers**: Tung logik i event handlers kan göra gränssnittet oresponsivt.

**Minnesläckor**: Om event listeners inte tas bort korrekt kan de leda till minnesläckor genom att hålla kvar referenser till DOM-element.

**Direkta listeners**: Att binda listeners till många individuella element istället för att använda event delegation kan vara ineffektivt.

```js
document.getElementById('parentElement').addEventListener('click', (event) => {
    if (event.target && event.target.matches('.childElement')) {
        console.log('Child element clicked');
    }
});
```
*Event delegation binder en listener till ett parent element och hanterar händelser för dess children och är mer effektivt än individuella listeners.*

---

## JS 1.9 Prototype inheritance
Prototypbaserat arv i JavaScript innebär att ett objekt kan ärva egenskaper och metoder från andra objekt.
Till skillnad från klassbaserade språk som använder klasser för att definiera objektens struktur och arv, använder JavaScript prototyper för att skapa arv. Varje JavaScript-objekt har en inbyggd egenskap som kallas prototype, vilket refererar till ett annat objekt som det ärver från.

När man försöker få tillgång till en egenskap eller metod på ett objekt, och den egenskapen inte finns direkt på objektet, kommer JavaScript att leta efter den i objektets prototypkedja. Denna kedja fortsätter uppåt tills slutet av kedjan nås (där prototypen är null).

```js 
let animal = {
    speak() {
        console.log('The animal makes a sound.');
    }
};

let dog = Object.create(animal);
dog.bark = function() {
    console.log('The dog barks.');
};

dog.speak(); // Output: The animal makes a sound.
dog.bark();  // Output: The dog barks.
```
*Exempel: Hur man skapar ett objekt och använder prototypbaserat arv:*

```js
class Animal {
    constructor(name) {
        this.name = name;
    }

    speak() {
        console.log(`${this.name} makes a sound.`);
    }
}

class Dog extends Animal {
    speak() {
        console.log(`${this.name} barks.`);
    }
}

let dog = new Dog('Rex');
dog.speak(); // Output: Rex barks.
```
*Med ES6 introducerades klasser, vilket gjorde det enklare att definiera och arbeta med arvstrukturer*

```js
function Person(name) {
    this.name = name;
}

Person.prototype.greet = function() {
    console.log(`Hej, jag heter ${this.name}.`);
};

let person1 = new Person('Alice');
person1.greet(); // Output: Hej, jag heter Alice.
```
*Här skapas en konstruktorfunktionen `Person`, och en metod `greet` läggs till prototypen. Alla instanser av `Person` kommer att ärva denna metod.*

Prototypbaserat arv gör JavaScript väldigt flexibelt och dynamiskt. 
Genom att förstå och utnyttja prototypkedjan kan utvecklare skapa komplexa arvshierarkier och effektivt återanvända kod.
Möjligheten att dela metoder och egenskaper mellan objekt minskar minnesanvändningen och förbättrar prestandan, vilket gör det möjligt att skapa av stora applikationer med effektiv minneshantering. 
JavaScript tillåter också dynamisk ändring av prototypen för ett objekt efter att det har skapats och bidrar med flexibilitet men kan bli stökigt om man inte är noggrann. 
Det kan bli svårt att följa varifrån metoder oche genskaper kommer ifrån, vilken i sin tur gör det svårt att avgöra vilken del av koden som ansvarar för funktionen/beteendet.

Det finns viss risk för prestandaproblem. För även om prototypbaserat arv kan förbättra minnesanvändningen, kan frekventa dynamiska ändringar av prototypen leda till prestandaförsämringar eftersom JavaScript-motorn måste omvärdera objektets struktur och dess prototypkedja.

---

## JS 1.10 Higher-order functions
Higher-order functions i JavaScript är funktioner som antingen tar en eller flera funktioner som argument eller returnerar en funktion som resultat, vilket gör det möjligt att skriva mer abstrakt och återanvändbar kod.

Ett exempel är `Array.prototype.map`, som tar en callback-funktion som argument och returnerar en ny array med resultaten av att anropa callbacken på varje element i den ursprungliga arrayen.

```js
Kopiera kod
let numbers = [1, 2, 3, 4];
let doubled = numbers.map(num => num * 2);
console.log(doubled); // Output: [2, 4, 6, 8]
```
*map-funktionen taren anonym funktion (num => num 2) som argument, som sedan appliceras på varje element i numbers-arrayen för att skapa en ny array, doubled.*

Prototypkedjan kan också utökas genom att lägga till metoder till `prototype`-egenskapen direkt:

```js
function Person(name) {
    this.name = name;
}

Person.prototype.greet = function() {
    console.log(`Hej, jag heter ${this.name}.`);
};

let person1 = new Person('Alice');
person1.greet(); // Output: Hej, jag heter Alice.
```
*I detta exempel skapas en konstruktorfunktion `Person`, och en metod greet läggs till prototypen. Alla instanser av `Person` kommer att ärva denna metod.*


`Array.prototype.filter` används för att skapa en ny array med alla element som passerar ett test som implementeras av den givna funktionen.
```js
let numbers = [1, 2, 3, 4, 5, 6];
let evenNumbers = numbers.filter(num => num % 2 === 0);
console.log(evenNumbers); // Output: [2, 4, 6]
```
*`filter`-funktionen tar en anonym funktion (num => num % 2 === 0) som argument, som sedan appliceras på varje element i numbers-arrayen för att skapa en ny array av de element som uppfyller villkoret.*

 `reduce` används för att ackumulera värdena i en array till ett enda värde:
 ```js
 let numbers = [1, 2, 3, 4];
let sum = numbers.reduce((total, num) => total + num, 0);
console.log(sum); // Output: 10
```
*`reduce`-funktionen tar en callback-funktion (total, num => total + num) och ett initvärde (0), som används för att lägga ihop värdena i numbers-arrayen till en enda summa.*

***Currying*** är en teknik som använder högre ordningens funktioner för att omvandla en funktion med flera argument till en serie av funktioner med ett argument vardera:
```js
function curry(fn) {
    return function curried(...args) {
        if (args.length >= fn.length) {
            return fn(...args);
        } else {
            return function(...nextArgs) {
                return curried(...args, ...nextArgs);
            };
        }
    };
}

function multiply(a, b, c) {
    return a * b * c;
}

let curriedMultiply = curry(multiply);
console.log(curriedMultiply(2)(3)(4)); // Output: 24
```
---

## JS 1.11 Single-thread programming
JavaScript är ett single-threaded programmeringsspråk, vilket innebär att det endast kan utföra en sak åt gången i en enda thread. Trots detta kan JavaScript hantera asynkrona operationer effektivt genom en event loop, vilket ger intrycket av parallell exekvering.

#### Event loop and Callback
Event loopen är hur JavaScript hanterar asynkrona uppgifter. När en asynkron operation (som en HTTP-förfrågan) påbörjas, skickas den till webbläsarens API. När operationen är klar, läggs callback-funktionen i händelseloopen för att köras när main thread är ledig.

```js
console.log('Start');

setTimeout(() => {
    console.log('Timeout completed');
}, 2000);

console.log('End');
```
*"Start" och "End" kommer att loggas först, medan "Timeout completed" loggas efter 2 sekunder*

Event loopen tillåter JavaScript att hantera flera uppgifter utan att blockera main thread. Det möjliggör att köra kod, samla och bearbeta händelser samt utföra underhållsarbete mellan uppgifterna.

***Web Workers*** gör det möjligt att köra skript i bakgrunden, vilket förbättrar prestandan för tunga uppgifter utan att blockera main thread. Web Workers har dock begränsningar, till exempel kan de inte manipulera DOM direkt.
```js
let worker = new Worker('worker.js');

worker.onmessage = function(event) {
    console.log('Message from worker: ' + event.data);
};

worker.postMessage('Start working');
```

```js
self.onmessage = function(event) {
    if (event.data === 'Start working') {
        self.postMessage('Work completed');
    }
};
```
Web Workers ger möjlighet att utföra parallella uppgifter utan att belasta main thread. De är användbara för komplexa beräkningar och bakgrundsarbete.

***Async/await*** används för att hantera asynkrona operationer som gör koden mer läsbar och lättare att skriva. Det är ett syntactic sugar[^1] över promises som ger ett strukturerat sätt att skriva asynkron kod. Detta introducerades i ES8.
Genom att använda async och await kan utvecklare skriva asynkron kod som om den vore synkron.



```js
async function exampleFunction() {
    try {
        const result = await someAsyncOperation();
        console.log(result);
    } catch (error) {
        console.error(error);
    }
}

exampleFunction();
```
 *Koden väntar på att someAsyncOperation ska slutföras innan den fortsätter till nästa rad och gör det möjligt att hantera asynkrona operationer på ett mer intuitivt sätt jämfört med kedjade .then-anrop i promises.*


Trots fördelarna med single-threaded programmering så har det vissa begränsningar.

***Race conditions*** uppstår när resultatet av en operation beror på den exakta tidpunkten då flera asynkrona operationer körs. Det kan leda till oförutsägbara resultat eller buggar i programmet.
 När två eller flera asynkrona operationer försöker få tillgång till eller ändra samma resurs samtidigt utan korrekt synkronisering, kan de "tävla" om att bli färdiga först.

Eftersom Javascript endast har en thread kan användaren uppleva att applikationen "fryser" om en uppgift blockerar main thread för länge. Därför är det viktigt att undvika exempelvis tunga beräkningar i main thread. 
Flera asynkrona operationer samtidigt kan leda till bottle necks om resurser inte hanteras korrekt.


[^1]: *"Syntactic sugar"* är syntax i ett programmeringsspråk som gör koden lättare att läsa och skriva utan att tillföra nya funktioner.

---

## JS 1.12 OAuth från frontend
OAuth är en standardprotokoll för autentisering och auktorisering som används för att ge applikationer säker tillgång till användarresurser utan att behöva dela användarens inloggningsuppgifter direkt.
Det är särskilt användbart för webbapplikationer som behöver interagera med externa tjänster och API
, som exempelvis Google eller Facebook.

I ett typiskt OAuth-flöde från frontend initierar applikationen processen genom att omdirigera användaren till en auktoriseringsserver, ofta av en tredjepartstjänst.
Användaren loggar sedan in på denna server och ger applikationen tillstånd att få tillgång till specifika resurser, 
till exempel deras profilinformation eller e-postadress. 
När användaren har godkänt begäran, returnerar servern en åtkomstkod eller token tillbaka till applikationen. 
Denna token används sedan av applikationen för att göra autentiserade API-anrop till den externa tjänsten.

#### OAuth-flow exempel
 **Initiera OAuth-processen:** 
 Applikationen länkar användaren till authservern som begär åtkomst.
```html
<a href="https://auth.example.com/authorize?response_type=code&client_id=YOUR_CLIENT_ID&redirect_uri=YOUR_REDIRECT_URI&scope=profile email&state=RANDOM_STRING&code_challenge=CODE_CHALLENGE&code_challenge_method=S256">Login with Example</a>
```

**Fånga upp auktoriseringskoden:**
När användaren kommer tillbaka till applikationen efter att ha loggat in och godkänt åtkomst, authkoden hämtas från URL
```js
const params = new URLSearchParams(window.location.search);
const authorizationCode = params.get('code');
```


**Byt ut authkod mot åtkomsttoken:**
Applikationen skickar authkoden till authservern och får en åtkomsttoken i utbyte.
```js
const tokenResponse = await fetch('https://auth.example.com/token', {
    method: 'POST',
    headers: {
        'Content-Type': 'application/x-www-form-urlencoded'
    },
    body: new URLSearchParams({
        grant_type: 'authorization_code',
        code: authorizationCode,
        redirect_uri: 'YOUR_REDIRECT_URI',
        client_id: 'YOUR_CLIENT_ID',
        code_verifier: 'CODE_VERIFIER'
    })
});
const tokenData = await tokenResponse.json();
console.log(tokenData.access_token);
```
**Använd åtkomsttoken för API-anrop:**
Med åtkomsttoken kan applikationen nu göra autentiserade anrop till API
```js
const userProfileResponse = await fetch('https://api.example.com/userinfo', {
    headers: {
        Authorization: `Bearer ${tokenData.access_token}`
    }
});
const userProfile = await userProfileResponse.json();
console.log(userProfile);
```

Ett av de mest använda flödena inom OAuth 2.0 är Authorization Code Flow med PKCE (Proof Key for Code Exchange) och är särskilt utformat för att förbättra säkerheten genom att förhindra attacker som kan uppstå när en auktoriseringskod fångas upp av en obehörig part.Användaren omdirigeras först till authservern där de loggar in och beviljar åtkomst. Därefter skickas en authkod tillbaka till klientapplikatioinen, som byter ut denna kod mot en åtkomsttoken via en säker kommunikation med servern.

Med åtkomsttoken kan applikationen sedan göra förfrågningar till API
för att få tillgång till användarens resurser, exempelvis för att hämta användarens profilinformation.
Det är viktigt att använda HTTPS i detta flöde för att säkerställa att token och annan känslig information inte kan avlyssnas.

---


## JS 1.13 Websockets
WebSockets möjliggör realtidskommunikation mellan en klient, som en webbläsare, och en server genom en ihållande och tvåvägsanslutning.
Till skillnad från traditionella HTTP-förfrågningar, där klienten måste initiera varje begäran och vänta på ett svar, tillåter WebSockets både klienten och servern att skicka meddelanden till varandra när som helst utan att vänta på en ny förfrågan.
Detta skapar en fullständig duplex-kommunikation som är särskilt lämplig för applikationer där snabb och kontinuerlig dataöverföring är avgörande, såsom i chattprogram, onlinespel och finansiella tjänster.

WebSocket-processen inleds med att klienten skickar en HTTP-förfrågan till servern för att etablera anslutningen.
När anslutningen är gjord, byter kommunikationen från HTTP till WebSocket-protokollet, vilket etablerar en ihållande anslutning mellan klienten och servern.
fter detta kan båda parter skicka och ta emot data när som helst, vilket möjliggör omedelbara uppdateringar med minimal fördröjning.

För att använda WebSockets i en JavaScript-applikation nyttjar man WebSocket API. Genom att skapa en WebSocket-anslutning kan man hantera olika händelser, såsom när anslutningen öppnas, när ett meddelande tas emot, när anslutningen stängs eller när ett fel inträffar.
Till exempel kan man skapa en anslutning till en server med följande kod: `const socket = new WebSocket('wss://example.com/socket');`.
När anslutningen är etablerad, kan klienten både skicka meddelanden till servern och ta emot dem i realtid.

En av de stora fördelarna med WebSockets är deras effektivitet jämfört med traditionella HTTP-baserade tekniker, där upprepade förfrågningar behövs för att hålla sig uppdaterad med servern.
Med WebSockets hålls en enda anslutning öppen, vilket minskar både nätverks- och serverbelastningen och förbättrar användarupplevelsen genom snabbare dataöverföring.

Det är dock viktigt att vara medveten om vissa utmaningar med WebSockets, särskilt när det gäller säkerhet och anslutningsstabilitet.
Det är avgörande att använda wss://-protokollet för att skydda anslutningen mot potentiella attacker.