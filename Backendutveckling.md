# Teorihandboken - Backendutveckling (BE)
Studerande: Emma Jensen

## BE 1.1 PHP
Beskriv rubriken här

## BE 1.2 OOP i PHP
Beskriv rubriken här

## BE 1.3 Säkerhet i PHP
Beskriv rubriken här
### Applikatioinssäkerhet
#### Sårbarheter
SE OWASP.ORG!!

Cross-site Scripting (XSS)
är en svaghet som uppstår när en app innehåller opålitlig data i en ny sida utan validering (validering av vad?)

Användning av komponenter med kända säkerhetsbrister- När bibliotek, ramverk etc. som har kända säkerhetsbrister utnyttjas. Kan resultera i förlorande av data eller t.o.m. övertagning av server.

Otillräcklig loggning och övervakning - När loggar ch övervakning är bristande kan attacker fortsätta obekmärkt och på sikt lyckas manipulera, få ut eller radera data. De flesta studier visar på att det tar över 200 dagar att upptäcka intrång. Vilket ofta innebär att 


En xss attack låter en hackare att köra script..

Vi använder PHP 8.3 vilket är den senaste versionen av php, 8< är safe. Ett bra sätt att skydda sig är att kontinuerligt uppdatera sin php.  
För att kunna uppdatera behöver allt testas (PHP UNIT TEST) igen. phpUNIT 10 kräver 8.1 or later. 
Ett problem kan vara att din server supplier inte har php 8 eller senare. 

VPS- innebär att man får en server som man kan ställa in servern själv


#### SQL-Injections
Vad är det och hur undviker man det?
föreläsning 16e januari

##### Hur gör man för att en lista på allas användernamn oc lösen ska bli oanvändbara?
> HASHing innebär att göra en ny sträng av t.ex. ett lösen, som då inte går att hitta med hjälp av den strängen som gets. 
> Rainbow tables: 
> Salt: är random data som läggs in för att försvåra lösenorden. En salt "något bullshit" läggs till på ditt lösen innan hashen gör sin sträng för att göra hashen unik.
> Peppar: ?
> Krav på lösen för användare. MINST men inte längst
>
> Password_hash() skapar lösen med säker has algoritm (bycrypt som default)




## BE 1.4 MVC
Beskriv rubriken här

## BE 1.5 Wordpress
#### Vad är Wordpress?
#### Varför Wordpress?
#### Skapa ett tema:
#### Skapa ett plugin:



## BE 1.6 Heirarkiska databaser
Beskriv rubriken här

## BE 1.7 Relationsdatabaser, SQL och ER-modellering
Mapping går att skriva om här 
eloquent går också att skriva om under laravel och objectorienteradprogrammering
 > ORM stands for Object-Relational Mapping. It is a programming technique used in software development to bridge the gap between the object-oriented paradigm used in programming languages and the relational paradigm used in relational databases. ORM frameworks provide a way to interact with databases using programming language objects, allowing developers to work with databases in a more natural and object-oriented manner.

> Here are some key concepts related to ORM:

> 1. **Objects as Entities:**
  > - In an object-oriented programming language, you work with objects that represent entities in your application, such as users, products, or orders.
   > - ORM allows you to map these objects directly to corresponding tables in a relational database.

> 2. **Classes as Tables:**
  >  - ORM frameworks often use classes to represent database tables.
  >  - Class attributes typically correspond to table columns.

> 3. **Relationships:**
  > - ORM frameworks support defining relationships between objects/classes, such as one-to-one, one-to-many, and many-to-many relationships.
  >  - These relationships are translated into corresponding relationships between database tables.

> 4. **CRUD Operations:**
   > - ORM provides an abstraction layer for performing CRUD (Create, Read, Update, Delete) operations on the database using object-oriented syntax.
  >  - Instead of writing SQL queries, developers can use methods provided by the ORM framework to interact with the database.

> 5. **Data Integrity:**
  >  - ORM frameworks often include features to ensure data integrity, such as validation and automatic generation of appropriate database constraints.

> 6. **Portability:**
  >  - ORM helps in making the code more portable across different database systems. Developers can often switch between databases with minimal code changes because the ORM framework abstracts the database-specific details.

> Popular ORM frameworks in different programming languages include:
> - **Java:** Hibernate, EclipseLink
> - **Python:** SQLAlchemy, Django ORM
> - **.NET:** Entity Framework (EF)
> - **PHP:** Doctrine, Eloquent (Laravel)

> Using ORM can lead to more maintainable and readable code, as developers can focus on the application's logic without having to write complex SQL queries. However, it's essential to understand the underlying database structure and how the ORM framework translates between objects and the database to optimize performance and avoid potential pitfalls.
Beskriv rubriken här

## BE 1.8 OAuth i backend
Beskriv rubriken här

## BE 1.9 HTTP-protokollet
Beskriv rubriken här

## BE 1.10 cURL
Beskriv rubriken här

## BE 1.11 REST
Beskriv rubriken här

## BE 1.12 XML och andra dataformat
#### XML
eXtensible Markup Language
alike html but carry and store data, do not display it.
self descriptive
Gör ingenting
sender, reciever, heading, message(in body)

FÖRDELAR: Lättläst, främst för att det är beskrivande men även för att det är luftigt.
#### CSV
Comma(character/colon) separated Values
Används ofta i filformat t.ex. Excel

(visar exempel i adminer där man kan exportera i CSV-format istället för t.ex. SQL)

FÖRDELAR MED CSV:
Då får vi all data som kommaseparerade värden
   - enkelt att läsa för t.ex ett excel som förstår att varje komma innebär att den kommer sätta ut varje value i en enskid cell i en collumn.

NACKDELAR: sparar kompakt och det är svårt att läsa med alla kommatecken mellan
#### JSON

Används för att beskriva objekt

> "Textsträng (måste omges av citattecken)
Tal
JSON-objekt (måste omges av klammerparenteser)
Array (måste omges av hakparenteser)
Boolean
Null"

JSON blir ofta nestlat, det kan bli väldigt djupt. t.ex. objekt i objekt i objekt.

## BE 1.13 Webbservrar

##### Serverside serndering vs  Clientside renderering 
