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

## BE 1.4 MVC
***MVC***, som står för *Model-View-Controller,* är en designmönster som används för att organisera och strukturera applikationer genom att separera applikationens data, användargränssnitt och affärslogik i tre huvudkomponenter och hjälper till att skapa en tydlig och hanterbar arkitektur, särskilt i större projekt.

***Model*** representerar applikationens data och affärslogik. Den är ansvarig för att hantera data och reglerna för hur data kan ändras.
Modellen interagerar direkt med databasen och andra datakällor.
I en Laravel-app skulle en modell representera en databasentitet, som en användare eller en produkt, och innehålla metoder för att hämta och manipulera data.

```php
class Product extends Model {
    protected $table = 'products';
    protected $fillable = ['name', 'description', 'price', 'quantity'];
}
```

***View*** är ansvarig för att presentera data för användaren.
Den innehåller all HTML och presentationens logik för att visa information från modellen.
I laravel används *Blade* för att skapa views.
```php
<!-- resources/views/product.blade.php -->
<h1>{{ $product->name }}</h1>
<p>{{ $product->description }}</p>
<p>Pris: {{ $product->price }} kr</p>
```
***Controller*** fungerar som en mellanhand mellan model och view. Den hanterar user inputs, bearbetar dem och updaterar model eller view baserat på behov. I laravel skulle en controller t.ex. ta emot en request om update på en produkt, updatera model och sedan återge en updaterad view.
```php
class ProductController extends Controller {
    public function show($id) {
        $product = Product::findOrFail($id);
        return view('product', ['product' => $product]);
    }
}
```
MVC används främst för att separera applikationens logik och användargränssnitt, vilket gör det enklare att underhålla, utveckla och testa applikationen.
Genom att dela upp applikationen i tre distinkta komponenter kan utvecklare arbeta på olika delar av applikationen samtidigt utan att behöva oroa sig för att störa andra delar av koden.

---

## BE 1.5 Wordpress
WordPress är ett innehållshanteringssystem (CMS) byggt på PHP och MySQL. Det är en av de mest populära plattformarna för att skapa och hantera webbplatser och bloggar.
WordPress är open-source, vilket innebär att källkoden är fritt tillgänglig för alla att använda, modifiera och förbättra.


Idag används WordPress för att driva en stor andel av webbplatserna på internet. 
Det används av allt från personliga bloggar till stora företagswebbplatser och e-handelsbutiker.
WordPress kan anpassas för att passa olika typer av projekt genom användning av teman och plugins.

Utvecklare kan också skapa egna teman och plugins för att uppfylla specifika behov. Detta gör WordPress till ett väldigt användbart verktyg för att snabbt och enkelt bygga webbplatser med komplex funktionalitet.

#### Tema
Att skapa ett tema i WordPress innebär att utveckla en anpassad design och layout för en webbplats. Teman i WordPress består av en samling filer som tillsammans styr hur innehåll presenteras för användaren. Grundläggande komponenter i ett tema inkluderar index.php, som fungerar som huvudfilen, style.css för att definiera utseendet, och functions.php där man kan lägga till egna funktioner och hooks. 
För att börja utveckla ett tema, placeras dessa filer i en ny mapp under wp-content/themes. I style.css inkluderas även metadata som beskriver temat, såsom namn, författare och version. Genom att utnyttja WordPress-template tags och loop-funktionen kan utvecklare anpassa hur inlägg, sidor och andra innehållstyper visas på webbplatsen. 
Temat aktiveras via WordPress-admin dashboard, där det sedan tillämpas på hela webbplatsen.

#### Plugin
Att skapa ett plugin i WordPress innebär att utveckla en modul som lägger till eller utökar funktionaliteten på en webbplats utan att ändra kärnprogramvaran.
Ett plugin börjar med en enkel PHP-fil som placeras i en mapp under `wp-content/plugins`. 

Denna fil innehåller ett block med metadata som beskriver pluginet, såsom namn, beskrivning och version.
Ett plugin kan till exempel skapa nya anpassade posttyper, lägga till widgetar, eller integrera tredjepartstjänster.
Pluginet aktiveras sedan även det via WordPress-admin dashboard.
Eftersom pluginet är modulärt och fristående kan det enkelt distribueras och återanvändas på andra WordPress-webbplatser.

---

## BE 1.6 Heirarkiska databaser
Hierarkiska databaser är en typ av databassystem där data organiseras i en trädstruktur, med en tydlig hierarki av parent-child-relationer mellan posterna.
Denna modell var en av de tidigaste databasmodellerna och används fortfarande i vissa specifika applikationer där hierarkiska datarelationer är dominerande.


Ett vanligt exempel på en hierarkisk databas kan vara en organisation där strukturen är strikt hierarkisk. Till exempel kan en databas för en skola se ut så här:

- Skola
    - Klass 1
      - Elev A
      - Elev B
    - Klass 2
      - Elev C
      - Elev D
      - 
*Här representerar skolan roten i trädet, med klasser som childnoder och elever som children till respektive klass. Detta upplägg är enkelt att förstå och navigera, vilket gör hierarkiska databaser mycket användbara i sammanhang där data naturligt organiseras i en hierarkisk struktur.*



En av de största fördelarna med hierarkiska databaser är deras enkelhet när det gäller att navigera i data. Sökningar och uppdateringar kan göras snabbt, eftersom den hierarkiska strukturen är väldigt tydlig och data är lättåtkomlig om sökvägen är känd.
Men det finns också betydande nackdelar. Hierarkiska databaser är mindre flexibla när det gäller att hantera mer komplexa relationer som inte passar in i en strikt hierarkisk struktur. Till exempel är det svårt att modellera many-to-many-relationer, och databasen kan bli ineffektiv om hierarkin förändras ofta eller om flera poster behöver dela en förälder.

Dessutom kan hierarkiska databaser vara svåra att skala och anpassa när organisationen av data behöver förändras. Om hierarkin i data behöver modifieras, kan det krävas omfattande omstrukturering av hela databasen, vilket kan vara både tids- och resurskrävande.

Trots dessa begränsningar har hierarkiska databaser specifika användningsområden där deras struktur är fördelaktig. Till exempel används de ofta i operativsystemens filhanteringssystem, där deras fasta struktur gör det enkelt att organisera och hantera filer och mappar på ett logiskt sätt.

---

## BE 1.7 Relationsdatabaser, SQL och ER-modellering
Relationsdatabaser är den dominerande modellen för datalagring i moderna applikationer. Denna databasmodell bygger på konceptet att organisera data i tabeller, där varje tabell representerar en specifik entitet, såsom en användare eller en produkt. Tabellen består av rader och kolumner, där varje rad motsvarar en enskild post, och varje kolumn representerar ett attribut hos denna post. Relationer mellan olika tabeller definieras genom användning av primärnycklar och främmande nycklar, vilket gör det möjligt att skapa komplexa strukturer för att spegla verkliga samband mellan olika dataenheter.

***SQL*** *(Structured Query Language)* är det huvudsakliga språket som används för att interagera med relationsdatabaser. Med SQL kan utvecklare skapa, hämta, uppdatera och radera data från databasen genom kraftfulla och flexibla frågor. En grundläggande SQL-fråga som används för att hämta alla poster från en tabell kan se ut så här:
```sql
SELECT * FROM users;
```
*Denna request returnerar alla rader från tabellen "users".*

SQL är inte bara användbart för att hämta data; det kan också användas för att skapa och ändra strukturen på databaser, såsom att lägga till nya tabeller eller kolumner, och för att hantera användarbehörigheter och säkerhet.

***ER-modellering*** *(Entity-Relationship modellering)* är en metod som används i designfasen av en relationsdatabas för att skapa en visuell representation av systemets entiteter och de relationer som finns mellan dem. I en ER-modell representeras entiteter, som exempelvis "Kund" eller "Produkt", som rektanglar, och relationerna mellan dem representeras av linjer som förbinder dessa rektanglar. ER-modellen fungerar som en karta över databasen och hjälper till att säkerställa att alla relevanta entiteter och deras relationer är korrekt identifierade innan den fysiska databasen skapas.

***Objekt-relationell mapping*** *(ORM)* används för att brygga över skillnaderna mellan den objektorienterade världen i programmering och den relationsbaserade världen i databaser. 
Genom att använda ett ORM-ramverk kan utvecklare hantera databasposter som om de vore objekt i deras programmeringsspråk, vilket förenklar arbetet med data och minskar behovet av att skriva rå SQL-kod. 
Ett exempel på ett ORM-verktyg i PHP är Eloquent, som ingår i Laravel-ramverket. Med Eloquent kan utvecklare skriva kod som följande:

```php$user = User::find(1);
$user->name = 'Emma';
$user->save();
```
*En användare med ID 1 från databasen hämtas, användarens namn ändras till 'Emma', och ändringen sparas – allt utan att utvecklaren behöver skriva SQL.*

ORM-ramverk innehåller ofta funktioner för att validera data och automatiskt skapa lämpliga databasbegränsningar

Portabilitet är en annan fördel med ORM. Eftersom ORM-ramverk abstraherar databasspecifika detaljer kan utvecklare byta mellan olika databassystem med minimal kodändring. Detta gör applikationer mer flexibla och lättare att underhålla.


En typisk sekvens i backend kan vara:

- Ta emot auktoriseringskoden: Backend tar emot auktoriseringskoden från frontend-applikationen.
- Utbyte av auktoriseringskoden mot en access-token: Backend skickar en förfrågan till auktoriseringsservern för att byta ut auktoriseringskoden mot en access-token.
- Lagring och hantering av access-token: Access-token lagras säkert i backend för framtida användning när applikationen behöver interagera med externa API
.
- Gör API-anrop med access-token: Backend använder access-token för att göra autentiserade API-anrop till externa tjänster å användarens vägnar.

```php
$ch = curl_init();

curl_setopt($ch, CURLOPT_URL, "https://oauth2.googleapis.com/token");
curl_setopt($ch, CURLOPT_POST, 1);
curl_setopt($ch, CURLOPT_POSTFIELDS, http_build_query([
    'code' => $authorization_code,
    'client_id' => $client_id,
    'client_secret' => $client_secret,
    'redirect_uri' => $redirect_uri,
    'grant_type' => 'authorization_code',
]));

curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);

$response = curl_exec($ch);
curl_close($ch);

$token_data = json_decode($response, true);
$access_token = $token_data['access_token'];

```

En av de viktigaste aspekterna i backend är att säkert hantera access-tokens. Tokens bör behandlas som känslig data och lagras på ett säkert sätt, till exempel i en krypterad databas. Tokens har vanligtvis en begränsad livslängd, vilket innebär att backend också måste hantera token-förnyelse (refresh tokens) för att bibehålla åtkomsten till användarresurser över tid.
```php
// Exempel på lagring av en token
saveTokenToDatabase($user_id, $access_token, $refresh_token, $expires_in);

```


Säkerheten är central när man hanterar OAuth i backend. Det är viktigt att alla förfrågningar och dataöverföringar som involverar tokens görs över HTTPS för att förhindra avlyssning och manipulation. Dessutom bör åtkomstkontroller implementeras för att säkerställa att endast auktoriserade delar av backend-applikationen kan interagera med dessa tokens.


Backend-servern bör också vara ansvarig för att automatisera processen med att förnya access-tokens när de löper ut. Detta kan göras genom att använda en scheduler eller cron-jobb som regelbundet kontrollerar tokenens giltighet och förnyar dem vid behov.
```php
if (isTokenExpired($token)) {
    $newTokenData = refreshToken($refresh_token, $client_id, $client_secret);
    updateTokenInDatabase($user_id, $newTokenData['access_token'], $newTokenData['refresh_token'], $newTokenData['expires_in']);
}
```




--- 

## BE 1.8 OAuth i backend
***OAuth*** *(Open Authorization)* är ett standardprotokoll som används för att tillhandahålla säkra delegerade åtkomster, vilket innebär att en 
  applikation kan få begränsad åtkomst till användarresurser på en annan server utan att exponera användarens inloggningsuppgifter.
 I backend-konteksten är hanteringen av OAuth av avgörande betydelse eftersom det är backend-servern som hanterar de flesta säkerhetskritiska operationer, såsom hantering av tokens, autentisering, och interaktion med externa API.
 Detta innebär att backend-servern måste hantera alla känsliga operationer med hög säkerhet och noggrannhet för att skydda användarens data.


I backend-flödet börjar processen vanligtvis efter att frontend har erhållit en auktoriseringskod från en auktoriseringsserver (till exempel Google eller Facebook). Denna kod skickas sedan till backend-servern, som byter ut den mot en access-token genom att göra ett säkert API-anrop till auktoriseringsservern och byta ut auktoriseringskoden mot en access-token. Access-token är den nyckel som tillåter backend-servern att autentisera sig mot den externa tjänsten och få tillgång till användarens resurser på ett säkert sätt.


Backend-servern hanterar också förnyelsen av access-tokens när de löper ut, vilket görs genom att använda en refresh-token. Refresh-tokens ger möjlighet att erhålla nya access-tokens utan att användaren behöver autentisera sig på nytt, vilket förbättrar användarupplevelsen och säkerställer att applikationen kan fortsätta att interagera med externa API
utan avbrott. 
Det är avgörande att dessa tokens lagras säkert, ofta i en krypterad databas, och att de hanteras med strikta säkerhetsåtgärder för att förhindra otillåten åtkomst.

---

## BE 1.9 HTTP-protokollet
***HTTP*** (*Hypertext Transfer Protocol *) är grundpelaren för dataöverföring på webben. Det är ett protokoll som definierar hur meddelanden formuleras och överförs mellan klienter och servrar. När en användare besöker en webbplats sker en mängd HTTP-förfrågningar och -svar i bakgrunden, vilket möjliggör laddning av sidor, nedladdning av filer och interaktion med webbapplikationer. HTTP är ett stateless protokoll, vilket innebär att varje förfrågan behandlas oberoende av tidigare förfrågningar. Detta gör HTTP enkelt och effektivt, men det kräver att utvecklare använder tekniker som sessionshantering för att behålla tillståndet mellan förfrågningar.

HTTP använder en rad metoder för att definiera den typ av åtgärd som klienten vill utföra. De vanligaste metoderna inkluderar GET, POST, PUT och DELETE. GET används för att hämta data från en server, medan POST skickar data till servern för att skapa eller uppdatera en resurs. PUT används för att uppdatera en resurs och DELETE för att ta bort en resurs. Dessa metoder utgör grunden för RESTful API
, där resurser hanteras genom en standardiserad uppsättning HTTP-metoder.

Säkerhet är en viktig aspekt av HTTP, och detta hanteras ofta genom HTTPS, en säker version av HTTP som använder SSL/TLS för att kryptera data under överföringen. Detta skyddar data från att avlyssnas eller manipuleras under överföring. I dagens webbutveckling är HTTPS en grundläggande del av att skydda användardata och förhindra säkerhetsöverträdelser. 

---

## BE 1.10 cURL
***cURL*** är ett kommandoradsverktyg och en bibliotek som används för att göra HTTP-förfrågningar och överföra data till och från en server. Det är extremt mångsidigt och stöder flera protokoll, inklusive HTTP, HTTPS, FTP och många fler. Inom PHP och annan server-side utveckling används cURL ofta för att interagera med externa API
, skicka och ta emot data, samt automatisera och testa webbapplikationer.

Ett typiskt användningsområde för cURL i PHP är att skicka en HTTP-förfrågan till en extern server. Detta kan vara en GET-förfrågan för att hämta data, en POST-förfrågan för att skicka data, eller mer komplexa förfrågningar som kräver autentisering eller hantering av sessionsdata. Exempelvis kan en cURL-baserad förfrågan se ut så här:
```php
$ch = curl_init();
curl_setopt($ch, CURLOPT_URL, "https://api.example.com/data");
curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);
$response = curl_exec($ch);
curl_close($ch);
```

I detta exempel initieras en cURL-session, en URL anges, och sedan utförs förfrågan. Slutligen stängs sessionen och svaret från servern sparas i variabeln $response. Detta ger utvecklare möjlighet att programatiskt interagera med webbtjänster, vilket är särskilt användbart när man arbetar med RESTful API.

cURL erbjuder också avancerade funktioner som hantering av cookies, uppladdning av filer, och stöd för SSL-certifikat för säkra förbindelser.

---

## BE 1.11 REST
***REST***, eller *Representational State Transfer*, är en arkitekturstil som används för att skapa skalbara och lätta webbtjänster. RESTful API
bygger på HTTP-protokollet och använder dess metoder – GET, POST, PUT och DELETE – för att hantera resurser på en server. I en RESTful arkitektur är resurser, som exempelvis användare, produkter eller artiklar, identifierade genom URL
, och dessa resurser kan manipuleras genom de olika HTTP-metoderna.

En av styrkorna med REST är dess enkelhet och flexibilitet. Eftersom det använder standard HTTP-metoder och statuskoder, är det lätt att integrera och felsöka RESTful API
. RESTful tjänster är också designade för att vara stateless, vilket innebär att varje förfrågan från klienten till servern måste innehålla all information som behövs för att förstå och bearbeta förfrågan. Detta gör att RESTful tjänster kan skalas effektivt, eftersom varje förfrågan behandlas oberoende av tidigare förfrågningar.

Ett exempel på en RESTful förfrågan är att hämta data om en specifik användare från en server:

``` http
GET /users/1 HTTP/1.1
Host: example.com
```

Denna request hämtar information om användaren med ID 1. Svaret från servern returneras vanligtvis i ett format som JSON eller XML, som är lätt att parsa och använda i applikationer. *REST* har blivit standarden för API-design på grund av dess enkelhet och kompatibilitet med moderna webbutvecklingsverktyg.

***REST*** är inte en strikt standard, utan en uppsättning riktlinjer som gör det möjligt för utvecklare att skapa flexibla och skalbara API
. RESTful API
används ofta i samarbete med andra tekniker som OAuth för autentisering, och de kan effektivt användas för att skapa applikationer som är både användarvänliga och säkra. REST fortsätter att vara en hörnsten inom modern webbutveckling och API-design.

---

## BE 1.12 XML och andra dataformat
#### XML
Dataformat spelar en kritisk roll i webbutveckling, särskilt när det gäller att överföra information mellan system. ***XML*** (*eXtensible Markup Language*) är ett av de äldsta och mest använda formaten för att strukturera och lagra data. Till skillnad från HTML, som används för att presentera data, används XML för att beskriva och transportera data. XML är självbeskrivande, vilket innebär att varje dataelement omges av taggar som beskriver dess innehåll. Detta gör XML lättläst och förståelig för både människor och maskiner, men det kan också göra XML-filer stora och svårhanterliga i jämförelse med modernare format.

***JSON*** (*JavaScript Object Notation*) har på senare år blivit det mest populära dataformatet, särskilt i samband med webbaserade API
. JSON är lättare och mer läsbart än XML, vilket gör det till det föredragna formatet för många utvecklare. JSON använder en struktur av nyckel-värde-par och kan lätt representera komplexa data genom att nästla objekt och arrayer. Detta gör JSON särskilt användbart för att skicka och ta emot data mellan klient och server i webbaserade applikationer.

***CSV*** (*Comma-Separated Values*) är ett annat vanligt dataformat som används för att representera tabulär data, såsom data från kalkylblad eller databaser. CSV är enkelt att skapa och läsa, men det har begränsningar när det gäller att representera komplexa datatyper. Varje rad i en CSV-fil representerar en post, och varje värde separeras av kommatecken, vilket gör det enkelt att importera och exportera data mellan olika system.

Varje dataformat har sina styrkor och svagheter, och valet av format beror ofta på applikationens specifika behov. XML är kraftfullt för dokumentcentrerad data, JSON är idealiskt för webbtjänster och API
, och CSV är perfekt för enkla, tabulära datauppgifter.

---

## BE 1.13 Webbservrar

Webbservrar spelar en central roll i webbutveckling, då de är ansvariga för att hantera inkommande HTTP-förfrågningar från klienter (som webbläsare) och svara med rätt innehåll, oftast i form av HTML, CSS, JavaScript eller andra dataformat som JSON och XML. Webbservrar kan vara både hårdvara och mjukvara. När vi talar om en webbserver i utvecklingssammanhang, syftar vi oftast på mjukvaran som lyssnar på nätverksförfrågningar, behandlar dem och skickar tillbaka ett svar.

Det finns flera populära webbservermjukvaror, inklusive Apache, Nginx, och Microsoft's Internet Information Services (IIS). Apache och Nginx är två av de mest använda webbservrarna på internet och är kända för sin stabilitet, flexibilitet och kraftfulla konfigurationsmöjligheter. Dessa servrar kan hantera allt från små personliga bloggar till stora, skalbara applikationer med miljontals användare.

En av de grundläggande koncepten inom webbservrar är ***server-side rendering*** *(SSR)* kontra ***client-side rendering*** *(CSR)*. Vid SSR bearbetas hela webbsidans innehåll på servern innan det skickas till klienten. Detta innebär att HTML-koden genereras på servern och skickas som en fullständig sida till klientens webbläsare. Fördelen med SSR är att det ofta resulterar i snabbare laddningstider och bättre prestanda på äldre enheter, eftersom klientens webbläsare inte behöver göra lika mycket arbete.

Å andra sidan innebär CSR att större delen av sidan renderas på klientens sida med hjälp av JavaScript. Detta tillvägagångssätt har blivit vanligare med utvecklingen av JavaScript-ramverk som React, Angular, och Vue.js, som möjliggör dynamiska och interaktiva användarupplevelser. Med CSR laddas en grundläggande HTML-sida initialt, och sedan fylls innehållet på genom JavaScript-baserade förfrågningar till servern. Detta kan resultera i snabbare interaktioner efter den första sidladdningen men kan leda till längre initiala laddningstider.

Valet mellan SSR och CSR beror på applikationens behov och användningsscenario. I vissa fall kombineras de två för att dra nytta av fördelarna från båda teknikerna, vilket kallas hybrid rendering. Det är också viktigt att notera att webbservrar måste konfigureras och optimeras för att stödja den valda renderingsmetoden effektivt, vilket innefattar hantering av cachning, säkerhet och skalbarhet för att möta applikationens krav.
