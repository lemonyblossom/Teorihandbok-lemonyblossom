# Teorihandboken - Backendutveckling (BE)
Studerande: Emma Jensen

## BE 1.1 PHP
PHP, som står för "Hypertext Preprocessor", är ett skriptspråk som körs på serversidan och används för att skapa dynamiska webbplatser och webbaserade applikationer.
Det är särskilt populärt för sin enkelhet och flexibilitet, vilket gör det lätt att integrera med HTML och att kommunicera med databaser som MySQL och PostgreSQL.
PHP är ett tolkat språk, vilket innebär att koden exekveras direkt av servern utan att behöva kompileras, vilket underlättar snabb utveckling.

PHP används ofta i webbapplikationer där interaktion med databaser är nödvändig, till exempel för att hantera inloggningssystem, e-handelsplattformar och innehållshanteringssystem (CMS) som WordPress.
Dess stora community och omfattande bibliotek gör det till ett väldigt användbart verktyg för utvecklare, vilket underlättar skapandet av robusta och skalbara applikationer.

En fördel med PHP är dess kompatibilitet med olika operativsystem, inklusive Windows, Linux och macOS, vilket gör det till ett mångsidigt verktyg för webbutveckling.
PHP
öppen källkod-karaktär har också bidragit till dess utbredda användning, eftersom det är gratis att använda och att källkoden är tillgänglig för alla att modifiera.

PHP används brett inom webbutveckling, och en av de mest kända plattformarna som använder PHP är WordPress, som driver en stor del av alla webbplatser på internet.
PHP används också för att bygga e-handelsplattformar som *Magento* och *WooCommerce*, och det är ett populärt val för att utveckla API
och webbapplikationer som kräver en solid backendstruktur.

Den senaste versionen av PHP, *PHP 8*, har introducerat flera förbättringar som ökad prestanda och nya språkliga funktioner som underlättar kodunderhåll.
PHP fortsätter att vara ett relevant verktyg för utvecklare tack vare sin flexibilitet och kraft, vilket gör det till ett självklart val för många utvecklingsprojekt.

PHP kräver en medvetenhet om säkerhet och att skydda PHP-applikationer från attacker som SQL-injektioner och Cross-Site Scripting *(XSS)* är avgörande.
SQL-injektioner kan exempelvis förebyggas genom att använda förberedda uttalanden med PDO eller mysqli, vilket säkerställer att inmatade data behandlas som rena strängar och inte som körbar kod.
Användningen av `password_hash()` för att säkra lösenord är också en grundläggande säkerhetsåtgärd.

För att förhindra XSS-attacker bör all data som ska presenteras för användaren valideras och sanitiseras, ofta med hjälp av funktioner som `htmlspecialchars()`. 

---

## BE 1.2 OOP i PHP
Objektorienterad programmering (OOP) i PHP är ett sätt att organisera kod i objekt och klasser, vilket främjar bättre struktur, modularitet och återanvändbarhet.

Istället för att använda procedurer eller funktioner för att hantera data och logik, använder OOP klasser för att skapa objekt som representerar olika delar av applikationen.

En klass i PHP definierar egenskaper (attribut) och beteenden (metoder) för objekten. Ett objekt är en instans av en klass som innehåller specifika värden för dessa egenskaper.
Till exempel kan en klass "User" innehålla egenskaper som namn, e-post och lösenord, samt metoder för att registrera, logga in och uppdatera användaruppgifter.

OOP erbjuder flera fördelar som gör det lättare att hantera och underhålla stora kodbaser:

- ***Återanvändbarhet:*** Genom att definiera generella klasser kan kod återanvändas i olika projekt, vilket minskar duplicering.
- ***Modularitet:*** Kod kan organiseras i separata klasser och moduler, vilket gör den mer hanterbar och lättare att felsöka.
- ***Enkel underhållning:*** Koden blir lättare att uppdatera och utöka när den är modulär och välstrukturerad.
- ***Inbyggda funktioner:*** PHP erbjuder ett omfattande bibliotek av inbyggda funktioner och klasser, vilket underlättar utvecklingen.

```php
class User {
    private $name;
    private $email;

    public function __construct($name, $email) {
        $this->name = $name;
        $this->email = $email;
    }

    public function getName() {
        return $this->name;
    }

    public function getEmail() {
        return $this->email;
    }
}

// Skapa ett nytt objekt av klassen User
$user = new User("Emma", "emma@example.com");

echo $user->getName(); // Output: Emma
```
*Här representerar klassen User en användare med egenskaperna name och email, samt metoder för att hämta dessa värden.*

OOP i PHP möjliggör också **arv** och **inkapsling**, vilket innebär att en klass kan ärva egenskaper och metoder från en annan klass *(superklass)*, och att data kan kapslas in så att den bara är åtkomlig på ett kontrollerat sätt.

```php
class Admin extends User {
    private $role;

    public function __construct($name, $email, $role) {
        parent::__construct($name, $email);
        $this->role = $role;
    }

    public function getRole() {
        return $this->role;
    }
}

// Skapa ett nytt Admin-objekt
$admin = new Admin("Emma", "emma@example.com", "Administrator");

echo $admin->getRole(); // Output: Administrator
```
*Här är klassen Admin en subklass av User och ärver dess egenskaper och metoder. Admin lägger också till en ny egenskap, role, som är specifik för administratörer.*



---


## BE 1.3 Säkerhet i PHP
Säkerhet är en kritisk aspekt inom PHP-utveckling, eftersom webbapplikationer ofta är måltavlor för olika typer av attacker. Det är avgörande för utvecklare att förstå och implementera säkerhetsåtgärder för att skydda både applikationer och användardata.

#### Vanliga hot och åtgärder
***SQL-injektion*** är en av de vanligaste attackerna där en angripare infogar skadlig SQL-kod i en applikation för att manipulera databasfrågor.
För att skydda sig mot SQL-injektioner bör utvecklare använda förberedda uttalanden och parametriserade frågor med PDO eller mysqli.
```php
$stmt = $pdo->prepare('SELECT * FROM users WHERE email = :email');
$stmt->execute(['email' => $email]);
```
***Cross-Site Scripting (XSS)*** XSS-attacker tillåter angripare att injicera skadlig kod i en webbsida som sedan körs i andra användares webbläsare. För att förhindra detta bör alla data som visas på webbsidor vara korrekt sanitiserade.

```php 
$clean_input = htmlspecialchars($input, ENT_QUOTES, 'UTF-8');
```
***Cross-Site Request Forgery*** (*CSRF*)-attacker tvingar användare att oavsiktligt skicka skadliga förfrågningar. Användning av CSRF-tokens i formulär hjälper till att förhindra denna typ av attacker. 
```php
echo '<input type="hidden" name="csrf_token" value="'.$csrf_token.'">';
```
En annan kritisk sårbarhet är användningen av bibliotek, ramverk eller andra komponenter som har kända säkerhetsbrister. Om dessa inte uppdateras regelbundet kan de utsätta applikationen för allvarliga risker, såsom dataläckage eller övertagande av hela servern. 
För att undvika detta är det avgörande att kontinuerligt hålla alla komponenter uppdaterade och säkerställa att de inte innehåller kända sårbarheter. 
Vi använder till exempel PHP 8.3, vilket är den senaste versionen av PHP, och det är viktigt att fortsätta uppdatera till nyare versioner när de släpps. 
Vid uppdatering av PHP-versionen är det också viktigt att återigen testa hela applikationen med enhetstester, exempelvis med PHPUnit 10, som kräver PHP 8.1 eller senare.

***Lösenordshantering***
 Lösenord bör aldrig lagras i klartext, utan istället hashas med starka algoritmer innan de sparas i databasen.
 PHP erbjuder inbyggda funktioner för säker lösenordshantering, såsom `password_hash()` och `password_verify()`.

```php
// hashat lösenord
$hashed_password = password_hash($password, PASSWORD_DEFAULT);

// Verifiera lösenordet
if (password_verify($input_password, $hashed_password)) {
    // Lösenordet korrekt
} else {
    // Lösenordet fel
}
```
Genom att använda `password_hash()` säkerställs att lösenorden hashas med en säker algoritm som även inkluderar en unik saltning för varje lösenord, vilket gör det svårare för angripare att knäcka lösenorden även om databasen skulle äventyras.

***Implementering av HTTPS***
För att säkerställa att data som överförs mellan användare och server är skyddad från avlyssning och manipulation, bör utvecklare alltid implementera HTTPS.
Genom att använda SSL/TLS-certifikat kan data krypteras under överföringen, vilket skyddar känslig information som inloggningsuppgifter och betalningsinformation. 

***Felmeddelanden och undantagshantering*** bör hanteras på ett sätt som inte avslöjar känslig information om applikationen. 
Att visa detaljerade felmeddelanden för användarna kan ge angripare insikt i applikationens struktur och potentiella svagheter. Det är viktigt att endast logga detaljerade felmeddelanden internt och visa generella felmeddelanden för slutanvändarna.

Otillräcklig loggning och övervakning
När loggning och övervakning är bristfälliga kan attacker pågå oupptäckta under lång tid, vilket ger angripare möjlighet att manipulera, stjäla eller radera data utan att någon märker det. 
Studier visar att det i genomsnitt tar över 200 dagar att upptäcka ett intrång, vilket ofta innebär att skadorna redan är omfattande.
För att minimera risken bör applikationer ha robusta loggnings- och övervakningssystem på plats som kan identifiera och varna om misstänkta aktiviteter.

---
---
---


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
