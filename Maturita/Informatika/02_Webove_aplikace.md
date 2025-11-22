# Webové aplikace
## Jak funguje web
- Web dnes vnímáme jako samozřejmost – zadáme adresu, stránka se objeví a můžeme ji používat. Abychom však dokázali webové aplikace efektivně vytvářet a optimalizovat, je důležité pochopit, co se děje „v zákulisí“. Celý proces funguje jako spolupráce několika vrstev technologií, které společně zajistí, že se obsah uložený na vzdáleném serveru promění ve stránku, kterou vidíme v prohlížeči.
- Webový prohlížeč, server a síťová komunikace tvoří základní stavební kameny každé webové aplikace. Prohlížeč interpretuje kód, server poskytuje data a síť zajišťuje přenos informací mezi nimi. Znalost jejich role a vzájemných interakcí je klíčová pro každého vývojáře.
### Co je webová stránka a jak vzniká
- Webová stránka je dokument napsaný primárně pomocí HTML, který popisuje strukturu obsahu. Na tento základ se aplikuje CSS, které definuje vzhled, a JavaScript, který řídí interaktivitu a logiku na straně uživatele.
- Prohlížeč načte soubory HTML, CSS a JS, postupně je interpretuje a vytvoří z nich vizuální podobu stránky. Tento proces zahrnuje vytvoření tzv. Document Object Modelu (DOM), což je stromová reprezentace HTML dokumentu, a následné vykreslení výsledku na obrazovku.
- _Jednoduše řečeno: HTML říká „co tam je“, CSS říká „jak to vypadá“ a JavaScript říká „co se má stát“._
### URL, domény a DNS
- Aby uživatel mohl stránku navštívit, musí znát její adresu. K tomu slouží URL (Uniform Resource Locator), které funguje podobně jako adresa domu – přesně popisuje, kde se daný obsah nachází.
- Doména (např. **google.com**) je uživatelsky přívětivá alternativa k číselné IP adrese (Google IPv4 `142.251.38.142`) serveru. Překlad domény na IP adresu zajišťuje DNS (Domain Name System). Když uživatel zadá adresu do prohlížeče, ten se nejprve dotáže DNS serveru, který mu sdělí, kde web fyzicky leží.
- ![](Obrazky/Web_app_DNS_server.png)
- **Struktura URL:** 
	- `https://` (protokol)
	- `www.google.com` (doména/host)
	- `/vyhledavani` (cesta)
	- `?q=dotaz` (query parametry) To se hodí později pro pochopení REST API a routování.
- Detailněji toto téma bude vysvětleno později.
### Hosting a nasazení
- Webová stránka musí někde fyzicky být uložená, aby ji mohli uživatelé navštívit. Hosting představuje službu, která nabízí prostor na serveru a připojení k internetu. Pro jednoduché statické stránky mohou být použity služby jako Netlify, Vercel nebo GitHub Pages.
	- Webovou stránku můžete hostovat i na obyčejném laptopu či raspberry pi!
- Komplexnější aplikace vyžadují serverový backend, databázi a někdy i více propojených služeb. Proces, kdy vývojář publikuje svou aplikaci na internet, se nazývá nasazení (deployment).
- Detailněji toto téma bude vysvětleno později.
### Client vs Server
- Webová architektura se většinou dělí na část klientskou (frontend) a serverovou (backend).
- **Klient** je uživatelův prohlížeč – zobrazuje obsah, provádí JavaScript a většinu interakcí.  
- **Server** je vzdálený počítač, který zpracovává požadavky, poskytuje data, generuje odpovědi a často komunikuje s databází.
- Frontend a backend spolu komunikují pomocí protokolů a struktur dat, nejčastěji pomocí HTTP a JSON.
- ![](Obrazky/Web_app_server_client.png)
- Detailněji toto téma bude vysvětleno později.
### Request a Response
- Komunikace mezi klientem a serverem probíhá na principu požadavků (request) a odpovědí (response). (můžeme vidět už na obrázku výše)
	- Klient odešle request – například „chci stránku /produkty“.
	- Server request zpracuje a vrátí response – HTML dokument, JSON data nebo chybu, pokud není požadavek platný.
- Pochopení tohoto cyklu je klíčové pro jakýkoli webový vývoj, protože většina aplikací neustále komunikuje se serverem.
- Detailněji toto téma bude vysvětleno později.
### Cookies, Session, LocalStorage
- Webové aplikace často potřebují uchovávat informace o uživateli – například, zda je přihlášen. K tomu slouží různé metody:
	- **Cookies**  
		- Malé textové soubory uložené v prohlížeči, často používané pro autentizaci.
	- **Session (relace)**  
		- Informace uložené na serveru, propojené s uživatelem pomocí cookie se session ID.
	- **LocalStorage**  
		- Trvalé lokální úložiště v prohlížeči, vhodné pro ukládání uživatelských preferencí nebo stavů aplikace.
- Každý způsob má své výhody a ideální použití, které vývojář musí znát.
- Detailněji toto téma bude vysvětleno později.
---
## Nástroje vývojáře webu
- Moderní webový vývoj se neopírá pouze o znalost HTML, CSS a JavaScriptu. Stejně důležitá je i orientace v nástrojích, které vývoj umožňují, zrychlují a zpříjemňují. Tato kapitola představuje základní vybavení každého webového vývojáře – od prohlížečů a jejich ladicích funkcí až po editor kódu, verzovací systémy a strukturu projektu.
- Cílem není jen ukázat jednotlivé nástroje, ale také vysvětlit jejich roli v běžném pracovním procesu, aby čtenář rozuměl nejen tomu _co_ použít, ale i _proč_.
### Moderní prohlížeče a DevTools
- Ať už vytváříme jednoduchou stránku nebo komplexní aplikaci, prvním a nejdůležitějším nástrojem je webový prohlížeč. Každý moderní prohlížeč – Google Chrome, Firefox, Safari nebo Edge – obsahuje zabudovanou sadu vývojářských nástrojů známou jako **DevTools**.
- DevTools umožňují:
	- prozkoumat HTML strukturu (DOM),
	- upravovat CSS v reálném čase,
	- sledovat síťové požadavky (Network tab),
	- odhalovat chyby v JavaScriptu pomocí debuggeru,
	- měřit výkon aplikace (Performance tab),
	- testovat různé velikosti obrazovky.
- Vývojář tak může rychle iterovat, odstraňovat chyby a optimalizovat chování aplikace. Znalost DevTools patří mezi základní dovednosti, které se vyplatí osvojit už na začátku.
- Do DevTools se dostaneme pomocí stisku klávesy `F12` a zobrazí se nám vpravo sloupec, jak můžeme vidět na obrázku níže.
- ![](Obrazky/Web_app_DevTools.png)
- Zde si můžeme povšimnout HTML kódu stránky, CSS nastavení jednotlivých HTML prvků a konzoli pro Javascript. 
- Pomocí kláves `Ctrl + Shift + C` můžeme na stránce vybrat jakýkoliv prvek k inspekci v HTML kódu.
- Pomocí kláves `Ctrl + Shift + M` se přepneme do módu, kde můžeme sledovat jak stránka mění vzhled, při jaké velikosti máme okno otevřené, či na jakém zařízení stránku navštěvujeme.
	- Toto je obzvláště využíváno, při stylování stránky pro telefony, tablety a počítače.
### VS Code a rozšíření
- Visual Studio Code (VS Code) se stal de facto standardem pro webový vývoj. Je lehký, přizpůsobitelný a podporuje stovky jazyků a frameworků prostřednictvím rozšíření.
- Mezi nejčastěji používané pluginy patří:
	- **ESLint** – kontrola kvality a konzistence JavaScript kódu
	- **Prettier** – formátování kódu
	- **Live Server** – automatické obnovování stránky při změně v souborech
	- **GitLens** – detailní informace o commitech a změnách v projektu
	- **Auto Rename Tag / IntelliSense** – usnadnění práce s HTML a JS
>[!NOTE]
> Pokud do Visual Studio Code nedoinstalujete pluginy, nebude vám nic z výše zmíněného fungovat. Visual Studio Code je v základu pouze textový editor! 
- VS Code navíc nabízí integrovaný terminál, možnost debugování a téměř neomezenou možnost přizpůsobení, což z něj číní ideální editor pro začátečníky i profesionály.
- ![](Obrazky/Web_app_VS_code.png)
- Jako alternativy zde máme
	- JetBrains WebStorm
		- Webstorm je velmi populární IDE pro webové vývojáře, které je kompatibilní s Windows, Mac a Linux. Podporuje jazyky jako HTML, JavaScript, Node.js, Angular, TypeScript, CSS, React a další. Je to nejchytřejší JavaScript IDE, díky čemuž vyniká jako nejlepší pro webový vývoj. Má také vynikající funkce pro dokončování kódu a refaktoring pro populární frameworky. Detekuje chyby a překlepy v kódu pomocí funkce analýzy kvality kódu. Je možné integrovat WebStorm s lintery jako Stylelint a ESLint. Má také vestavěného HTTP klienta v editoru pro úpravy, vytváření a spouštění HTTP požadavků. 
		- Zde jsou některé z funkcí WebStormu:
			- Masivní podpora pluginů
			- Správná navigace
			- Vestavěný debugger
			- Výkonný a přizpůsobitelný
			- Automatické doplňování kódu a nejlepší kompilace kódu
		- ![](Obrazky/Web_app_Webstorm.png)
### Git a GitHub
- Git je **distribuovaný verzovací systém**, který umožňuje sledovat historii projektu, bezpečně experimentovat, pracovat v týmu a kdykoliv se vracet ke starším verzím.  
- GitHub je pak **online služba**, která poskytuje vzdálené úložiště pro Git projekty, usnadňuje spolupráci, správu úkolů, code review a často i nasazování aplikací.
#### Proč Git existuje
- Představte si, že vyvíjíte web a potřebujete:
	- uložit si bezpečně práci,
	- porovnat, co se změnilo,
	- vrátit se ke starší verzi (třeba když se něco rozbije),
	- pracovat na nové funkci, aniž bychom rozbili stávající kód,
	- spolupracovat s dalšími vývojáři a řešit konflikty elegantně,
	- mít projekt uložený nejen na počítači, ale i online a stále dostupný.
- Na to všechno je Git.
#### GitHub a jeho role
- GitHub není Git – je to **platforma**, která:
	- hostuje repozitáře,
	- umožňuje přispívat do cizích projektů,
	- umožňuje schvalování změn (pull requesty),
	- poskytuje nástroje pro dokumentaci (README, Wiki),
	- nabízí automatizace (GitHub Actions),
	- funguje i jako portfolio vývojáře — zaměstnavatelé to milují.
#### Základní koncepty a operace
##### Repository (repozitář)
- „Projektová složka“ rozšířená o historii, větve a metadata.  
- Může být lokální (u tebe) nebo vzdálená (např. GitHub).
- ![](Obrazky/Web_app_repository.png)
##### Commit – uložení změn
- Commit je **základní jednotka historie**. Každý commit:
	- reprezentuje konkrétní změnu kódu,
	- má autora, čas a zprávu (message),
	- vytváří pomyslný „save point“.
- **Příklad zprávy:**  
	- `feat: přidána sekce s kontaktním formulářem`
- ![](Obrazky/Web_app_commit.png)
### Branch – větev pro vývoj
- Větve umožňují pracovat na nové funkci, opravě nebo experimentu **bez narušení hlavního kódu**.
- Běžná praxe:
	- `main` / `master` → stabilní, nasazovaná větev,
	- `dev` → vývojová větev,
	- feature větve → např. `feature/login-page`.
- Ukázku větví uvidíte níže společně s Merge / pull requesty
### Merge / Pull Request – začlenění změn
- Když dokončíš práci na větvi, chceš ji dostat do hlavní větve.
	- **Merge** provedeš lokálně nebo automaticky.
	- **Pull request (PR)** je GitHub metoda:  slouží k review kódu, debatě a schválení změn, než se sloučí.
- PR je základ týmové kultury.
- Merge větví následně vypadá takto:
- ![](Obrazky/Web_app_branches.png)
	- Může se stát, že nastane konflikt.
	- Konflikty vznikají, když se ve více větví pracuje na jednom souboru, a git neví, které změny má při merge větví uložit.
	- Konflikt se buď vyřeší automaticky, nebo se musíme rozhodnout kterou část změny, chceme přidat, či nepřidat.  
- Zde můžeme vidět jak vypadá pull request na Githubu.
- ![](Obrazky/Web_app_pull_req.png)
### Clone / Pull / Push – práce s remote verzemi
- **clone** – stáhne celý projekt k sobě,
- **fetch** - zjistí si zda nebyli na repozitáři změny,
- **pull** – stáhne popřípadě nové změny od ostatních,
- **push** – nahraje tvoje změny na GitHub.
Tento cyklus se používá neustále.
---
### Git v praxi – proč je nezbytný
- Umožňuje **vrátit nechtěné změny**.
- Zabraňuje tomu, aby se vývojáři **přepisovali navzájem**.
- Umožňuje **paralelní vývoj více funkcí**.
- V každé firmě je Git **standard** — bez něj se dnes vývojář neobejde.
- Pomáhá držet projekt čistý, přehledný a profesionální.
- Skutečná síla Gitu je v tom, že:
	- _nikdy o nic nepřijdeš,_
	- _můžeš pracovat kdykoliv a kdekoliv,_
	- _pokud něco rozbiješ, vždy máš únikovou cestu._
### Github desktop
- Pokud nejste zaběhlý v cmd, konzoli či terminálu nebo vám nepřijde intuitivní, existuje aplikace Github desktop.
- V této aplikaci dokážete skoro vše co potřebujete a to v GUI (grafickém rozhraní).
- ![](Obrazky/Web_app_Github_desktop.png)
### Struktura webového projektu
- Přehledná struktura projektu je základní předpoklad úspěšného vývoje. I malé projekty se mohou rychle stát nečitelnými, pokud se soubory organizují nahodile. Každý projekt může mít jiné rozvržení, avšak by správně měl dodržovat nějakou logiku!
#### Kořenová složka
- Obsahuje konfiguraci projektu a základní metadata.
- Typické soubory:
    - `package.json` – definice závislostí a skriptů pro npm/yarn,
    - `README.md` – dokumentace projektu, instrukce k nasazení,
    - `.gitignore` – seznam souborů, které Git ignoruje,
    - `.env` – environmentální proměnné (např. API klíče),
    - `vite.config.js` / `webpack.config.js` – konfigurace build nástroje.
#### Public / Static
- Statické soubory dostupné přímo z URL.
- Typicky obsahuje:
    - `index.html` – hlavní HTML stránku,
    - favicon, obrázky, ikony,
    - statické soubory CSS/JS, které se nemění během build procesu.
##### Src – zdrojový kód
- Hlavní složka pro **aplikaci samotnou**.
- Podrobný přehled:
###### Components / Widgets
- Opakovaně použitelné UI prvky (buttony, karty, formuláře).
- Příklad doporučený struktury:
```ls
src/components/Button/
  Button.jsx
  Button.css
  Button.test.js

```
- Oddělení logiky a stylů (CSS Modules / Styled Components) zvyšuje modularitu.
###### Pages / Views
- Reprezentují jednotlivé stránky nebo obrazovky SPA.
- Například: `Home.jsx`, `Dashboard.jsx`, `Login.jsx`.
###### Assets
- Grafika, fonty, ikonky, videa.
- Organizace složek podle typu (`images/`, `fonts/`, `icons/`) pomáhá udržet pořádek.
###### Styles / Themes
- Globální CSS/SCSS nebo Tailwind konfigurace.
- Případně motivy pro dark/light mode.
###### Services / API
- Funkce pro komunikaci s backendem.
- Např. `authService.js` (login/logout), `api.js` (fetch dat), `graphql.js` (GraphQL klient).
###### Hooks / Utils
- Vlastní hooky (React) a utility funkce.
- Například `useFetch.js`, `formatDate.js`.
###### State / Store
- Správa stavu aplikace (Redux, Zustand, Context API).
- Složka by měla obsahovat:
    - store,
    - slice/reducer,
    - akce (actions).
###### Config
- Konfigurace API endpointů, environmentální nastavení.
#### Test / **tests**
- Jednotkové a integrační testy.
- Struktura by měla odpovídat struktuře src, aby bylo jasné, co se testuje.
#### Build / Dist
- Výstupní složka po buildu.
- Obsahuje optimalizované HTML/CSS/JS soubory připravené k nasazení.
- Není verzována do Git (je zapsaná v `.gitignore`).
---
#### Doporučené postupy
- **Modularita:** Každá složka má jasnou zodpovědnost.
- **Consistency:** Stejný vzor složek a názvů napříč projekty.
- **Environmentální proměnné:** Nikdy nepíš citlivé údaje přímo do kódu.
- **Oddělení logiky a UI:** Lepší testovatelnost a údržba.
- Dobře navržená struktura šetří čas, usnadňuje orientaci novým členům týmu a předchází chaosu v kódu.
---
# Frontend – cesta od jednoduché stránky k aplikaci
## HTML – základ kostry webu

Vstupujeme do praktické části věnované frontendu. Základním stavebním kamenem každé webové stránky je **HTML** (**H**yper**T**ext **M**arkup **L**anguage).

Pokud chápeme webovou aplikaci jako celek, HTML definuje její **strukturu a obsah**. Je to kostra, která drží vše pohromadě.
* **HTML** (Struktura): Definuje, z jakých prvků se stránka skládá (nadpisy, odstavce, obrázky, formuláře).
* **CSS** (Prezentace): Popisuje, jak tyto prvky vizuálně vypadají (barvy, písma, rozložení).
* **JavaScript** (Chování): Řídí interaktivitu a dynamické chování aplikace.

Je důležité pochopit, že HTML není programovací jazyk. Je to **značkovací jazyk** (markup language). Pomocí definovaných značek (angl. **tags**) popisujeme jednotlivé části dokumentu – **elementy**. Prohlížeč následně tento dokument analyzuje, vytvoří z něj stromovou strukturu (DOM - Document Object Model) a vykreslí ji uživateli.

### První stránka
- Každý HTML dokument má základní, standardizovanou strukturu, která zajišťuje jeho správnou interpretaci prohlížečem. Následující kód představuje minimální kostru (boilerplate) validní HTML5 stránky.
- Uložte tento kód do souboru s názvem `index.html`:
```html
<!DOCTYPE html>
<html lang="cs">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Titulek stránky</title>
</head>
<body>
    <h1>Můj hlavní nadpis</h1>
    <p>Toto je první odstavec textu na mé webové stránce.</p>
</body>
</html>
```
- Po otevření tohoto souboru v prohlížeči uvidíte základní stránku s nadpisem a odstavcem.
- ![](../../Pasted%20image%2020251121234414.png)
#### Analýza základní struktury
- Pojďme si rozebrat jednotlivé řádky:
	- `<!DOCTYPE html>`: **Deklarace typu dokumentu**. Říká prohlížeči, že se jedná o moderní HTML5 dokument.
	- `<html lang="cs">...</html>`: **Kořenový element** celého dokumentu. Atribut `lang="cs"` specifikuje jazyk obsahu, což je důležité pro SEO a nástroje přístupnosti.
	- `<head>...</head>`: **Hlavička** dokumentu. Obsahuje metadata – informace _o_ stránce, které nejsou přímo viditelné v obsahu.
	    - `<meta charset="UTF-8">`: Definuje kódování znaků. UTF-8 je standard, který zajišťuje správné zobrazení diakritiky.
	    - `<meta name="viewport" ...>`: Klíčový meta tag pro **responzivní design**. Říká mobilním zařízením, aby stránku zobrazila ve své skutečné šířce.
	    - `<title>...</title>`: Definuje titulek stránky, který se zobrazuje v záložce (tabu) prohlížeče.
	- `<body>...</body>`: **Tělo** dokumentu. Tento element obsahuje veškerý viditelný obsah, který prohlížeč vykreslí – text, obrázky, tabulky, formuláře atd.
		- `<h1>...</h1>`: Element pro **nadpis první úrovně**.
		- `<p>...</p>`: Element pro **odstavec** (paragraf).
- Většina HTML elementů je párová – skládá se z otevírací značky (např. `<p>`) a uzavírací značky (např. `</p>`).
### Strukturování obsahu
- HTML poskytuje širokou škálu elementů pro sémantické strukturování textového obsahu.
- **Nadpisy:** `<h1>` až `<h6>` Definují hierarchii dokumentu. `<h1>` je nejvyšší úroveň (hlavní titulek stránky, měl by být pouze jeden) a `<h6>` nejnižší.
```html
    <h1>Hlavní téma</h1>
    <p>Text k hlavnímu tématu...</p>
    <h2>Podtéma 1</h2>
    <p>Text k podtématu...</p>
```
- **Seznamy:** **Nečíslovaný seznam** (Unordered List - `<ul>`) se používá pro položky, na jejichž pořadí nezáleží. Položky se definují značkou `<li>` (List Item).
```html
    <ul>
      <li>Položka A</li>
      <li>Položka B</li>
    </ul>
```
- **Číslovaný seznam** (Ordered List - `<ol>`) se používá pro položky, kde je pořadí důležité.
```html
    <ol>
      <li>Krok 1: Příprava</li>
      <li>Krok 2: Provedení</li>
    </ol>
```
- **Odkazy (Anchors):** Odkazy (`<a>`) jsou základem hypertextu. Klíčový je atribut `href` (Hypertext Reference), který určuje cíl odkazu.
```html
    <a href="[https://www.google.com](https://www.google.com)">Hledat na Google</a>
    
    <a href="/o-nas.html">O naší firmě</a>
```
- **Textová sémantika:**
    - `<strong>...</strong>`: Označuje text se **silnou důležitostí** (významově, ne jen vizuálně).
    - `<em>...</em>`: Označuje text s **důrazem** (emphasis).
    - `<b>...</b>` vs `<i>...</i>`: Na rozdíl od `<strong>` a `<em>` jsou tyto značky primárně pro vizuální odlišení (tučné, kurzíva) bez přidání sémantického významu.
    - `<br>`: Vloží zalomení řádku. Jde o **prázdný (nebo samo-uzavírací) element**.
    - `<hr>`: Vytvoří tematický předěl (horizontální čáru). Také prázdný element.
### Media (obrázky, video, audio)
- Pro vkládání multimediálního obsahu existují specializované elementy.
- **Obrázky:** `<img>` Element `<img>` je prázdný. Vyžaduje minimálně dva atributy:
    1. `src` (Source): Cesta k souboru obrázku.
    2. `alt` (Alternative text): Popis obrázku. **Je kriticky důležitý pro přístupnost** (čtečky obrazovek) a SEO. Zobrazí se také, pokud se obrázek nenačte.
```html
    <img src="obrazky/logo.png" alt="Logo naší společnosti" width="200" height="50">
```
    
> [!Note]
> Udávání atributů `width` a `height` je dobrá praxe. Pomáhá prohlížeči rezervovat místo pro obrázek ještě před jeho načtením, čímž zabraňuje "poskakování" layoutu (Layout Shift).

- **Video a Audio:** Tyto elementy jsou párové a umožňují vložení video a audio přehrávačů. Atribut `controls` zpřístupní uživateli standardní ovládací prvky.
```html
    <video src="media/promo.mp4" controls width="640">
      Váš prohlížeč nepodporuje HTML5 video.
    </video>
    
    <audio src="media/skladba.mp3" controls>
      Váš prohlížeč nepodporuje HTML5 audio.
    </audio>
```    

>[!note]
>Pro zajištění kompatibility napříč prohlížeči se často používá vnořený element `<source>`, který umožňuje specifikovat více formátů souboru.
### Formuláře
- Formuláře (`<form>`) jsou klíčovým prvkem pro sběr uživatelského vstupu.
- `<form>`: Obaluje celou skupinu formulářových prvků. Atribut `action` specifikuje URL, kam se data odešlou, a `method` (typicky `GET` nebo `POST`) určuje HTTP metodu.
- `<label>`: Popisek pro formulářový prvek. Pro zajištění přístupnosti je klíčové propojit `label` s `input`em pomocí atributu `for`, který odpovídá `id` daného `input`u.
- `<input>`: Univerzální vstupní prvek. Jeho chování se mění atributem `type`:
    - `type="text"`: Standardní textové pole.
    - `type="email"`: Pole pro e-mail s vestavěnou validací formátu.
    - `type="password"`: Pole pro heslo, kde je vstup maskován.
    - `type="checkbox"`: Zaškrtávací políčko.
    - `type="radio"`: Přepínač (vždy ve skupině se stejným `name`).
    - `type="submit"`: Tlačítko, které odešle formulář.
- `name`: Tento atribut je zásadní. Definuje "jméno" dat, které se odešle na server (např. `name="uzivatelske_jmeno"`).
- `<textarea>`: Víceřádkové textové pole.
- `<button type="submit">...</button>`: Flexibilnější varianta odesílacího tlačítka.
```html
<form action="/api/kontakt" method="POST">
    <div>
        <label for="frm-email">E-mail:</label>
        <input type="email" id="frm-email" name="email_address" required>
    </div>
    <div>
        <label for="frm-zprava">Zpráva:</label>
        <textarea id="frm-zprava" name="message_body" rows="5"></textarea>
    </div>
    <div>
        <button type="submit">Odeslat dotaz</button>
    </div>
</form>
```
### Best practices (sémantika, přístupnost)
- Kvalita HTML kódu se nehodnotí podle toho, jak vypadá, ale podle jeho **sémantické správnosti** a **přístupnosti**.
#### Sémantika
- Sémantické HTML znamená používání HTML elementů v souladu s jejich **významem**, nikoli pouze pro dosažení vizuálního efektu.
	- **Špatně (nesémanticky):** `<div class="nadpis">Novinky</div>` (Jen proto, že to přes CSS nastylujeme jako nadpis).
	- **Správně (sémanticky):** `<h2>Novinky</h2>` (Element má správný význam – je to nadpis 2. úrovně).
- **Proč?** Sémantický kód je lépe čitelný pro:
	1. **Vyhledávače (SEO):** Google lépe rozumí struktuře vašeho obsahu.
	2. **Nástroje přístupnosti:** Čtečky obrazovek pro nevidomé se spoléhají na sémantiku při navigaci.
	3. **Vývojáře:** Kód je přehlednější a snadněji udržovatelný.
- Kromě základních značek máme i elementy pro rozvržení stránky, které nahrazují generické `<div>` kontejnery:
	- `<header>`: Hlavička stránky (logo, hlavní navigace).
	- `<nav>`: Blok určený pro hlavní navigaci.
	- `<main>`: Definuje hlavní, unikátní obsah stránky.
	- `<section>`: Logická sekce dokumentu (např. "Naše služby", "Reference").
	- `<article>`: Samostatný, ucelený kus obsahu (blogový příspěvek, novinový článek).
	- `<footer>`: Patička stránky (copyright, doplňkové odkazy).
	- `<div>` a `<span>`: Jsou "nesémantické" kontejnery, které používáme pro stylování nebo seskupování, když žádný jiný sémantický element nedává smysl.
#### Přístupnost (Accessibility, a11y)
- Přístupnost (a11y) je disciplína zajišťující, aby webové aplikace mohl plnohodnotně používat kdokoli, bez ohledu na jeho fyzické či kognitivní schopnosti.
- Základní pilíře přístupnosti v HTML:
	1. **Sémantika:** Používejte správné elementy (`<nav>`, `<button>` atd.).
	2. **Atributy `alt`:** Vždy vyplňujte `alt` text u obrázků.
	3. **Propojení `label` a `input`:** U formulářů důsledně používejte `for` a `id`.
	4. **Hierarchie nadpisů:** Nepřeskakujte úrovně (např. z `<h1>` rovnou na `<h3>`).
### Mini-projekt: jednoduchý osobní web
- Aplikujte získané znalosti v malém praktickém projektu. Vytvořte nový soubor `o-mne.html`, který bude obsahovat:
	1. Korektní základní strukturu (`<!DOCTYPE>`, `<html>`, `<head>`, `<body>`).
	2. Hlavní nadpis `<h1>` s vaším jménem.
	3. Krátký odstavec `<p>` popisující vás.
	4. Obrázek (`<img>`) s vyplněným `src` a `alt` atributem.
	5. Podnadpis `<h2>` (např. "Moje dovednosti").
	6. Nečíslovaný seznam `<ul>` vašich dovedností nebo koníčků.
	7. Odkaz `<a>` na váš profesní profil (např. LinkedIn nebo GitHub).
- Soustřeďte se výhradně na korektní sémantickou strukturu. Vizuální stránkou se budeme zabývat v následující kapitole o CSS.

- Příklad:
`soubor: index.html`
```html
<html lang="cs"><head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Martin Novan - Profil webového vývojáře a tvůrce</title>
</head>
<body>
    <header>
        <h1>Martin Novan</h1>
        <p>Ahoj! Vítejte na mém webovém profilu.</p>
    </header>
    <main>
        <section>
            <h2>O mně a mých zájmech</h2>
            <p>Jsem vývojář, který se zaměřuje na robustní a čistá softwarová řešení. Neustále rozšiřuji své dovednosti v oblasti moderních frameworků a operačních systémů.</p>
            <img src="./Random_profile.png" alt="Martin Novan, vývojář pracující u počítače" width="300" height="300">
            <p>Aktuálně se v rámci osobních projektů intenzivně věnuji technologiím jako je **.NET MAUI**, **Avalonia UI** a skriptování pro **3D tiskárny (Klipper)**.</p>
        </section>
        <section>
            <h2>Technický Stack a Dovednosti</h2>
            <ul>
                <li><strong>Jazyky:</strong> C#, Python, SQL, HTML, CSS, JavaScript.</li>
                <li><strong>Frameworky / UI:</strong> .NET, WPF, AvaloniaUI, MAUI.</li>
                <li><strong>Databáze:</strong> MySQL, SQL, Microsoft SQL.</li>
                <li><strong>OS/Nástroje:</strong> Arch Linux, Klipper (Firmware).</li>
            </ul>
        </section>
        <section>
            <h2>Vybrané projekty</h2>
            <article>
                <h3>Simple Virtual PC Management (SVPM)</h3>
                <p>Nástroj pro správu virtuálních PC, zákazníků a jejich vztahů. Systém zahrnuje komplexní <strong>Customer Management</strong>, správu konfigurací, auditování změn a zabezpečení integrity dat pomocí **Hash Verification**.</p>
            </article>
            <article>
                <h3>Endeaxim-3 (Hardware Upgrade Kit)</h3>
                <p>Komplexní upgrade kit pro 3D tiskárnu Creality Ender 3. Projekt zahrnuje **Hardware Upgrades** (Dual Z-axis, Linear Rail), implementaci **Klipper Firmware** na Raspberry Pi a optimalizaci pro vysoké rychlosti. K dispozici jsou také **STEP soubory** pro precizní modely.</p>
            </article>
        </section>
    </main>
    <footer>
        <nav>
            <p>Najdete mě zde:</p>
            <ul>
                <li><a href="https://github.com/MartinNovan" target="_blank">GitHub Profil (My Repositories)</a></li>
            </ul>
        </nav>
        <p>© 2025 Martin Novan. Všechna práva vyhrazena.</p>
    </footer>
</body>
</html>
```
![](../../Pasted%20image%2020251121235221.png)

---
## CSS – Vzhled a Design
- CSS je jazyk, který popisuje **prezentaci** dokumentu napsaného v HTML. Zatímco HTML definuje **co** na stránce je, CSS definuje **jak** se to má uživateli zobrazit (barvy, písma, rozměry, pozice).
- Představte si to takto: HTML je hrubý textový dokument. CSS jej promění v uživatelské rozhraní.
### Jak funguje CSS
- CSS kód se skládá z **pravidel** (rules), kde každé pravidlo má:
	1. **Selektor:** Cílí na konkrétní HTML element nebo skupinu elementů.
	2. **Deklarační blok:** Obsahuje jednu nebo více **deklarací**.
	    - **Vlastnost (Property):** Co chceme měnit (např. `color`).
	    - **Hodnota (Value):** Jakou hodnotu má vlastnost dostat (např. `blue`).
```css
/* Selektor cílí na všechny elementy <h1> */
h1 {
    /* Deklarace 1: Vlastnost: barva, Hodnota: modrá */
    color: blue; 
    /* Deklarace 2: Vlastnost: velikost písma, Hodnota: 32 pixelů */
    font-size: 32px; 
}
```
- CSS kód umisťujeme buď:
	- **Inline:** Přímo do atributu `style` v HTML elementu (nedoporučeno pro profesionální vývoj).
	- **Interní:** Do bloku `<style>` v `<head>` HTML dokumentu.
	- **Externí:** Do samostatného souboru (`style.css`), který je připojen v `<head>` pomocí `<link rel="stylesheet" href="style.css">` (standardní a **doporučovaný postup**).
---
### Selektory, Kaskáda, Specifita
- Základem efektivní práce s CSS je pochopení, **jak a proč** se styly aplikují.
#### Selektory
- Selektory umožňují cílit na přesné elementy, které chceme stylovat:

|**Typ Selektoru**|**Příklad**|**Popis**|
|---|---|---|
|**Element**|`p { ... }`|Cílí na **všechny** elementy `<p>`.|
|**Třída**|`.karta { ... }`|Cílí na elementy s atributem `class="karta"`. **Nejčastěji používaný typ.**|
|**ID**|`#logo { ... }`|Cílí na **jediný** element s atributem `id="logo"`.|
|**Potomek**|`div p { ... }`|Cílí na elementy `<p>`, které jsou **uvnitř** elementu `<div>`.|
|**Atribut**|`input[type="text"] { ... }`|Cílí na elementy `<input>` s konkrétním atributem.|

#### Kaskáda (The Cascade)
- "Cascading" v názvu CSS znamená, že styly se **překrývají a slučují** z různých zdrojů (např. styl prohlížeče, styl uživatele, váš styl). Proces řešení konfliktů se řídí pravidly kaskády, která určují pořadí, v jakém se styly aplikují.
	- **Pravidlo:** Pozdější pravidla přepisují ta dříve definovaná. (Pokud v `style.css` definujete barvu odstavce červenou a v navazujícím `theme.css` modrou, bude finální barva modrá).
#### Specifita (Specificity)
- Pokud se dva různé selektory snaží stylovat stejnou vlastnost stejného elementu, rozhoduje **specifita** (váha) selektoru. Čím je selektor přesnější, tím je jeho váha vyšší a jeho pravidlo má přednost.
- **Váha selektorů (od nejvyšší po nejnižší):**
    1. **Inline styl** (Nejvyšší váha).
    2. **ID** (`#logo`).
    3. **Třídy**, pseudo-třídy a atributy (`.karta`, `[type="text"]`).
    4. **Elementy** (`p`, `h1`).
    
> [!Note] **Příklad konfliktu:** 
> Styl definovaný pomocí `.telo` vždy přepíše styl definovaný pouze elementem `body`, protože selektor třídy má vyšší specifitu než selektor elementu.

---
### Barvy, Typografie, Spacing
- Tyto vlastnosti tvoří základy vizuální konzistence a čitelnosti.
#### Barvy
- Barvy lze definovat různými formáty:
	- **Hexadecimální:** `#ff5733` (Standard).
	- **RGB/RGBA:** `rgb(255, 87, 51)` / `rgba(255, 87, 51, 0.5)` (Poslední hodnota 'A' je **alfa kanál**, určuje průhlednost 0.0 - 1.0).
	- **Názvy:** `red`, `blue`.
#### Typografie (Písmo)
- Elementy ovlivňující text:
	- `font-family`: Nastavuje rodinu písma (např. `Arial, sans-serif`). **Vždy uvádějte fallback písma!**
	- `font-size`: Velikost písma (`px`, `em`, `rem`).
	- `font-weight`: Tloušťka písma (`normal`, `bold`, nebo číselně 100-900).
	- `line-height`: Výška řádku (klíčové pro čitelnost).
	- `text-align`: Zarovnání textu (`left`, `center`, `right`).
#### Spacing (Mezery)
- Pro kontrolu mezer mezi elementy se používají dva klíčové modely:
	1. **Padding (Vnitřní okraj):** Mezera mezi **obsahem** elementu a jeho **hranicí (border)**.
	2. **Margin (Vnější okraj):** Mezera **vně** hranice elementu, oddělující jej od okolních elementů.
#### Box Model
- Každý HTML element je v CSS považován za obdélníkový box. **Box Model** definuje, jak se počítají celkové rozměry tohoto boxu:
$$\text{Celková šířka} = \text{šířka} + \text{padding-left} + \text{padding-right} + \text{border-left} + \text{border-right}$$
>[!Tip] **Tip:** 
>Používání vlastnosti `box-sizing: border-box;` ve vašem CSS zjednodušuje výpočty, protože pak platí, že šířka zahrnuje padding a border.

---
### Flexbox (`display: flex`)
- Flexbox (Flexibilní Box Model) je jednorozměrný layoutový systém určený pro **distribuci prostoru mezi položkami v jednom řádku nebo sloupci**. Je ideální pro tvorbu navigace, malých komponent a zarovnávání obsahu.
- **Koncept:**
	- **Flex kontejner:** Element, na který aplikujeme `display: flex;`.
	- **Flex položky:** Přímí potomci kontejneru.
- **Klíčové vlastnosti kontejneru:**
	- `flex-direction`: Definuje hlavní osu (`row` nebo `column`).
	- `justify-content`: Řídí zarovnání položek **podél hlavní osy** (např. `space-between`, `center`).
	- `align-items`: Řídí zarovnání položek **kolmo k hlavní ose** (např. `center`, `flex-start`).
```css
.navigace {
    display: flex; /* Udělá z elementu flex kontejner */
    justify-content: space-between; /* Rozprostře položky rovnoměrně */
}
```

---
### Grid (`display: grid`)
- CSS Grid je **dvourozměrný** layoutový systém, který umožňuje rozdělit prostor stránky na řádky a sloupce. Je ideální pro **celkové rozložení stránky** (layout), kde potřebujeme přesně definovat umístění velkých bloků (header, sidebar, footer).
- **Koncept:**
	- **Grid kontejner:** Element, na který aplikujeme `display: grid;`.
	- **Grid položky:** Přímí potomci kontejneru.
- **Klíčové vlastnosti kontejneru:**
	- `grid-template-columns`: Definuje sloupce a jejich šířky.
	- `grid-template-rows`: Definuje řádky a jejich výšky.
	- Jednotka **`fr` (fractional unit)**: Umožňuje automaticky rozdělit zbývající prostor mezi sloupce.
```css
.layout {
    display: grid;
    /* 3 sloupce: sidebar 200px, hlavní obsah zabere 2/3 volného místa, sidebar 1/3 */
    grid-template-columns: 200px 2fr 1fr;
    gap: 16px; /* Mezera mezi řádky a sloupci */
}
```

---
### Responzivita (`@media queries`)
- Responzivní design zajišťuje, že se web správně zobrazuje na všech zařízeních (mobily, tablety, desktopy). Klíčovým nástrojem jsou **Media Queries**.
- **Media Query** je pravidlo, které aplikuje styly, **pouze pokud je splněna určitá podmínka**.
	- **Pravidlo Mobile-First:** Doporučuje se nejprve stylovat pro mobilní zařízení (nejmenší obrazovky) a media queries používat pro styly, které se mají **přidat pro větší obrazovky**.
```css
/* Styly platné pro VŠECHNA zařízení (mobilní základ) */
.karta {
    width: 100%; /* Mobil: šířka 100% */
}

/* Styly, které se aplikují POUZE, když je šířka okna (viewport) alespoň 768px */
@media screen and (min-width: 768px) {
    .karta {
        width: 300px; /* Tablet a desktop: pevná šířka */
        float: left;
    }
}
```

>[!Note] **Zásada:** 
>Media queries se nejčastěji cílí na šířku (např. `min-width` nebo `max-width`) a umožňují nám měnit layout (např. přechod z vertikálního Flexboxu na horizontální Grid).

---
### Animace a Přechody (Transitions)
- CSS umožňuje plynulé vizuální efekty bez nutnosti JavaScriptu.
#### Přechody (Transitions)
- Transitions umožňují plynulý přechod mezi dvěma stavy elementu (např. ze žluté barvy na modrou po najetí myší).
```css
.tlacitko {
    background-color: blue;
    transition: background-color 0.3s ease-in-out; /* Doba přechodu 0.3 sekundy */
}

.tlacitko:hover {
    background-color: darkblue; /* Změna se stane plynule */
}
```
#### Animace (Animations)
- Animations umožňují definovat složitější sekvenci změn pomocí **Keyframes**.
	1. **Definice Keyframes:** Určuje, jaké vlastnosti a v jakých krocích se mají měnit.
	2. **Aplikace Animace:** Přiřazení definované animace elementu.
```css
/* 1. Definice animace */
@keyframes rotace {
    0%   { transform: rotate(0deg); }
    100% { transform: rotate(360deg); }
}

/* 2. Aplikace animace na element */
.ikona {
    animation-name: rotace;
    animation-duration: 2s; /* Trvání */
    animation-iteration-count: infinite; /* Opakování donekonečna */
    animation-timing-function: linear; /* Rychlostní křivka */
}
```

---
### Preprocesory (Sass)
- Sass (Syntactically Awesome Style Sheets) je **CSS preprocesor**. Jde o nástroj, který rozšiřuje CSS o funkce, které běžné CSS neumožňuje (např. proměnné, vnoření, mixiny).
	- **Proč Sass?** Umožňuje psát **organizovanější, modulárnější a efektivnější** CSS.
	- **Princip:** Kód píšete v syntaxi Sass (`.scss` soubory) a následně jej **kompilátor** (compiler) převede zpět na čisté, standardní CSS (`.css`), kterému prohlížeče rozumí.
#### Klíčové funkce Sass:
- **Proměnné:** Umožňují opakovaně používat hodnoty (např. barvy, fonty).
```scss
    $primarni-barva: #3498db;
    
    .hlavicka {
        background-color: $primarni-barva;
    }
```
- **Vnoření (Nesting):** Umožňuje vnořit selektory do sebe, což kopíruje hierarchii HTML.
```scss
    .navigace {
        padding: 20px;
    
        a { /* Bude zkompilováno na .navigace a */
            color: white;
    
            &:hover { /* Bude zkompilováno na .navigace a:hover */
                text-decoration: underline;
            }
        }
    }
```
- **Mixiny:** Umožňují vytvářet znovupoužitelné bloky CSS kódů (např. pro vendor prefixy nebo složité styly).
---
### Mini-projekt: Responzivní Osobní Web
- Nyní aplikujte své znalosti CSS na váš předchozí HTML projekt (`o-mne.html`).
- **Cíl:** Vytvořte soubor `style.css` a propojte jej s HTML. Stylujte web tak, aby byl **responzivní** a profesionální.
- **Požadavky:**
	1. **Základní styly:** Nastavte písmo, barvy pozadí a textu.
	2. **Flexbox:** Použijte Flexbox pro zarovnání prvků v hlavičce (`<header>` nebo `<nav>`).
	3. **Grid nebo Flexbox:** Použijte Grid nebo Flexbox k uspořádání sekcí s projekty (např. dva sloupce na desktopu).
	4. **Responzivita:** Pomocí **@media query** zajistěte, že na mobilních zařízeních (pod 768px) se sloupce z bodu 3 změní na **jeden sloupec** (`width: 100%`).
	5. **Přechod (Transition):** Přidejte jednoduchý `transition` na tlačítko nebo odkaz (např. při `hover` efektu).

- Příklad
`soubor: style.css`
```css
/* 1. ZÁKLADNÍ NASTAVENÍ (RESET) */ 
/* Zajišťuje, že se padding a border počítají dovnitř šířky elementu (border-box) */
*, *::before, *::after {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
} 
/* Nastavení základního fontu a barvy pozadí / textu */
body {
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    line-height: 1.6;
    color: #333; /* Tmavá barva textu */
    background-color: #f4f4f9; /* Světle šedé pozadí */
} 
/* 2. TYPOGRAFIE A ZÁKLADNÍ VZHLED */ 
h1, h2, h3 {
    margin-bottom: 0.5em;
    line-height: 1.2;
    color: #007bff; /* Modrá jako primární barva */
} 
h1 {
    font-size: 2.5rem; /* Větší velikost pro hlavní nadpis */
    color: #f4f4f9; /* Světle šedá pro kontrast s modrým pozadím */
} 
h2 {
    font-size: 1.8rem;
    padding-top: 1em;
    border-bottom: 2px solid #ddd;
    margin-bottom: 1em;
} 
ul {
    list-style-type: disc;
    margin-left: 20px;
} 
/* Stylování obrázku */
img {
    max-width: 100%; /* Zajištění, že obrázek nepřeteče rodičovský kontejner */
    height: auto;
    border-radius: 8px; /* Jemné zaoblení rohů */
    margin: 15px 0;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
} 
/* 3. ROZVRŽENÍ A FLEXBOX (LAYOUT) */ 
.container {
    /* Centrujeme obsah na stránce a dáváme mu maximální šířku */
    max-width: 1200px;
    margin: 0 auto;
    padding: 20px;
} 
header, footer {
    background-color: #007bff;
    color: white;
    padding: 1.5em 20px;
    text-align: center;
} 
/* Vytvoření kontejneru pro navigaci/patičku pomocí Flexboxu */
footer nav {
    display: flex;
    justify-content: center; /* Centrování obsahu (text a seznam) */
    align-items: center;
    flex-wrap: wrap; /* Umožní zalomení na malých obrazovkách */
    gap: 20px;
} 
footer nav ul {
    list-style: none; /* Odstranění odrážek */
    margin: 0;
    display: flex; /* Vodorovné zarovnání odkazů */
    gap: 20px;
} 
/* Vytvoření Flex/Grid kontejneru pro sekci Vybrané projekty */
#projekty-kontejner {
    display: flex; /* Flexbox je ideální pro karty */
    flex-direction: column; /* MOBILE-FIRST: ve výchozím stavu řadíme vertikálně (sloupec) */
    gap: 25px;
    margin-top: 20px;
} 
article {
    background-color: white;
    padding: 20px;
    border-left: 5px solid #007bff; /* Vizuální akcent */
    border-radius: 4px;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.05);
} 
/* 4. RESPONZIVITA (@MEDIA QUERIES) */ 
/* Aplikuje se, když je šířka okna (viewport) alespoň 768px (Tablet a Desktop) */
@media screen and (min-width: 768px) {
    
    /* Změna layoutu projektů z vertikálního na horizontální pomocí Flexboxu */
    #projekty-kontejner {
        flex-direction: row; /* Změna na horizontální uspořádání */
    } 
    /* Každý projekt zabere polovinu dostupného místa */
    #projekty-kontejner article {
        flex: 1 1 45%; /* Flex: grow shrink basis (umožní růst/smrsknutí a základní velikost) */
    } 
    /* Větší padding na velkých obrazovkách */
    main section {
        padding: 40px 0;
    }
} 
/* 5. INTERAKTIVNÍ PRVKY (TRANSITIONS) */ 
/* Stylování odkazů */
a {
    color: white; /* Barva odkazu ve footeru */
    text-decoration: none;
    padding-bottom: 2px;
    border-bottom: 2px solid transparent; /* Průhledná čára pro hladký přechod */
    
    /* Nastavení přechodu pro barvu textu a podtržení */
    transition: color 0.3s ease-in-out, border-color 0.3s ease-in-out; 
} 
/* Efekt při najetí myší (hover) */
a:hover {
    color: #e2e6ea; /* Mírně světlejší barva */
    border-bottom: 2px solid #e2e6ea; /* Zviditelnění podtržení */
}
```

`soubor: index.html`
```html
<!DOCTYPE html>
<html lang="cs">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Martin Novan - Profil webového vývojáře a tvůrce</title>
    <link rel="stylesheet" href="style.css"> 
</head>
<body>
    <header class="container">
        <h1>Martin Novan</h1>
        <p>Ahoj! Vítejte na mém webovém profilu.</p>
    </header>
    <main class="container">
        <section>
            <h2>O mně a mých zájmech</h2>
            <img src="./Random_profile.png" alt="Martin Novan, vývojář pracující u počítače" width="100" height="100">
            <p>Jsem vývojář, který se zaměřuje na robustní a čistá softwarová řešení. Neustále rozšiřuji své dovednosti v oblasti moderních frameworků a operačních systémů.</p>
            <p>Aktuálně se v rámci osobních projektů intenzivně věnuji technologiím jako je **.NET MAUI**, **Avalonia UI** a skriptování pro **3D tiskárny (Klipper)**.</p>
        </section>
        <section>
            <h2>Technický Stack a Dovednosti</h2>
            <ul>
                <li><strong>Jazyky:</strong> C#, Python, SQL, HTML, CSS, JavaScript.</li>
                <li><strong>Frameworky / UI:</strong> .NET, WPF, AvaloniaUI, MAUI.</li>
                <li><strong>Databáze:</strong> MySQL, SQL, Microsoft SQL.</li>
                <li><strong>OS/Nástroje:</strong> Arch Linux, Klipper (Firmware).</li>
            </ul>
        </section>
        <section>
            <h2>Vybrané projekty</h2>
            
            <div id="projekty-kontejner">
                
                <article>
                    <h3>Simple Virtual PC Management (SVPM)</h3>
                    <p>Nástroj pro správu virtuálních PC, zákazníků a jejich vztahů. Systém zahrnuje komplexní <strong>Customer Management</strong>, správu konfigurací, auditování změn a zabezpečení integrity dat pomocí **Hash Verification**.</p>
                </article>
                
                <article>
                    <h3>Endeaxim-3 (Hardware Upgrade Kit)</h3>
                    <p>Komplexní upgrade kit pro 3D tiskárnu Creality Ender 3. Projekt zahrnuje **Hardware Upgrades** (Dual Z-axis, Linear Rail), implementaci **Klipper Firmware** na Raspberry Pi a optimalizaci pro vysoké rychlosti. K dispozici jsou také **STEP soubory** pro precizní modely.</p>
                </article>
                
            </div> 
        </section>
    </main>
    <footer>
        <nav>
            <p>Najdete mě zde:</p>
            <ul>
                <li><a href="https://github.com/MartinNovan" target="_blank">GitHub Profil (My Repositories)</a></li>
            </ul>
        </nav>
        <p>© 2025 Martin Novan. Všechna práva vyhrazena.</p>
    </footer>
</body>
</html>
```
- Vzhled:
	- ![](../../Pasted%20image%2020251122002141.png)
- Responsivita animace:
	- ![](Obrazky/Web_app_responsive.gif)

---
## UI/UX pro web
- V předchozích kapitolách jsme se naučili, jak vytvořit strukturu stránky (HTML) a jak ji vizuálně nastylovat (CSS). Nyní se posuneme o úroveň výš. Nestačí, aby stránka *nějak* vypadala; musí také *skvěle fungovat* a být *příjemná na používání*.
- To nás přivádí k disciplínám **UI** a **UX**.
	* **UI (User Interface – Uživatelské rozhraní):** Je to, co uživatel **vidí**. Je to vizuální vrstva – rozložení, barvy, tlačítka, písmo. Je to "vzhled a dojem" (look and feel) aplikace. Náš `style.css` je v podstatě implementace UI.
	* **UX (User Experience – Uživatelský prožitek):** Je to, jak se uživatel **cítí** při používání aplikace. Je navigace logická? Najde rychle, co hledá? Je proces objednávky bezproblémový? Je to celkový prožitek, který UI pomáhá utvářet.
>[!Note] **Analogie:** 
>Představte si auto. **UI** je barva laku, tvar palubní desky, materiál potahů a design tlačítek. **UX** je pocit z jízdy, snadnost, s jakou najdete ovládání klimatizace, a jistota, kterou cítíte při řízení. Můžete mít krásné auto (dobré UI), které se otřesně řídí (špatné UX). Naším cílem je obojí.
### Designové principy
- Dobré UI/UX není náhoda; řídí se osvědčenými principy, které pomáhají uživateli dosáhnout cíle bez frustrace.
	1.  **Konzistence (Consistency):**
		- Nejdůležitější princip. Tlačítko "Odeslat" by mělo vypadat stejně na každé stránce. Navigace by měla být vždy na stejném místě. Konzistence buduje důvěru a snižuje "kognitivní zátěž" – uživatel se nemusí na každé stránce učit něco nového.
	2.  **Hierarchie (Hierarchy):**
		- Vizuální hierarchie říká uživateli, co je nejdůležitější. V HTML jsme to dělali sémanticky (`<h1>` je důležitější než `<h2>`). V CSS toho dosahujeme velikostí písma, tloušťkou (`font-weight`) nebo barvou. Uživatelovo oko musí být přirozeně vedeno k nejdůležitější akci (např. "Koupit nyní").
	3.  **Zpětná vazba (Feedback):**
		- Uživatel musí vždy vědět, co se děje.
		    * Klikl na odkaz? Odkaz by měl změnit barvu (`:visited`).
		    * Najíždí na tlačítko? Tlačítko by mělo reagovat (`:hover`).
		    * Odeslal formulář? Musí vidět zprávu "Úspěšně odesláno" nebo "Chyba: E-mail je neplatný". Ticho je nejhorší UX.
	4.  **Jednoduchost a srozumitelnost (Clarity):**
		- Každý prvek na stránce by měl mít jasný účel. Pokud stránka vypadá přeplácaně, uživatel neví, co má dělat. Držte se pravidla: **"Don't make me think"** (Nenuťte mě přemýšlet).
	5.  **Bílé místo (White Space):**
		- Prostor *mezi* prvky (napsaný v CSS jako `margin` a `padding`) je stejně důležitý jako prvky samotné. Dává obsahu prostor "dýchat", zlepšuje čitelnost a pomáhá oddělovat logické celky.
### Barvy, kontrast, tón
- Barvy nejsou jen dekorace; jsou to mocné nástroje komunikace.
	* **Tón:** Volba barev nastavuje emocionální tón. Jasné, syté barvy působí energicky (vhodné pro startup nebo sport). Tlumené, tmavé tóny (jako v našem mini-projektu) působí profesionálně a technicky.
	* **Barevná paleta:** Profesionální weby nepoužívají 20 různých barev. Drží se omezené palety. Běžné pravidlo je **60-30-10**:
	    * **60 %** Primární barva (např. pozadí, hlavní plochy).
	    * **30 %** Sekundární barva (např. hlavička, patička, karty).
	    * **10 %** Akcentní barva (např. tlačítka, odkazy, důležité prvky).
#### Kontrast a Přístupnost (Accessibility)
- Nejdůležitější pravidlo při práci s barvami. **Kontrast** je rozdíl v jasu mezi textem a jeho pozadím.
	* **Špatný kontrast** (např. světle šedé písmo na bílém pozadí) je nečitelný pro lidi se slabším zrakem a nepříjemný pro všechny ostatní.
	* **Dobrý kontrast** (např. tmavě šedé písmo na bílém pozadí) je snadno čitelný.
- Profesionální standardy (**WCAG** - Web Content Accessibility Guidelines) definují přesné poměry kontrastu, které musíte splnit. Vždy si své barevné kombinace kontrolujte v online nástrojích (hledejte "Contrast Checker"). Tím zajistíte, že váš web je **přístupný** pro co nejvíce lidí.
### Tvorba layoutu
- Než začneme psát kód, musíme vědět, *kam* prvky umístit.
	1.  **Drátové modely (Wireframes):**
		- Jsou to nízkoúrovňové (low-fidelity) náčrty – v podstatě "architektonický plán" webu. Soustředí se pouze na rozložení a strukturu, zcela ignorují barvy a písmo. Často se kreslí jen tužkou na papír nebo v jednoduchých online nástrojích.
	2.  **Mockupy (Vizuální návrhy):**
		- Jsou to vysoce věrné (high-fidelity) návrhy, které vypadají přesně tak, jak má finální produkt vypadat. Zahrnují reálné barvy, písma a obrázky. Vytvářejí se v nástrojích jako **Figma**, Sketch nebo Adobe XD. Náš `style.css` byl v podstatě kódováním takového (myšleného) mockupu.
	3.  **Běžné skenovací vzory (Scanning Patterns):**
		- Uživatelé na webu nečtou – skenují. V západním světě sledují jejich oči nejčastěji dva vzory:
		    * **F-Pattern:** Uživatel skenuje horní část stránky (horní lišta "F"), pak sjede pohledem níže a skenuje další horizontální řádek (kratší lišta "F"). Typické pro blogy a zpravodajství.
		    * **Z-Pattern:** Oko přejede zleva doprava nahoře, pak diagonálně dolů doleva a opět zleva doprava dole. Typické pro jednodušší stránky a "landing pages".
- Znalost těchto vzorů vám pomůže umístit nejdůležitější prvky (jako tlačítko "Registrovat") tam, kam se uživatel přirozeně podívá.
### Praktický UI kit
- Ať už pracujete sami nebo v týmu, klíčem k udržitelnosti a konzistenci je **UI Kit** (nebo "Design System"). Je to sbírka všech znovupoužitelných komponent a definovaných pravidel pro váš projekt.
- Představte si ho jako vaši osobní "knihovnu" designových prvků.
#### Co typický UI Kit obsahuje:
* **1. Základy (Foundations):**
    * **Barevná paleta:** (Přesné HEX kódy pro vaši primární, sekundární a akcentní barvu).
    * **Typografie:** (Jak vypadá `<h1>`, `<h2>`, `<p>`, `<a>`).
    * **Mezery (Spacing):** (Jaké jsou vaše standardní hodnoty `margin` a `padding`, např. 8px, 16px, 24px).
* **2. Komponenty (Components):**
    * **Tlačítka (Buttons):** Jak vypadá primární tlačítko? Sekundární? Jak vypadají ve stavu `:hover` nebo `:disabled`?
    * **Karty (Cards):** Jak vypadá `article` v našem projektu? Má mít stín? Zaoblené rohy?
    * **Formulářové prvky:** Jak vypadá `input`, `label`, `checkbox`?
- V našem mini-projektu by UI Kit znamenal, že bychom si definovali: 
	- "Všechna `<h2>` budou mít velikost `1.8rem` a spodní linku `2px solid #ddd`." 
	- Když pak přidáme novou sekci, jen použijeme `<h2>` a máme zaručenou konzistenci.
---
## JavaScript – základy logiky webu
- Doposud jsme vytvořili kostru (HTML) a dali jí vzhled (CSS). Náš web je ale stále statický – je to jen hezký dokument. Nyní přidáme **"mozek"** a **"svaly"** pomocí **JavaScriptu (JS)**.
- JavaScript je **programovací jazyk**, který běží přímo v prohlížeči uživatele. 
  Umožňuje nám:
	* **Reagovat na akce uživatele** (kliknutí, vyplnění formuláře, scrollování).
	* **Dynamicky měnit obsah** stránky bez nutnosti jejího znovunačtení.
	* **Komunikovat se serverem** na pozadí (načítat nová data, odesílat formuláře).
	* Provádět výpočty, animovat prvky a mnoho dalšího.
---
### Proměnné, funkce, cykly
- Toto jsou základní stavební bloky jakéhokoliv programovacího jazyka.
#### Proměnné (Variables)
- Proměnné jsou "kontejnery" pro ukládání dat (čísla, text, objekty). V moderním JS používáme dvě klíčová slova:
- **`let`**: Pro proměnné, jejichž hodnota se **může změnit**.
```javascript
    let vek = 30;
    vek = 31; // OK
```
-  **`const`**: Pro konstanty, jejichž hodnota se **měnit nesmí**. Je to preferovaný způsob, pokud víte, že hodnotu měnit nebudete (zvyšuje bezpečnost a čitelnost kódu).
```javascript
    const jmeno = "Martin";
    // jmeno = "Petr"; // Vyhodí chybu! (snažíme se měnit konstantu)
```

>[!Note] **Poznámka:** 
>- Dříve se používalo klíčové slovo `var`. Dnes se jeho používání nedoporučuje kvůli jeho matoucímu chování (tzv. hoisting a funkční scope). Vždy preferujte `let` a `const`.
>	- **Hoisting**: je chování, při kterém se deklarace (nikoli inicializace) proměnných, funkcí a tříd přesunou na začátek jejich rozsahu (scope) během kompilace.
>	- **Funkční scope**: Je oblast, kde jsou proměnné a funkce vytvořené uvnitř funkce dostupné pouze uvnitř této funkce.
#### Datové typy
- Základní typy dat, se kterými pracujeme:
    - **`string`**: Text (`"Ahoj světe"`)
    - **`number`**: Číslo (`10`, `3.14`)
    - **`boolean`**: Pravda / Nepravda (`true`, `false`)
    - **`array`**: Seznam hodnot (`[1, "text", true]`)
    - **`object`**: Kolekce dat ve formátu „klíč: hodnota” (`{ jmeno: "Martin", vek: 20 }`)
    - **`null`**: Záměrně prázdná hodnota – říká: „tady nic není“ (`null`)
    - **`undefined`**: Hodnota, která ještě nebyla nastavena (`let x; // undefined`)
    - **`bigint`**: Velká čísla mimo rozsah typu `number` (`12345678901234567890n`)
    - **`symbol`**: Unikátní identifikátor – používá se pro speciální případy (`Symbol("id")`)
    - **`function`**: V JS funkce fungují také jako datový typ (`function pozdrav() {}`)
>[!Note] `null` vs `undefined`
> `undefined`
> 	- Hodnota, která _vznikla sama_, protože ji JavaScript ještě nedostal.
> 	- Nastává například když:
> 		- deklaruješ proměnnou, ale nic do ní nedáš
> ```javascript
> let x; console.log(x); // undefined
> ```
> - funkce nic nevrátí
> - objekt nemá danou vlastnost
> - **`undefined` = „Nevím, co tady má být.“**
> ---
> `null`
> - Hodnota, kterou _dáš záměrně_, aby řekla: „Tady nic není.“
> - Například:
> ```javascript
> let uzivatel = null; // aktuálně žádný přihlášený uživatel
> ```
>- Používá se tehdy, když **chceš říct, že hodnota existuje, ale je prázdná**.
>- **`null` = „Vím, že to tu má být, ale nemá to žádnou hodnotu.“**
#### Funkce (Functions)
- Funkce jsou znovupoužitelné bloky kódu, které provádějí specifický úkol.
```javascript
// Tradiční deklarace funkce
// Funkci můžeš volat kdykoliv poté i předtím (hoisting ji zvedne nahoru).
function pozdrav(jmeno) {
    // Funkce může přijímat parametry (zde: "jmeno")
    // "return" vrátí hodnotu volajícímu kódu
    return "Ahoj, " + jmeno + "!";
    // Po returnu se funkce ukončí
}

// Moderní šipková funkce (Arrow Function)
// Arrow funkce se ukládají do proměnné.
// Narozdíl od tradiční funkce NEJSOU "hoistované" — musí být definované před použitím.
const pozdravArrow = (jmeno) => {
    // Šipkový zápis je kratší a čitelnější, používá se velmi často.
    // Pomocí Template Literals (`...`) lze vkládat proměnné přímo do textu.
    return `Ahoj, ${jmeno}!`;
};

// Volání funkcí
// Funkci zavoláš tak, že za její název napíšeš závorky a parametry.
// Výsledek uložení do proměnné:
let zprava = pozdrav("Martine"); 
// zprava teď obsahuje: "Ahoj, Martine!"

let zprava2 = pozdravArrow("Martine");
// zprava2 obsahuje: "Ahoj, Martine!"
```
##### Funkce jako datový typ
- V JavaScriptu je funkce považovaná za **value** (hodnotu), úplně stejně jako string, číslo nebo objekt.
- To znamená, že s funkcemi můžeš:
	- předávat je do jiné funkce,
	- ukládat je do proměnných,
	- vracet je z funkcí,
	- ukládat je do polí nebo objektů.
- Tohle je něco, co v mnoha jiných jazycích nejde — JavaScript je v tomhle flexibilní.
- Díky tomu fungují:
	- event listenery,
	- callbacky,
	- promise `.then()`,
	- React komponenty,
	- middleware,
	- Express routy,
	- atd.
###### Funkce jako hodnota:
```javascript
let pozdrav = function() {
    console.log("Ahoj!");
};

pozdrav(); // funguje normálně
```
###### Funkce v poli:
```javascript
let akce = [
    () => console.log("První"),
    () => console.log("Druhá")
];

akce[1](); // Druhá
```
###### Funkce vracející funkci:
```javascript
function vytvorPozdrav(jmeno) {
    return () => console.log("Ahoj " + jmeno);
}

let pozdrav = vytvorPozdrav("Petr");
pozdrav(); // Ahoj Petr
```
#### Cykly a Podmínky

##### Operátory pro podmínky
###### **Porovnávací operátory**
- Používají se pro porovnávání dvou hodnot — výsledek je vždy `true` nebo `false`.

| Operátor | Význam                                | Příklad     | Výsledek |
| -------- | ------------------------------------- | ----------- | -------- |
| `==`     | Porovnává hodnotu (bez ohledu na typ) | `5 == "5"`  | `true`   |
| `===`    | Porovnává hodnotu i typ               | `5 === "5"` | `false`  |
| `!=`     | Nerovnost hodnot                      | `3 != 5`    | `true`   |
| `!==`    | Nerovnost hodnoty nebo typu           | `3 !== "3"` | `true`   |
| `>`      | Větší než                             | `7 > 3`     | `true`   |
| `<`      | Menší než                             | `3 < 5`     | `true`   |
| `>=`     | Větší nebo rovno                      | `6 >= 6`    | `true`   |
| `<=`     | Menší nebo rovno                      | `2 <= 5`    | `true`   |
###### **Logické operátory**
- Používají se v podmínkách pro kombinování více logických výrazů.

| Operátor | Význam                                          | Příklad             | Výsledek |
| -------- | ----------------------------------------------- | ------------------- | -------- |
| `&&`     | Logické **A** — obě podmínky musí být pravda    | `true && false`     | `false`  |
| \| \|    | Logické **NEBO** — stačí, aby jedna byla pravda | `true` \|\| `false` | `true`   |
| `!`      | Logické **NOT** — obrací hodnotu                | `!true`             | `false`  |
##### Podmínky (`if`, `else`, `else if`, `switch`)
- Podmínky umožňují řídit tok programu. Kód se spustí pouze tehdy, pokud je splněna definovaná podmínka.  
- Program tak může reagovat na různé situace — například na hodnotu proměnné, vstup uživatele nebo výsledek výpočtu.
###### `if` – základní konstrukce
- Když je podmínka splněna, provede se blok kódu:
```javascript
let teplota = 35;

if (teplota > 30) { // Pokud je teplota větší jak 30 (35>30 -> true)
    console.log("Je horko."); // Vypiš je horko
}
```
###### `if / else`
- Použije se, pokud chceme alternativu, když se podmínka nesplní:
```javascript
let skore = 85;

if (skore > 90) { // Podmínka není splněna (85 > 90 → false)
    console.log("Výborně!");
} else { // Provádí se tedy tato větev
    console.log("Je třeba se víc snažit.");
}
```
- Podmínka splní pouze jednu větev!
###### `else if`
- Slouží pro více možností:
```javascript
let skore = 75;

if (skore >= 90) { // false
    console.log("Výborně.");
} else if (skore >= 70) { // true -> provede se tato větev
    console.log("Chvalitebné.");
} else if (skore >= 50) { // true -> už se neprovede, jelikož se už jenda true podmínka našla před touto 
	console.log("Dobré.");
} else {
    console.log("Nedostatečné."); // také se neprovádí
}
```
- Můžete si povšimnout, že výše jsou splněné 2 podmínky, avšak pouze jedna se vykoná.
- To se děje kvůli tomu, že podmínky se procházejí postupně od zhora dolů, a provede se pouze první, která se najde jako `true`, popřípadě podmínka `else` pokud se `true` nenajde.
###### `switch`
- Používá se, když porovnáváš **jednu hodnotu** vůči **více možnostem**.  
- Je přehlednější než několik `else if` za sebou:
```javascript
	let den = 2;

switch (den) { // Porovnává se den === case
    case 1:
        console.log("Pondělí");
        break; // Zabrání pokračování do další větve
    case 2: // den === 2 -> true
        console.log("Úterý"); // tato větev se provede
        break;// Zabrání pokračování do další větve
    case 3:
        console.log("Středa");
        break;
    default: // Defaultní větev, pokud se den neshoduje s žádnou case
        console.log("Neplatný den");
}
```
- `switch` na rozdíl od  `if` nekontroluje jednotlivé větve. `switch` totiž zjistí hodnotu zadaného parametru a okamžitě ví jakou větev má spustit. Toto je výhodné pro to když máme několik možností, jelikož `switch` nám rovnou najde větev, ale `if` musí ověřit každou podmínku dokud nenajde správnou větev. (při nejhorším případě `if` zkontroluje všechny podmínky což je neefektivní) 
- `switch` porovnává pouze pomocí `===`, ničím jiným neporovnává. Také porovnává pouze hodnoty nikoliv podmínky. 
- To že porovnává pomocí `===` může vést k občasnému zmatku v debugování, pokud si toto nezapamatujete.
```javascript
let x = 5;

switch (x) {
    case "5":   // string ≠ number → neprojde
        console.log("Tohle se nevypíše");
        break;
    case 5:     // number === number → OK
        console.log("Správně!");
        break;
}
```
- Povolené hodnoty k porovnání
```javascript
switch (x) {
    case 1:
    case "text":
    case true:
    case null:
}
```
- Nepovolené hodnoty k porovnání
```javascript
switch (x) {
    case x > 10: // ❌ NESPRÁVNĚ – není to hodnota
    case (a + b): // ❌ výraz, ne hodnota
    case (funkce()): // ❌ výsledek funkce – není statická hodnota
}
```
- Můžete se ale setkat s tím, že se v case objeví porovnání. Koukněte na příklad níže.
```javascript
switch (true) {
    case x > 10:
        console.log("větší než 10");
        break;

    case x > 5:
        console.log("větší než 5");
        break;
}
```
- To FUNGUJE, ale jen kvůli tomu:
	- `switch` porovnává hodnotu `true`
	- s výsledkem výrazu `x > 10` (což je také `true` / `false`)
>[!Warning] Není to oficiální účel, je to hack.
> - `switch` je určen pro porovnávání **jedné hodnoty vůči konkrétním hodnotám** (`===`).
> - Použití výrazu je jen trik. -> může vést k neočekávanému chování
> - Pro porovnávání by se měl použít `if`.
###### Rozdíl mezi `if` a `switch`

| `if`                                        | `switch`                                                                                         |
| ------------------------------------------- | ------------------------------------------------------------------------------------------------ |
| Porovnává komplexní výrazy (např. >, <, &&, | Porovnává pouze určité hodnoty pomocí `===`                                                      |
| Univerzální a flexibilní.                   | Čitelnější při mnoha možnostech.                                                                 |
| Vhodné pro logiku obsahující více podmínek. | Vhodné pro jednoduché porovnání jedné hodnoty. Mnohem rychlejší pro mnoho jednoduchých podmínek. |

---
##### Cykly (`for`, `while`, `do...while`, `forEach`…)
- Cykly opakují kód, dokud je splněna podmínka, nebo dokud neprojdou všechny položky v poli.  
- Nejčastěji se používají při práci s daty — seznamy produktů, výsledky API, řádky tabulky…
---
###### `for` — klasický cyklus
- Hodí se, když potřebujete kontrolovat index a mít plnou kontrolu nad průběhem:
```javascript
for (let i = 0; i < 5; i++) {  // i začíná na 0, běží dokud i < 5, po každém kole se zvětší o 1
    console.log("Číslo:", i); // Vypíše 0,1,2,3,4
}
```
- Parametry `for` cyklu
	1. parametr nám definuje proměnnou, kterou použijeme jako index
	2. parametr nám udá podmínku, do kdy se má cyklus provádět. Porovnává se index s tím co zrovna potřebujeme
	3. parametr nám určuje, co se s indexem po skončení cyklu stane. Nejčastěji se dává zvětšení o 1 nahoru, ovšem můžeme si to určit, jak se nám to zrovna hodí.
###### `while` — opakuje se, dokud je podmínka pravda
- Funguje jako „opakuj, dokud platí…“:
```javascript
let x = 0; // definování hodnoty pro cyklus

while (x < 3) {      // Běží, dokud je podmínka true
    console.log(x);  // Vypíše 0,1,2
    x++;             // Bez zvýšení by vznikl nekonečný cyklus
}
```
###### `do...while` — provede se **minimálně jednou**
- Rozdíl oproti `while` -> nejdřív se provede kód, teprve potom se kontroluje podmínka.
```javascript
let y = 0; // definování hodnoty pro cyklus

do {
    console.log(y); // Tento kód se provede vždy alespoň jednou
    y++; // Zvýšení indexu o 1
} while (y < 3);     // Po provedení znovu kontroluje podmínku
```
###### `for...of` — moderní iterace přes pole
- Ideální na čitelné procházení seznamů:
```javascript
const ovoce = ["Jablko", "Banán", "Pomeranč"];

for (const item of ovoce) { // item = každá položka pole
    console.log(item);
}
```
###### `forEach` — metoda pole
- Velmi oblíbený způsob v moderním JavaScriptu.
```javascript
const ovoce = ["Jablko", "Banán", "Pomeranč"];

ovoce.forEach((item) => {  // Pro každou položku zavolá funkci
    console.log(item);
});
```
###### `for...in` — iterace přes klíče objektu
- Nehodí se na pole, používá se pro objekty:
```javascript
const osoba = { jmeno: "Jan", vek: 25 };

for (const klic in osoba) {            // klic = název vlastnosti objektu
    console.log(klic, osoba[klic]);    // vypíše: jmeno Jan / vek 25
}
```

---
##### Zacyklení (infinite loop)
- Cyklus se může nikdy nezastavit, pokud je podmínka **stále pravdivá**:
```javascript
while (true) { // Opakuje se do nekonečna, jelikož podmínka je pořád true
	console.log("Tohle nikdy neskončí!"); 
}
```
- To může vést k:
	- zamrznutí skriptu,
	- vytížení CPU,
	- spadnutí aplikace.
- Proto je důležité vždy aktualizovat proměnné, které podmínku ovlivňují.
>[!Note] 
> - Například ale v Arduinu, či jiných mikrokontrolérech, můžeme zacyklení využít k našemu prospěchu. Například pokud potřebujeme něco monitorovat a následně to zapsat do logů, můžeme k tomu využít nekonečný cyklus.  
> - Jak to bude probíhat:
> 	- Zapneme arduino -> začne s monitoringem
> 	- Zapnuté arduino -> neustále monituruje a loguje
> 	- Vypneme arduino -> zastavíme monitoring
- Toto ale ovšem neplatí pro webové stránky, v javascriptu, v prohlížeči nekonečný cyklus `while(true)` zamrzne stránku. 
---
##### Kdy použít který cyklus?

| Typ cyklu    | Kdy ho použít                                                      |
| ------------ | ------------------------------------------------------------------ |
| `for`        | Když potřebuješ index nebo chceš počítat krok.                     |
| `while`      | Když nevíš, kolikrát se cyklus provede (např. čekání na podmínku). |
| `do...while` | Když se kód má provést aspoň jednou.                               |
| `for...of`   | Nejčtenější varianta pro pole a iterovatelné objekty.              |
| `forEach`    | Moderní práce s poli, hlavně v JS aplikacích.                      |
| `for...in`   | Pro procházení klíčů objektů.                                      |

---
### DOM – manipulace s prvky
- **DOM (Document Object Model)** je klíčový koncept. Když prohlížeč načte vaše HTML, převede ho na stromovou strukturu objektů – DOM. JavaScript pak může tento strom **číst a upravovat**.
#### 1. Výběr prvků
- Než můžeme něco změnit, musíme to vybrat. Používáme metody objektu `document`:
	- `document.getElementById('nejake-id')`: Vybere prvek podle jeho `id`. (Nejrychlejší)
	- `document.querySelector('.nejaka-trida')`: Vybere **první** prvek, který odpovídá CSS selektoru. (Nejuniverzálnější)
	- `document.querySelectorAll('.nejaka-trida')`: Vybere **všechny** prvky, které odpovídají selektoru (vrátí seznam).
#### 2. Úprava prvků
- Jakmile máme prvek vybraný (uložený v proměnné), můžeme ho měnit:
	- `.textContent`: Mění **pouze text** uvnitř prvku (bezpečné).
	- `.innerHTML`: Mění **celé HTML** uvnitř prvku (může být nebezpečné kvůli XSS útokům, pokud vkládáte data od uživatele – k tomu se dostaneme v kapitole o bezpečnosti).
	- `.style`: Umožňuje měnit CSS vlastnosti (`element.style.color = "red";`).
	- `.classList`: Umožňuje přidávat nebo odebírat CSS třídy (`element.classList.add('aktivni');`).
#### 3. Tvorba a mazání prvků
- Můžeme také vytvářet úplně nové prvky:
```javascript
// 1. Výběr rodiče
const seznam = document.querySelector('#mujoblibeny-seznam');

// 2. Vytvoření nového prvku
const novaPolozka = document.createElement('li');

// 3. Nastavení jeho obsahu
novaPolozka.textContent = "Nová položka";

// 4. Přidání prvku do DOMu (na konec seznamu)
seznam.appendChild(novaPolozka);

// Mazání prvku
// novaPolozka.remove(); 
```
---
### Události (click, input…)
- JavaScript je **řízený událostmi (event-driven)**. Čeká, až uživatel něco udělá (událost), a pak spustí kód, který je na tuto událost navázán.
- Moderní způsob "poslouchání" událostí je metoda `.addEventListener()`:
```javascript
// 1. Vybereme tlačítko
const tlacitko = document.querySelector('#moje-tlacitko');

// 2. Definujeme funkci, která se má spustit
const priKliknuti = () => {
    alert("Bylo na mě kliknuto!");
};

// 3. Přidáme "posluchače", který spojí událost 'click' s naší funkcí
tlacitko.addEventListener('click', priKliknuti);
```
- **Běžné typy událostí:**
	- `click`: Kliknutí myší.
	- `input`: Změna hodnoty ve formulářovém poli (`<input>`).
	- `submit`: Odeslání formuláře (`<form>`).
	- `mouseover`: Najetí myší na prvek.
- U formulářů je časté zabránit jejich výchozímu chování (které by znovu načetlo stránku) pomocí `event.preventDefault()`:
```javascript
const formular = document.querySelector('#muj-formular');
formular.addEventListener('submit', (event) => {
    event.preventDefault(); // Zabráníme odeslání a znovunačtení
    console.log("Formulář odeslán pomocí JS!");
});
```
---
### Fetch API – volání serveru
- Weby jsou zřídka statické. Často potřebujeme načíst data ze serveru (např. seznam produktů, počasí). K tomu slouží **Fetch API**.
- `fetch()` je **asynchronní** funkce. To znamená, že její spuštění **neblokuje** zbytek kódu. JS na ni nečeká, ale pokračuje dál. Výsledek nám "slíbí" do budoucna. Tomuto slibu se říká **Promise**.
- S "Promises" pracujeme pomocí metody `.then()` (co dělat, až se slib splní) a `.catch()` (co dělat, když nastane chyba).
```javascript
// Adresa API (v tomto případě veřejné API pro testování)
const url = '[https://jsonplaceholder.typicode.com/posts/1](https://jsonplaceholder.typicode.com/posts/1)';

console.log("Začátek volání...");

fetch(url)
    .then(response => {
        // První .then() zpracuje odpověď serveru (HTTP status atd.)
        // Převedeme data z formátu JSON na JS objekt
        return response.json(); 
    })
    .then(data => {
        // Druhý .then() má k dispozici reálná data
        console.log("Data dorazila:", data.title);
    })
    .catch(error => {
        // .catch() zachytí jakoukoliv chybu během volání
        console.error("Chyba při načítání:", error);
    });

console.log("... kód pokračuje, nečeká na data.");
```
---
### Asynchronní JS (async/await)
- Řetězení `.then()` může být nepřehledné. Moderní JS nabízí elegantnější syntaxi pro práci s "Promises": `async/await`.
- Je to tzv. "syntaktický cukr" – kód dělá na pozadí to samé co `.then()`, ale nám umožňuje psát asynchronní kód, jako by byl synchronní (lineární).
- Pravidla:
	1. Funkce, která používá `await`, musí být označena jako `async`.
	2. `await` "pozastaví" provádění _pouze dané funkce_, dokud `Promise` není splněn.
	3. Asynchronní kód bychom měli vždy obalit do bloku `try...catch` pro odchycení chyb.
```javascript
const nactiData = async () => {
    const url = '[https://jsonplaceholder.typicode.com/posts/1](https://jsonplaceholder.typicode.com/posts/1)';
    console.log("Začínám načítat...");
    
    try {
        // await "počká", až fetch skončí
        const response = await fetch(url); 
        
        // await "počká", až se data převedou z JSONu
        const data = await response.json(); 
        
        console.log("Data načtena:", data.title);
    } catch (error) {
        console.error("Chyba při načítání:", error);
    }
    
    console.log("... funkce skončila.");
};

nactiData();
```
- Tento zápis je dnes profesionálním standardem.
---
### Moduly
- Když se aplikace rozroste, nechceme mít veškerý kód v jednom obřím souboru. **ESM (ES Moduly)** je moderní standard JavaScriptu, jak rozdělit kód do více souborů.
- **Princip:**
	1. **Export:** Z jednoho souboru "zpřístupníme" funkce nebo proměnné pomocí klíčového slova `export`.
	2. **Import:** V jiném souboru je "načteme" pomocí klíčového slova `import`.
- **Příklad:**
**`soubor: utils.js`**
```javascript
// Exportujeme pojmenovanou konstantu
export const PI = 3.14159;

// Exportujeme pojmenovanou funkci
export const secti = (a, b) => {
    return a + b;
};
```
**`soubor: main.js`**
```javascript
// Importujeme specifické části z našeho modulu
import { PI, secti } from './utils.js';

console.log("Hodnota PI je:", PI);
console.log("Součet 2+3 je:", secti(2, 3));
```
- Aby to celé fungovalo v prohlížeči, musíme hlavní skript v HTML označit jako modul:
```html
<script type="module" src="main.js"></script>
```
- Moduly nám umožňují psát čistý, organizovaný a znovupoužitelný kód, což je základem pro frameworky jako React.
---

### Mini-projekt: Osobní web s interaktivní To-Do app
- Nyní zkombinujeme vše, co jsme se naučili. Přidáme na váš existující osobní web (`o-mne.html`) novou sekci `<section>`, která bude obsahovat plně funkční "To-Do List" (seznam úkolů).
- **Požadavky:**
	1. **HTML:** Přidejte do `index.html` novou sekci s `<input type="text">` pro nový úkol, `<button>` pro přidání a prázdný seznam `<ul>` pro zobrazení úkolů.
	2. **JS (DOM + Události):** Vytvořte nový soubor `app.js` a připojte ho k HTML (pomocí `<script type="module">`).
	3. **Přidání úkolu:** Napište funkci, která po kliknutí na tlačítko:
	    - Přečte text z `<input>`.
	    - Vytvoří nový prvek `<li>`.
	    - Nastaví `<li>.textContent` na text z inputu.
	    - Přidá `<li>` do `<ul>`.
	    - (Bonus) Vyčistí `<input>`.
	4. **Mazání úkolu (Bonus):** Přidejte na každý nový `<li>` `addEventListener('click')`. Po kliknutí na `<li>` se tento prvek smaže (`element.remove()`).
	5. **Perzistence (Bonus 2):** Pomocí `localStorage.setItem()` a `localStorage.getItem()` zkuste zařídit, aby se úkoly uložily v prohlížeči a nezmizely po znovunačtení stránky.
- příklad:
`soubor: index.html`
```html
<!DOCTYPE html>
<html lang="cs">
<head>
	<meta charset="UTF-8">
	<meta name="viewport" content="width=device-width, initial-scale=1.0">
	<title>Martin Novan - Profil webového vývojáře a tvůrce</title>
	<link rel="stylesheet" href="style.css">
</head>
<body>
	<header class="container">
		<h1>Martin Novan</h1>
		<p>Ahoj! Vítejte na mém webovém profilu.</p>
	</header>
	<main class="container">
		<section>
			<h2>O mně a mých zájmech</h2>
			<img src="./Random_profile.avif" alt="Martin Novan, vývojář pracující u počítače" width="100" height="100">
			<p>Jsem vývojář, který se zaměřuje na robustní a čistá softwarová řešení. Neustále rozšiřuji své dovednosti v oblasti moderních frameworků a operačních systémů.</p>
			<p>Aktuálně se v rámci osobních projektů intenzivně věnuji technologiím jako je **.NET MAUI**, **Avalonia UI** a skriptování pro **3D tiskárny (Klipper)**.</p>
		</section>
		<section>
			<h2>Technický Stack a Dovednosti</h2>
			<ul>
				<li><strong>Jazyky:</strong> C#, Python, SQL, HTML, CSS, JavaScript.</li>
				<li><strong>Frameworky / UI:</strong> .NET, WPF, AvaloniaUI, MAUI.</li>
				<li><strong>Databáze:</strong> MySQL, SQL, Microsoft SQL.</li>
				<li><strong>OS/Nástroje:</strong> Arch Linux, Klipper (Firmware).</li>
			</ul>
		</section>
		<section>
			<h2>Vybrané projekty</h2>
			<div id="projekty-kontejner">
				<article>
					<h3>Simple Virtual PC Management (SVPM)</h3>
					<p>Nástroj pro správu virtuálních PC, zákazníků a jejich vztahů. Systém zahrnuje komplexní <strong>Customer Management</strong>, správu konfigurací, auditování změn a zabezpečení integrity dat pomocí **Hash Verification**.</p>
				</article>
				<article>
					<h3>Endeaxim-3 (Hardware Upgrade Kit)</h3>
					<p>Komplexní upgrade kit pro 3D tiskárnu Creality Ender 3. Projekt zahrnuje **Hardware Upgrades** (Dual Z-axis, Linear Rail), implementaci **Klipper Firmware** na Raspberry Pi a optimalizaci pro vysoké rychlosti. K dispozici jsou také **STEP soubory** pro precizní modely.</p>
				</article>
			</div>
		</section>
		<section id="todo-app">
			<h2>Mini Aplikace: To-Do List</h2>
			<p>Přidejte úkoly, které chcete splnit. Kliknutím na úkol ho označíte jako splněný (a smažete).</p>
			<form id="todo-form">
				<input type="text" id="todo-input" placeholder="Napište nový úkol..." aria-label="Nový úkol">
				<button type="submit" id="todo-add-btn">Přidat</button>
			</form>
			<ul id="todo-list">
			</ul>
		</section>
	</main>
	<footer>
	<nav>
		<p>Najdete mě zde:</p>
		<ul>
			<li><a href="https://github.com/MartinNovan" target="_blank">GitHub Profil (My Repositories)</a></li>
		</ul>
	</nav>
	<p>© 2025 Martin Novan. Všechna práva vyhrazena.</p>
	</footer>
	<script src="app.js" type="module"></script>
</body>
</html>
```
`soubor: app.js`
```javascript
/*
 * Mini-projekt: Interaktivní To-Do List
 * Tento soubor je načten jako modul (type="module"),
 * takže se spustí až po načtení HTML (má vlastnost 'defer').
 */

// 1. Výběr elementu z index.html
// Potřebujeme formulář, pole pro zadávání a seznam (ul)
const todoForm = document.querySelector('#todo-form');
const todoInput = document.querySelector('#todo-input');
const todoList = document.querySelector('#todo-list');

// Klíč pro ukládání dat do localStorage
const STORAGE_KEY = 'moje-ukoly';

// 2. Funkce
/**
 * Načte úkoly z localStorage při startu aplikace.
 * Splňuje Bonus 2 (Perzistence).
 */
function nactiUkoly() {
    // Získáme data z localStorage, nebo použijeme prázdné pole, pokud nic nenajdeme
    const ukoly = JSON.parse(localStorage.getItem(STORAGE_KEY)) || [];
    
    // Pro každý uložený textový úkol vytvoříme HTML element
    ukoly.forEach(textUkolu => {
        vytvorElementUkolu(textUkolu);
    });
}

/**
 * Hlavní funkce pro přidání nového úkolu (z formuláře).
 * @param {Event} event - Událost odeslání formuláře
 */
function pridejUkol(event) {
    event.preventDefault(); // Zabráníme výchozímu chování formuláře (znovunačtení stránky)
    // Získáme text z inputu a ořízneme bílé znaky (mezery)
    const textUkolu = todoInput.value.trim();
    // Pokud je input prázdný, nic neděláme
    if (textUkolu === '') {
        alert("Musíte napsat nějaký úkol.");
        return;
    }
    // 1. Vytvoříme HTML element
    vytvorElementUkolu(textUkolu);
    // 2. Vyčistíme input
    todoInput.value = '';
    // 3. Uložíme nový stav do localStorage (Bonus 2)
    ulozUkoly();
}

/**
 * Vytvoří a připojí <li> element do seznamu <ul>.
 * @param {string} text - Text nového úkolu
 */
function vytvorElementUkolu(text) {
    // Vytvoříme nový prázdný <li>
    const li = document.createElement('li');
    
    // Nastavíme mu textový obsah
    li.textContent = text;
    // Splnění Bonusu 1 (Mazání úkolu)
    // Přidáme posluchač události 'click' přímo na tento nový <li>
    li.addEventListener('click', () => {
        // Po kliknutí se prvek sám smaže z DOMu
        li.remove();
        // A aktualizujeme localStorage (Bonus 2)
        ulozUkoly();
    });
    // Přidáme hotový <li> na konec seznamu <ul>
    todoList.appendChild(li);
}

/**
 * Uloží aktuální stav všech úkolů (textový obsah) do localStorage.
 * Splňuje Bonus 2 (Perzistence).
 */
function ulozUkoly() {
    const ukoly = [];
    // Vybereme všechny <li> prvky v seznamu
    const polozkySeznamu = document.querySelectorAll('#todo-list li');
    
    // Projdeme je a jejich textový obsah uložíme do pole
    polozkySeznamu.forEach(li => {
        ukoly.push(li.textContent);
    });
    
    // Převedeme pole na JSON řetězec a uložíme ho
    localStorage.setItem(STORAGE_KEY, JSON.stringify(ukoly));
}

// 3. Spuštění a posluchač
	// 1. Při načtení stránky se pokusíme načíst úkoly z úložiště
nactiUkoly();
	// 2. Nastavíme posluchač na formulář (pro událost 'submit')
todoForm.addEventListener('submit', pridejUkol);
```
`soubor: style.css`
```css
/* 1. ZÁKLADNÍ NASTAVENÍ (RESET) */ 
/* Zajišťuje, že se padding a border počítají dovnitř šířky elementu (border-box) */
*, *::before, *::after {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
} 
/* Nastavení základního fontu a barvy pozadí / textu */
body {
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    line-height: 1.6;
    color: #333; /* Tmavá barva textu */
    background-color: #f4f4f9; /* Světle šedé pozadí */
} 
/* 2. TYPOGRAFIE A ZÁKLADNÍ VZHLED */ 
h1, h2, h3 {
    margin-bottom: 0.5em;
    line-height: 1.2;
    color: #007bff; /* Modrá jako primární barva */
} 
h1 {
    font-size: 2.5rem; /* Větší velikost pro hlavní nadpis */
    color: #f4f4f9; /* Světle šedá pro kontrast s modrým pozadím */
} 
h2 {
    font-size: 1.8rem;
    padding-top: 1em;
    border-bottom: 2px solid #ddd;
    margin-bottom: 1em;
} 
ul {
    list-style-type: disc;
    margin-left: 20px;
} 
/* Stylování obrázku */
img {
    max-width: 100%; /* Zajištění, že obrázek nepřeteče rodičovský kontejner */
    height: auto;
    border-radius: 8px; /* Jemné zaoblení rohů */
    margin: 15px 0;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
} 
/* 3. ROZVRŽENÍ A FLEXBOX (LAYOUT) */ 
.container {
    /* Centrujeme obsah na stránce a dáváme mu maximální šířku */
    max-width: 1200px;
    margin: 0 auto;
    padding: 20px;
} 
header, footer {
    background-color: #007bff;
    color: white;
    padding: 1.5em 20px;
    text-align: center;
} 
/* Vytvoření kontejneru pro navigaci/patičku pomocí Flexboxu */
footer nav {
    display: flex;
    justify-content: center; /* Centrování obsahu (text a seznam) */
    align-items: center;
    flex-wrap: wrap; /* Umožní zalomení na malých obrazovkách */
    gap: 20px;
} 
footer nav ul {
    list-style: none; /* Odstranění odrážek */
    margin: 0;
    display: flex; /* Vodorovné zarovnání odkazů */
    gap: 20px;
} 
/* Vytvoření Flex/Grid kontejneru pro sekci Vybrané projekty */
#projekty-kontejner {
    display: flex; /* Flexbox je ideální pro karty */
    flex-direction: column; /* MOBILE-FIRST: ve výchozím stavu řadíme vertikálně (sloupec) */
    gap: 25px;
    margin-top: 20px;
} 
article {
    background-color: white;
    padding: 20px;
    border-left: 5px solid #007bff; /* Vizuální akcent */
    border-radius: 4px;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.05);
} 
/* 4. RESPONZIVITA (@MEDIA QUERIES) */ 
/* Aplikuje se, když je šířka okna (viewport) alespoň 768px (Tablet a Desktop) */
@media screen and (min-width: 768px) {
    
    /* Změna layoutu projektů z vertikálního na horizontální pomocí Flexboxu */
    #projekty-kontejner {
        flex-direction: row; /* Změna na horizontální uspořádání */
    } 
    /* Každý projekt zabere polovinu dostupného místa */
    #projekty-kontejner article {
        flex: 1 1 45%; /* Flex: grow shrink basis (umožní růst/smrsknutí a základní velikost) */
    } 
    /* Větší padding na velkých obrazovkách */
    main section {
        padding: 40px 0;
    }
} 
/* 5. INTERAKTIVNÍ PRVKY (TRANSITIONS) */ 
/* Stylování odkazů */
a {
    color: white; /* Barva odkazu ve footeru */
    text-decoration: none;
    padding-bottom: 2px;
    border-bottom: 2px solid transparent; /* Průhledná čára pro hladký přechod */
    
    /* Nastavení přechodu pro barvu textu a podtržení */
    transition: color 0.3s ease-in-out, border-color 0.3s ease-in-out; 
} 
/* Efekt při najetí myší (hover) */
a:hover {
    color: #e2e6ea; /* Mírně světlejší barva */
    border-bottom: 2px solid #e2e6ea; /* Zviditelnění podtržení */
}
/* 6. TO-DO app */
#todo-app {
    background-color: #fff;
    padding: 25px;
    border-radius: 8px;
    box-shadow: 0 4px 12px rgba(0, 0, 0, 0.08);
    margin-top: 40px;
}
#todo-form {
    display: flex; /* Použijeme Flexbox pro zarovnání inputu a tlačítka */
    gap: 10px; /* Mezera mezi nimi */
    margin-bottom: 20px;
}
#todo-input {
    flex: 1; /* Input zabere veškeré volné místo */
    padding: 12px;
    border: 2px solid #ddd;
    border-radius: 4px;
    font-size: 1rem;
}
#todo-add-btn {
    background-color: #007bff; /* Stejná modrá jako v designu */
    color: white;
    border: none;
    padding: 0 20px;
    font-size: 1rem;
    font-weight: bold;
    border-radius: 4px;
    cursor: pointer;
    transition: background-color 0.3s ease;
}
#todo-add-btn:hover {
    background-color: #0056b3; /* Tmavší modrá při najetí */
}
#todo-list {
    list-style: none; /* Odstranění odrážek */
    margin: 0;
    padding: 0;
}
#todo-list li {
    background-color: #f9f9f9;
    padding: 15px;
    border: 1px solid #eee;
    border-radius: 4px;
    margin-bottom: 10px;
    
    /* Bonus 1: Indikace, že je prvek klikatelný */
    cursor: pointer; 
    
    /* Plynulý přechod pro efekt */
    transition: all 0.3s ease;
}
/* Bonus 1 (rozšíření): Efekt při najetí na úkol */
#todo-list li:hover {
    background-color: #f1f1f1;
    text-decoration: line-through; /* Přeškrtnutí jako náznak smazání */
    color: #888;
}
```
- ukázka animace:
- ![](Obrazky/Web_app_to_do_app.gif)

---
# Moderní Frontend – frameworky a architektura
## JavaScript ekosystém
- Když jsme v minulé kapitole psali kód, dělali jsme všechno ručně. Problém je, že moderní aplikace neobsahují jen náš kód, ale spoléhají na desítky či stovky "balíčků" (knihoven) od jiných vývojářů.
- **JavaScript ekosystém** je termín pro obrovskou sbírku nástrojů, knihoven, frameworků a postupů, které nám umožňují:
	- Spravovat závislosti (kód jiných lidí).
	- Optimalizovat kód pro produkci.
	- Automatizovat opakující se úkoly (jako je kompilace Sass).
	- Psát kód rychleji a bezpečněji.
- Tyto nástroje tvoří základ, na kterém stavíme frameworky jako React.
---
### NPM a package.json
#### Co je NPM?
- **NPM (Node Package Manager)** je největší světový "obchod" s open-source kódem. Je to obrovská online databáze (registr) balíčků – kousků JavaScript kódu, které za nás řeší nějaký problém.
	- Potřebujete formátovat datum? Není třeba to psát, stačí `npm install date-fns`.
	- Potřebujete dělat složité HTTP požadavky? `npm install axios`.
	- Potřebujete postavit celou aplikaci? `npm install react`.
- NPM je také **nástroj v příkazové řádce**, který se stará o instalaci a správu těchto balíčků.
#### Co je `package.json`?
- Pokud je NPM obchod, `package.json` je váš **nákupní seznam** a zároveň **občanský průkaz** vašeho projektu. Je to jednoduchý JSON soubor, který definuje metadata o projektu.
- **Klíčové části `package.json`:**
	- **`"name"`** a **`"version"`**: Identifikace vašeho projektu.
	- **`"dependencies"`**: Seznam balíčků, které váš projekt potřebuje k **běhu** (např. `react`). Když spustíte `npm install react`, balíček se automaticky přidá sem.
	- **`"devDependencies"`**: Seznam balíčků, které jsou potřeba pouze pro **vývoj** (např. testovací nástroje, bundlery jako Vite).
	- **`"scripts"`**: Zkratky pro spouštění příkazů v terminálu. Místo psaní `vite --run-dev-server --port 3000` napíšete jen `npm run dev`.
- Když si stáhnete projekt z GitHubu, neobsahuje složku `node_modules` (která je obrovská a nikdy se do Gitu nedává!). Stačí v terminálu spustit `npm install`. NPM si přečte `package.json` a automaticky stáhne všechny potřebné `dependencies` a `devDependencies`.
---
### Bundlery – Webpack, Vite
- V kapitole "Moduly" jsme propojili soubory `utils.js` a `main.js` pomocí `<script type="module">`. To funguje pro 2 soubory. Reálná aplikace má ale **stovky souborů**. Kdyby měl prohlížeč načítat každý soubor zvlášť, udělal by stovky HTTP požadavků a stránka by se načítala minuty.
- **Problém:** Chceme psát kód modulárně (ve stovkách souborů), ale prohlížeč ho chce dostat ideálně v **jednom souboru**.
- **Řešení:** **Bundler** (svazkovač).
	- Bundler je nástroj, který projde veškerý váš kód (`.js`, `.css`, `.scss`, obrázky...), analyzuje všechny `import` příkazy a "sváže" je dohromady do jednoho (nebo několika málo) optimalizovaných souborů, kterým už prohlížeč rozumí.
	- Během tohoto procesu také provádí další kouzla:
		- **Minifikace:** Odstraní z kódu všechny mezery a zkrátí názvy proměnných, aby byl soubor co nejmenší.
		- **Transpilace:** Převede moderní JS (nebo TypeScript) na starší verzi, které rozumí i starší prohlížeče.
		- **Zpracování CSS:** Zkompiluje Sass, přidá vendor prefixy atd.
#### Webpack vs. Vite
- **Webpack:** Dlouholetý král. Je nesmírně konfigurovatelný, ale jeho nastavení je notoricky složité. Před spuštěním dev serveru musí "přebudovat" celou aplikaci.
- **Vite:** Nová generace. Je extrémně rychlý, protože v developmentu využívá nativní ESM (které jsme se učili) a "bundluje" jen to, co je nezbytně nutné (např. závislosti). Bundluje až při finálním "buildu" pro produkci. Pro začátečníky je mnohem přívětivější a dnes je standardem pro React i Vue.
---
### ESM vs CJS
- Když jsme se učili moduly, použili jsme syntaxi `import` a `export`. Toto je **ESM (ECMAScript Modules)**, moderní, oficiální standard JavaScriptu pro práci s moduly, kterému rozumí prohlížeče.
```javascript
// ESM syntaxe (moderní, pro prohlížeče a nový Node.js)
import { secti } from './utils.js';
export const PI = 3.14;
```
- Dlouhou dobu ale existoval jiný standard, primárně vytvořený pro **Node.js** (JavaScript na serveru), kterému se říká **CJS (CommonJS)**. Prohlížeče mu vůbec nerozumí.
```javascript
// CJS syntaxe (starší, pro Node.js)
const { secti } = require('./utils.js');
module.exports.PI = 3.14;
```
- **Proč je to důležité?** Protože **NPM** (které vzešlo z Node.js) bylo historicky plné CJS balíčků. Dnešní bundlery (jako Vite) musí být schopné vzít starý CJS kód z `node_modules` a přeložit ho do ESM formátu, kterému rozumí prohlížeč
- Dnes se celý ekosystém přiklání k ESM, ale CJS syntaxi (`require`) ještě uvidíte ve spoustě starších tutoriálů nebo v konfiguračních souborech Node.js.
---
### Co je SPA (Single Page Application)
- Máme všechny nástroje a chápeme, jak fungují. K čemu je použijeme? K tvorbě **Single Page Application** (Aplikace na jedné stránce).
#### Tradiční web (MPA - Multi-Page Application)
- Postup
	1. Zadáte `www.web.cz/o-nas`.
	2. Prohlížeč pošle **HTTP request** serveru.
	3. Server vrátí **kompletní HTML soubor** pro stránku "O nás".
	4. Stránka se **kompletně znova načte** (bílá obrazovka, "bliknutí").
	5. Kliknete na "Kontakt".
	6. Celý proces se opakuje.
#### Moderní web (SPA - Single Page Application)
- Postup
	1. Zadáte `www.app.cz`.
	2. Prohlížeč pošle **HTTP request** serveru.
	3. Server vrátí **jediný HTML soubor** (`index.html`) a **velký JS soubor** (náš "bundle" z Vite).
	4. Stránka se načte. Nyní přebírá kontrolu JavaScript (např. React).
	5. Kliknete na odkaz "O nás".
	6. **Stránka se nenačte znova!**
	7. JavaScript zachytí kliknutí, pomocí **Fetch API** si ze serveru stáhne **pouze potřebná data** (obvykle ve formátu JSON).
	8. JavaScript pomocí **DOM manipulace** (kterou jsme se učili) "vymaže" obsah stránky a vykreslí nový obsah pro "O nás".
	9. URL adresa v prohlížeči se změní (pomocí speciálního API), aby uživatel mohl použít tlačítko Zpět.
- Výsledek je bleskurychlý. Aplikace působí jako program na počítači, ne jako webová stránka. Gmail, Google Mapy, Figma, Facebook – to všechno jsou Single Page Applications.
- Frameworky jako **React** jsou navrženy přesně k tomu, aby nám tvorbu těchto komplexních SPA co nejvíce usnadnily. A my jsme nyní připraveni se na React podívat.
---
## React – profesionální úroveň
- React (často React.js) je **JavaScriptová knihovna** pro tvorbu uživatelských rozhraní (UI). Není to kompletní framework (jako např. Angular), ale specializovaná knihovna, která se soustředí na jednu věc a dělá ji skvěle: **efektivní vykreslování UI komponent**.
- Proč je tak populární?
	- **Deklarativní:** Místo ruční manipulace DOMu (jako v našem to-do listu, např. `document.createElement...`) Reactu pouze _deklarujeme_, jak má UI vypadat v závislosti na datech. React se sám postará o tu nejsložitější část – efektivní aktualizaci DOMu.
	- **Komponentový přístup:** Umožňuje nám rozbít složité UI na malé, izolované a znovupoužitelné kousky – **komponenty**.
	- **Virtual DOM:** React si drží v paměti vlastní "virtuální" kopii DOMu. Když se data změní, React porovná nový virtuální DOM se starým, najde minimální nutný rozdíl a ten pak promítne do skutečného DOMu. To je extrémně rychlé.
---
### Komponenty
- **Komponenta je základní stavební jednotka Reactu.** Je to v podstatě JavaScriptová funkce (v moderním Reactu), která přijímá nějaká data a vrací HTML (respektive JSX).
- Vzpomeňte si na `utils.js`, kde jsme exportovali funkci. Zde exportujeme "kus" uživatelského rozhraní.
```javascript
// soubor: Tlacitko.jsx
// Toto je jednoduchá funkcionální komponenta.
function Tlacitko() {
    return (
        <button className="moje-tlacitko">
            Klikni na mě
        </button>
    );
}
// Exportujeme ji, abychom ji mohli použít jinde
export default Tlacitko;
```

```javascript
// soubor: App.jsx
// Importujeme naši komponentu
import Tlacitko from './Tlacitko.jsx';

// App je také komponenta, která "obaluje" ostatní
function App() {
    return (
        <div>
            <h1>Moje React Aplikace</h1>
            <Tlacitko />
            <Tlacitko /> 
        </div>
    );
}
```
- Všimněte si `className` místo `class`. Jelikož jsme v JavaScriptu, `class` je rezervované klíčové slovo. Syntaxi, která míchá HTML a JS, se říká **JSX (JavaScript XML)**.
---
### Props a State
- Toto je nejdůležitější koncept v Reactu. Komponenty potřebují data, aby byly dynamické. Data mohou získat ze dvou zdrojů: `props` nebo `state`.
#### Props (Vlastnosti)
- **Props** (properties) jsou data, která komponentě přicházejí **zvenčí**, od jejího rodiče. Komponenta je **nemůže sama změnit** (jsou pouze ke čtení, "read-only").
- _Analogie: Jsou to argumenty funkce._
```javascript
// Rodič (App.jsx) posílá 'props'
function App() {
    return (
        <div>
            <Tlacitko text="Odeslat" />
            <Tlacitko text="Zrušit" />
        </div>
    );
}
```

```javascript
// Potomek (Tlacitko.jsx) přijímá 'props'
// 'props' je objekt: { text: "Odeslat" }
function Tlacitko(props) {
    return (
        <button className="moje-tlacitko">
            {props.text} 
        </button>
    );
}
```
- Tomuto se říká **jednosměrný datový tok (one-way data flow)**. Data tečou vždy shora (rodič) -> dolů (potomek).
#### State (Stav)
- **State** (stav) jsou data, která komponenta spravuje **uvnitř sebe**. Je to její interní paměť. Když se `state` změní, React **automaticky a inteligentně překreslí** komponentu.
- _Analogie: Jsou to lokální proměnné uvnitř funkce, které si "pamatují" hodnotu mezi voláními._
- Jak ale přidáme `state` do funkce? Pomocí "háčků" (Hooks).
---
### Hooks (Háčky)
- Hooks jsou speciální funkce (vždy začínají na `use...`), které nám umožňují "zaháknout se" do interních mechanismů Reactu (jako je state nebo životní cyklus) z funkcionálních komponent.
#### `useState`
- Nejdůležitější hook. Přidává komponentě lokální `state`.
```javascript
import { useState } from 'react'; // Musíme ho importovat

function Pocitadlo() {
    // useState vrátí pole: [aktuální hodnota, funkce pro změnu hodnoty]
    // Používáme "destrukturaci" pole pro jejich pojmenování
    const [pocet, setPocet] = useState(0); // 0 je počáteční hodnota
    
    const zvedniPocet = () => {
        // Nikdy neměníme state přímo (NE: pocet = pocet + 1)!
        // Vždy voláme nastavovací funkci.
        setPocet(pocet + 1);
    };
    
    return (
        <div>
            <p>Kliknul jsi {pocet} krát.</p>
            <button onClick={zvedniPocet}>Klikni</button>
        </div>
    );
}
```
- Když zavoláme `setPocet(1)`, React si všimne změny a **znovu spustí funkci `Pocitadlo`**, ale tentokrát bude mít `pocet` hodnotu 1. Tím se UI automaticky aktualizuje.
#### `useEffect`
- Tento hook slouží k provádění **vedlejších efektů (side effects)**. Vedlejší efekt je cokoliv, co se děje mimo samotné vykreslování komponenty:
	- Načítání dat (Fetch)
	- Přímá manipulace s DOM (výjimečně)
	- Nastavení časovačů (`setTimeout`)
- `useEffect` přijímá funkci a pole závislostí.
```javascript
// Spustí se POUZE jednou, když se komponenta poprvé vykreslí
// (Díky prázdnému poli závislostí [])
useEffect(() => {
    console.log("Komponenta se poprvé vykreslila");
    // Ideální místo pro fetch dat
}, []);

// Spustí se po každém vykreslení, pokud se změnila hodnota 'pocet'
useEffect(() => {
    document.title = `Kliknul jsi ${pocet} krát`;
}, [pocet]); 
```

---
### Router
- React sám o sobě neumí spravovat URL adresy (je to jen UI knihovna). Pro vytvoření **SPA** (kterou jsme definovali v minulé kapitole) potřebujeme externí balíček.
- Nejpopulárnější je **React Router** (`npm install react-router-dom`).
- Umožňuje nám definovat, která komponenta se má vykreslit pro jakou URL, aniž by se stránka znovu načítala.
```javascript
import { BrowserRouter, Routes, Route, Link } from 'react-router-dom';

function App() {
    return (
        <BrowserRouter>
            <nav>
                <Link to="/">Domů</Link>
                <Link to="/o-nas">O nás</Link>
            </nav>
            
            <Routes>
                <Route path="/" element={<KomponentaDomu />} />
                <Route path="/o-nas" element={<KomponentaONas />} />
            </Routes>
        </BrowserRouter>
    );
}
```
- `<BrowserRouter>` obaluje celou aplikaci a umožňuje sledovat URL.
- `<Link>` funguje jako `<a>`, ale **bez reloadu stránky** — mění jen URL uvnitř SPA.
- `<Routes>` vybírá, která `<Route>` odpovídá aktuální adrese.
- Každá `<Route>` má:
    - `path` – URL cesta (např. `/`, `/o-nas`)
    - `element` – komponenta, která se má vykreslit
---
### Formuláře a validace
- Ve "vanilla" JS jsme četli hodnotu z DOMu (`todoInput.value`). V Reactu je to jinak. Stav formuláře (co je napsáno v inputu) je uložen v **React `state`**.
- Tomuto se říká **kontrolovaná komponenta (Controlled Component)**.
```javascript
import { useState } from 'react';

function FormularJmena() {
    const [jmeno, setJmeno] = useState('');

    const handleSubmit = (event) => {
        event.preventDefault(); // Zabráníme znovunačtení stránky
        alert(`Odesláno jméno: ${jmeno}`);
        // Zde by proběhla validace...
    };

    return (
        <form onSubmit={handleSubmit}>
            <label>Jméno:</label>
            <input 
                type="text"
                value={jmeno} // Hodnota inputu je VŽDY řízena stavem
                onChange={(e) => setJmeno(e.target.value)} // Každé písmeno aktualizuje stav
            />
            <button type="submit">Odeslat</button>
        </form>
    );
}
```
- **Datový tok:** Uživatel píše -> spouští se `onChange` -> `setJmeno` aktualizuje `state` -> React překreslí komponentu -> `input` dostane novou hodnotu (`value={jmeno}`).
---
### Fetch v Reactu
- Kam umístíme `fetch` kód, který jsme se naučili? Do `useEffect` hooku, aby se data načetla, jakmile se komponenta zobrazí. Načtená data uložíme do `state`.
```javascript
import { useState, useEffect } from 'react';

// Komponenta, která načítá data z API
function NactiData() {
    const [data, setData] = useState(null); // Stav pro uložená data z API
    const [nacitam, setNacitam] = useState(true); // Stav, který říká, zda se právě načítá
    const [chyba, setChyba] = useState(null); // Stav pro případnou chybu při načítání
    // useEffect se spustí po prvním vykreslení komponenty (mount)
    useEffect(() => {
        // Asynchronní funkce pro načtení dat
        const nactiApi = async () => {
            try {
                const url = 'https://jsonplaceholder.typicode.com/posts/1';
                // Zavoláme API pomocí fetch
                const response = await fetch(url);
                // Pokud server vrátí chybu (400, 500...), vyhodíme vlastní chybu
                if (!response.ok) {
                    throw new Error(`HTTP chyba! Status: ${response.status}`);
                }
                // Převedeme odpověď na JSON
                const json = await response.json();
                // Uložíme získaná data do stavu
                setData(json);
            } catch (e) {
                // Pokud nastane chyba (např. síťová), uložíme si její text
                setChyba(e.message);
            } finally {
                // Vždy se provede → říkáme, že načítání skončilo
                setNacitam(false);
            }
        };
        // Spustíme funkci pro načtení dat
        nactiApi();
        // Prázdné pole = efekt proběhne jen při prvním renderu
    }, []);
    // Pokud stále načítáme, zobrazíme hlášku
    if (nacitam) return <p>Načítám data...</p>;
    // Pokud nastala chyba, zobrazíme ji
    if (chyba) return <p>Chyba: {chyba}</p>;
    // Pokud máme data, zobrazíme název příspěvku
    if (data) return <p>Název: {data.title}</p>;
    // Teoretická fallback varianta (většinou se nestane)
    return null;
}
```

---
### Stavová správa (Redux, Zustand)
- `useState` je skvělý pro lokální stav. Co když ale 50 komponent v různých částech aplikace potřebuje znát přihlášeného uživatele? Posílat `props` přes 10 úrovní (`prop drilling`) je neefektivní.
- Potřebujeme **globální stav**.
	- **Context API:** Vestavěný mechanismus Reactu pro sdílení dat. Dobrý pro menší objem dat (např. téma dark/light mode, přihlášený uživatel).
	- **Zustand:** Moderní, minimalistická knihovna pro globální stav. Velmi jednoduchá na použití, využívá hooky.
	- **Redux / Redux Toolkit:** Starší, robustnější standard pro obrovské aplikace. Má složitější "boilerplate" (více kódu na nastavení), ale nabízí striktní pravidla pro správu stavu (Actions, Reducers), což se hodí ve velkých týmech.
---
### Testování (Jest, RTL)
- Jak si můžeme být jisti, že naše komponenty fungují? Otestujeme je.
	- **Jest:** Testovací platforma (nástroj od Facebooku), která poskytuje prostředí pro spouštění testů (funkce `test()`, `expect()`).
	- **React Testing Library (RTL):** Knihovna pro "vykreslení" komponenty v testovacím prostředí a interakci s ní (simulace kliknutí, psaní do inputu).
- Filozofie RTL je: "Testujte aplikaci tak, jak ji používá uživatel." Místo hledání `div`ů podle `id` nebo `className`, hledáte tlačítko podle jeho textu.
```javascript
import { render, screen, fireEvent } from '@testing-library/react';
import Pocitadlo from './Pocitadlo';

test('po kliknutí na tlačítko se zvýší počet', () => {
    // 1. Vykreslíme komponentu
    render(<Pocitadlo />);
    
    // 2. Najdeme elementy podle textu
    const tlacitko = screen.getByText('Klikni');
    const zprava = screen.getByText('Kliknul jsi 0 krát.');
    
    // 3. Simulujeme akci uživatele
    fireEvent.click(tlacitko);
    
    // 4. Ověříme výsledek
    const novaZprava = screen.getByText('Kliknul jsi 1 krát.');
    expect(novaZprava).toBeInTheDocument();
});
```

---
### Mini-projekt: React dashboard
- Nyní vše spojíme.
- **Cíl:** Vytvořit jednoduchou **SPA** (Single Page Application) dashboardu.
- **Požadavky:**
	1. **Nástroje:** Použijte `npm create vite@latest` pro rychlé nastavení projektu.
	2. **Komponenty:** Vytvořte komponenty (`Sidebar.jsx`, `Dashboard.jsx`, `Users.jsx`).
	3. **Router:** Použijte `react-router-dom` k vytvoření dvou stránek: `/` (Dashboard) a `/users` (Uživatelé).
	4. **Fetch & State:** Na stránce `/users` použijte `useEffect` a `useState` k načtení a zobrazení seznamu uživatelů z veřejného API (např. `jsonplaceholder.typicode.com/users`).
	5. **Formuláře:** (Bonus) Na stránce `/users` přidejte `<input>`, který bude pomocí `useState` filtrovat zobrazené uživatele podle jména.
---
## CSS ve velkých projektech
- Organizace stylů, aby byly přehledné a snadno udržovatelné.
### BEM
- Metodika pro systematické psaní CSS tříd.
### CSS Modules
- Izolace stylů na úrovni komponent.
### TailwindCSS
- Utility-first CSS framework.
### Styled Components
- Stylování přímo v JavaScriptu.
---
# Backend – serverová logika a databáze
## Backend základy
- Úvod do toho, co se děje na serveru a jak se pracuje s daty.
### Co je serverový jazyk
- Rozdíl mezi JavaScript v prohlížeči a na serveru.
### REST API – principy
- Struktura API a typické endpointy.
### JSON
- Formát pro přenos dat mezi frontendem a backendem.
---
## Node.js a Express
- Praktický výklad vývoje backendu v JS pomocí Expressu.
### První server
- Ukázka jednoduchého serveru.
### Routing
- Jak tvořit různé cesty v API.
### Middleware
- Funkce pro práci s požadavky.
### Ověřování JWT
- Základy autentizace a bezpečného přihlášení.
### Soubory a upload
- Jak zpracovat soubory posílané uživatelem.
### Mini-projekt: API pro e-shop
- Server poskytující data o produktech.
---
## PHP – základní serverový jazyk
### role PHP v historii a současnosti
### první PHP skript
### práce s proměnnými, podmínkami, cykly

### práce se soubory, odesílání formulářů
### PHP + MySQL
###  bezpečnost (SQL Injection, XSS)
###  mini-projekt: jednoduchý kontakt formulář s uložením do DB
---
## Databáze (SQL i NoSQL)
- Základní práce s relačními i nerelačními databázemi.
### SQL – principy
- Jak fungují tabulky, relace a dotazy.
### SQLite a PostgreSQL
- Dva bežné SQL systémy.
### NoSQL – MongoDB
- Databáze založená na dokumentech.
### Vztahy a indexy
- Optimalizace výkonu databází.
### ORM (Prisma/Mongoose)
- Ulehčení práce s databázemi.
---
## Fullstack integrace
- Propojení frontendu s backendem do jednoho celku.
### Frontend ↔ Backend komunikace
- Jak posílat a přijímat data v aplikaci.
### Error handling
- Správné zpracování chyb v aplikaci.
### Deployment fullstack app
- Nasazení klienta i serveru do produkce.
### Mini-projekt: Fullstack aplikace
- Např. blog, e-shop, dashboard.
---
# WordPress – nejrozšířenější redakční systém

- co je WordPress a kdy se vyplatí ho použít
    
- instalace (lokální i hosting)
    
- šablony (themes) – úprava vzhledu
    
- pluginy – rozšíření funkcí bez programování
    
- tvorba vlastního pluginu (úvodní příklad)
    
- tvorba vlastního jednoduchého motivu (theme)
    
- bezpečnost WordPressu
    
- performance – optimalizace, caching
    
- mini-projekt: vytvoření funkčního webu (blog/portfolio/Web s přihlášením)
---
# Pokročilé webové technologie
## API architektury
- Pokročilé způsoby komunikace mezi službami.
### GraphQL
- Alternativa k RESTu s flexibilními dotazy.
### gRPC
- Rychlá komunikace založená na binárním přenosu.
### WebSockets
- Reálný čas, chaty, online aplikace.
---
## Pokročilá bezpečnost
- Komplexní pohled na ochranu aplikací.
### XSS
- Útok vložením škodlivého kódu.
### CSRF
- Útok využívající cizí relaci uživatele.
### SQL Injection
- Nechráněné dotazy do databáze.
### Bezpečné ukládání hesel
- Hashování, salting, best practices.
### CORS
- Mechanismus řízení přístupu u API.
---
## Výkon frontendu a backendu
- Jak zrychlit aplikaci na všech úrovních.
### Lazy load a code splitting
- Oddálení načítání těžkých částí webu.
### CDN
- Distribuční síť pro rychlejší načítání.
### Caching strategií
- Jak ukládat data pro zrychlení.
### Lighthouse
- Nástroj pro měření kvality webu.
---
## PWA – Progressive Web Apps
- Jak vytvořit aplikaci, která funguje jako mobilní app.
### Service Workers
- Script běžící na pozadí pro práci offline.
### Offline režim
- Cacheování a ukládání dat.
### Instalační manifest
- Jak umožnit instalaci webu jako aplikace.
---
## Mobilní a desktopové webové technologie
- Jak ze znalostí webu tvořit nativní aplikace.
### React Native
- Tvorba mobilních aplikací pomocí JS.
### Electron
- Tvorba desktopových aplikací pomocí webu.
### WebView model
- Hybridní aplikace kombinující nativní funkcionalitu s webem.
---
# DevOps – profesionální praxe
## Docker
- Kontejnery pro oddělené a opakovatelné spuštění aplikací.
### Dockerfile
- Definice prostředí aplikace.
### Docker Compose
- Koordinace více kontejnerů.
### Container networking
- Jak kontejnery spolu komunikují.
---
## CI/CD
- Automatizace buildů, testů a nasazení.
### GitHub Actions
- Automatické workflow nad GitHub repozitářem.
### Pipeline build + test + deploy
- Jaké kroky má mít profesionální pipeline.
### Automatické nasazení
- Uvolnění nové verze bez ruční práce.
---
## Cloud a serverless
- Nasazení aplikací bez správy serveru.
### AWS / Azure – základy
- Cloudové služby dostupné pro web.
### Serverless funkce
- Výpočet bez nutnosti běžícího serveru.
### CDN, edge computing
- Zrychlení aplikací přiblížením obsahu k uživateli.
---
# Profesionální vývojář – jak pracuje tým
## Code review a dokumentace
- Jak psát udržovatelný a srozumitelný kód.
### Jak psát dobré commity
- Best practices ve verzovacím systému.
### PR best practices
- Jak správně vytvořit pull request.
### UML a systémová dokumentace
- Grafické znázornění architektury systému.
---
## Návrhové vzory pro web
- Osvědčené postupy řešení problémů.
### MVC, MVVM, MVU
- Architektonické přístupy ve webovém vývoji.
### Pub/Sub
- Komunikace mezi částmi systému pomocí událostí.
### Singleton
- Vzor pro sdílení jediné instance objektu.
### Service layer
- Oddělení logiky aplikace od infrastruktury.
---
# Závěrečný projekt
## Kompletní real-world aplikace
- Vytvoření kompletní webové aplikace používající všechny znalosti z učebnice.
- návrh databáze
- backend API
    
- frontend aplikace
    
- testování
    
- CI/CD
    
- Docker nasazení
---
# Závěr
- Shrnutí celého materiálu a doporučení pro další rozvoj.