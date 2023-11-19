# Teorihandboken - HTML & CSS (HC)
Studerande: Emma Jensen

## HC 1.1 HTML & CSS

#### HTML *(Hypertext markup language)*
HTML är språket som utgör strukturen och formaterar dokument på webbsidor, vilket gör att text konverteras till hypertext och återger sidor i browsern på ett korrekt sätt. HTML tillsammans med HTTP ( Hypertext Transfer Protocol- ett kommunikationsprotokoll ) grunden för World Wide Web.  
Webbsidorna som skrivs i HTML överförs med HTTP över internet. 
I html används taggar för att definiera olika delar av hemsidan, dessa benämns som element och kan vara rubriker, olika typer av stycken (såsom artiklar), listor, tabeller, formulär och många fler typer av strukturelement. 
Genom dessa element kan developers strukturera innehållet av sin kod på ett lättöverskådligt, logiskt och förståeligt sätt. Både för sig själv men även för andra. 
Att använda de globala element som finns i html5 istället för att göra divar som inte nödvändigtvis behövs, gör det dessutom mycket lättare för webbläsaren att förstå vad som finns på sidan, vilket i sin tur leder till att hemsidan blir mer tillgänglig för t.ex. läsverktyg för synskadade eller genom att bara kunna tabba sig genom sidan.


HTML är dock inte ett programmeringsspråk, utan är ett markeringsspråk som genom taggar har i uppgift att ge struktur för hela webbsidans text med styckeindelningar, listor, rubriker, avdelningar osv. 
HTML har inte i uppgift att utföra kommandon, vilket är kriteriet för att ett språk ska kategoriseras som programmeringsspråk.
 Däremot så tillåter HTML infogande av program i t.ex.Javascript för att utföra interaktiva och dynamiska funktioner på webbsidan och använder då css för att styra hur sidan ska se ut i sin design.


#### CSS *(Cascading Style Sheet)*
Css står för Cascading Style Sheet och är en stilmall som styr allt som har med design på en webbsida att göra. 
Det inkluderar bl.a. font, färg och storlek på text,  om hur de olika elementen ser ut och förhå
ller sig till varandra i t.ex. storlek. 
Dessutom styr det även eventuella förändringar i attributen när användaren interagerar med sidan, såsom när dem hovrar med sin muspekare eller webbläsarfönstret ändrar storlek.

Det är viktigt att notera att CSS, även om det kan inbäddas i HTML *(inline styling i varje element eller internal i en style tag)*, är självständigt från HTML och kan användas tillsammans med alla XML-baserade märkningsspråk.

####Inline vs Internal vs External CSS

##### *INLINE*
```
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Inline CSS</title>
</head>
<body>
    <!-- Inline styles -->
    <h1 style="color: blue;">This is a Heading</h1>
    <p style="color: green;">This is a paragraph.</p>
</body>
``` 

##### *INTERNAL*
```
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Internal CSS</title>
<style>
        h1 {
            color: red;
        }

        p {
            color: purple;
        }
    </style>
</head>

<body>
    <h1>This is a Heading</h1>
    <p>This is a paragraph with internal styles.</p>
</body>
```

##### *EXTERNAL*

```</head>
<body>
    <h1>This is a Heading</h1>
    <p>This is a paragraph with external styles.</p>
</body>
```
```
/* External CSS in a style.css */
body {
    background-color: #f0f0f0;
    font-family: Arial, sans-serif;
}

h1 {
    color: red;
}

p {
    color: purple;
} 
```

## HC 1.2 Responsiv design


#### Vad är det och varför är det viktigt?
Responsiv design innebär att utformningen av en webbsida anpassar sig dynamiskt baserat på användarens enhet (dvs skärmstorlek och om skärmen kan rotera), vilket skapar en användarvänlig plattform där allt innehåll fortfarande är lättillgängligt och rent semantiskt bibehåller sin plats även i olika skärmformat.

För att detta ska vara möjligt använder utvecklare media queries i sina stilmallar, och baserar elementens attribut baserat på enhetens upplösning och skärmstorlek. 

Med tanke på hur vi idag har otaliga skärmstorlekar att förhålla oss till så är det av yttersta vikt göra sin design responsiv även mellan pixlarna utvecklarna har satt sina media queries till. T.ex. bör en webbsidas innehåll och elementens förhållande se bra ut även när användaren gör sitt fönster mindre eller större.

För att säkerställa detta är så bör utvecklarna testa sin design på olika enheter under utvecklingens gång.

```
/* Grund för alla*/
body {
    font-family: 'Comic Sans MS', cursive, sans-serif;
}

h1 {
    color: purple;
}

p {
    color: darkorange;
}

/*för skärmar 600 pixlar eller bredare */
@media screen and (min-width: 600px) {
    body {
        background-color: #ffeead;
    }

    h1 {
        color: turquoise;
    }

    p {
        font-size: 18px;
        text-align: center;
    }
}

/* för skärmar 900 pixlar eller bredare */
@media screen and (min-width: 900px) {
    body {
        background-color: #a1dbb2;
    }
}
```

##### HUR? 

För att skapa en responsiv design är det hjälpsamt att använda sig av relativa mätvärden för att skapa en flexibel design. Om utvecklaren använder t.ex. pixlar för att sätta storlekar på avstånd eller sektioner så blir dessa värden fasta och reagerar därför inte när användaren zoomar in eller gör webbläsarfönstret mindre/större, vilket i sin tur kan skapa problem i relation till resten av webbsidan i andra enheter än den utvecklaren anpassat sina pixlar efter. Det kan bli problematiskt när målet är en dynamisk och flexibel design som ska vara tillgänglig och passa alla.

## HC 1.3 Tillgänglighet inom webb
Beskriv rubriken nedan här

## HC 1.4 Aktuella webbstandarder (gällande och kommande standarder)
Beskriv rubriken nedan här

## HC 1.5 CSS Pre-processorer (ex SASS/LESS)
Beskriv rubriken nedan här

## HC 1.6 Optimering och validering av HTML & CSS
Beskriv rubriken nedan här


Länkar:
 > [Internetkunskap](-https://internetkunskap.se/artiklar/ordlista/http/)