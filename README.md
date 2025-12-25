# NTIkstad — av Siam Karlsson

## Snabbstart

- Installera en lokal PHP-server (t.ex. XAMPP, WAMP eller MAMP).
- Kopiera projektmappen till din webroot (t.ex. `htdocs` eller `www`).
- Öppna `index.php` i webbläsaren.

## Funktioner

- Användarautentisering: inloggning och registrering via `login.php` och `register.php`.
- Administrationsgränssnitt: `admin.php` för hantering av användare och innehåll.
- Filuppladdning och organisering: `uploads/` lagrar användarfiler.
- Klubb- och forumfunktioner: hantera klubbar och klubbmedlemmar via `clubs.php` och `club-member.php`.
- Annonser och inlägg: skapa och visa annonser (`announcements/`, `announcement-detail.php`).
- Supportärenden och biljetter: skapa och se tickets (`support.php`, `ticket-detail.php`, `admin-ticket-detail.php`).
- Profilhantering: användare kan uppdatera sin profil via `profile.php`.
- Enkel API: `api.php` erbjuder endpoints för integration (se avsnittet "API").

## Detaljerade funktioner

- Inloggning/utloggning: sessionsbaserad inloggning, lösenordsåterställning via `reset-password.php`.
- Filuppladdning: stöd för kategorier och uppladdningsmappar under `uploads/`.
- Rollbaserad åtkomst: admin-sidor skyddas och kräver administratörsbehörighet.
- Meddelanden/annonser: CRUD för annonser (skapa, läsa, uppdatera, ta bort).
- Supportflöde: skapa ärenden från frontend; administratörer svarar via admin-gränssnittet.

## Filstruktur (översikt)

- `admin/` — admin-panel och tillhörande assets
- `includes/` — `header.php`, `footer.php`, `i18n.php` mm.
- `uploads/` — användarfiler, vidare uppdelat i underkataloger (announcements, club_posts, osv.)
- Huvudsidor: `index.php`, `login.php`, `register.php`, `profile.php`, `support.php` m.fl.

## Teman och språk

- Teman: Projektet inkluderar flera färdiga teman som ligger under `admin/assets/themes/`:
	- compact.css
	- cyberpunk.css
	- dark.css
	- forest.css
	- midnight.css
	- modern.css
	- ocean.css
	- responsive.css
	- sunset.css
	- tablet.css

- Språkstöd: Projektet har flerspråkigt stöd via `includes/i18n.php` och översättningsfiler. Tillgängliga språk:
	- Svenska
	- Engelska
	- Ryska

Användare kan välja tema och språk via gränssnittet (om stöd finns i front-end). Tema- och språkfilerna kan utökas genom att lägga till nya CSS-filer eller språkfiler i `includes/`.

## Installation och konfiguration

1. Kopiera projektmappen till din webroot.
2. Skapa en databas och importera eventuellt medföljande SQL (om tillämpligt).
3. Konfigurera `config.php` med databasuppgifter och bas-URL.
4. Sätt korrekta filbehörigheter för `uploads/` och `storage/user_files/`.

OBS: Glöm inte att uppdatera `config.php` med korrekta databasinställningar (host, databas, användare, lösenord) innan du kör applikationen. Projektet kräver en MySQL- eller MariaDB-server — se till att en sådan är installerad och körs.

## Administratörskonto (test)

OBS: Följande konto är endast för utvecklingstester:

- E-post: admin@admin.se
- Lösenord: 12345678

VARNING: Detta lösenord är mycket svagt. Byt det omedelbart i en produktionsmiljö och undvik att använda riktiga uppgifter i repo.

## API (kort)

- `api.php` hanterar enkla anrop för integration. Kontrollera filen för tillgängliga endpoints.
- Exempel: anrop mot `api.php?action=getAnnouncements` kan returnera JSON-lista över annonser.

## Användningsexempel

- Logga in via `login.php`.
- Ladda upp filer via profilsidan eller formulär som stöder uppladdning.
- Skapa en annons via lämpligt formulär och ladda upp bilder till `uploads/announcements/`.

## Säkerhet och drift

- Byt standardlösenord och skapa starka lösenord (minst 12 tecken med variation).
- Aktivera HTTPS i din serverkonfiguration.
- Skydda `includes/`-filer och konfigurationer från publik åtkomst.
- Håll PHP och beroenden uppdaterade.

## Felsökningstips

- Kontrollera PHP-loggar vid fel (t.ex. i XAMPP-katalogen eller serverns loggar).
- Verifiera filbehörigheter för `uploads/` och `storage/`.

## Bidra

- Skicka en PR eller skapa issue om du vill förbättra funktioner eller dokumentation.

## Licens

- Licens: MIT — se `LICENSE` för fullständig text.

---

Behöver du att jag lägger till exempel på API-endpoints eller en SQL-schema-import? Säg till så lägger jag till det.
## Licens och äganderätt

- Licens: Detta projekt släpps under MIT-licensen. Se `LICENSE` för fullständig text.

- Äganderätt: Projektet ägs av projektets upphovsman ("Projektägaren"). Skolan eller andra organisationer äger inte projektkoden.

- Rätt att se filer: Skolan kan ha rätt att granska eller läsa filer som lagras i systemet (t.ex. för administrativ eller säkerhetsrelaterad granskning), men detta utgör inte äganderätt till projektet.

- Footer-regler: Footern i applikationens vyer får tas bort endast av legitimerade lärare inom teknikämnena som har uttrycklig, skriftlig tillåtelse från Projektägaren. Om du inte är en legitimerad lärare med sådan tillåtelse har du inte rätt att ändra eller ta bort footern.
 - Otillåten ändring eller användning: Vid otillåten ändring, borttagning av footer eller annan otillåten användning av systemet förbehåller Projektägaren sig rätten att vidta lämpliga åtgärder, inklusive anmälan till ansvariga parter eller andra rättsliga åtgärder där tillämpligt.

 - Skriftligt tillstånd krävs: Muntligt eller informellt tillstånd räknas inte. Endast uttryckligt, skriftligt godkännande från Projektägaren ger rätt att ta bort watermark/footern.

 - Kontakt för tillstånd: Lärare som är legitimerade inom teknikämnen och som vill använda hemsidan som undervisningsexempel och begära borttagning av watermark måste kontakta Projektägaren via e-post: siam.karlsson@gmail.com. Ange din skola, yrkestitel och syftet med ändringen i förfrågan.

OBS: Detta avsnitt är ett uttalande av avsikt och ska inte tolkas som juridisk rådgivning. Kontakta juridisk expertis om du behöver bindande avtal eller formell rättslig text.
