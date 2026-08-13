# Opdracht: complete redesign jeau.st

Je bouwt de nieuwe website voor Jeau.st, de eenmanszaak van Joost Beers. Vervangt een bestaande WordPress-site. Volledige vrijheid op vormgeving en copy, binnen de kaders hieronder.

## Wie het is

Joost Beers, ZZP'er uit Den Bosch, KvK 88930343. Doet CRM-implementatie en procesautomatisering voor start-ups en scale-ups. Werkt met Pipedrive, n8n, Jira en Power BI. Zijn klanten zijn oprichters en operationeel managers van bedrijven van pakweg 10 tot 100 man die vastlopen in losse systemen, Excel-lijsten en handwerk.

Wat hem onderscheidt: hij is geen implementatiepartner die een tool over de schutting gooit. Hij doet de techniek, het proces en de coaching van het team dat er daarna mee moet werken. Nuchter, praktisch, geen consultancytaal.

Contact loopt via joost@jeau.st. Geen telefoonnummer op de site.

## Doel van de pagina

Eén pagina. Eén taak: een bezoeker die twijfelt of dit zijn probleem oplost, laten mailen voor een gesprek. Geen formulier, geen nieuwsbrief, geen blog.

## Technische kaders

- Statische site, gehost op GitHub Pages. Geen backend, geen server-side code.
- Tailwind CSS v4, gebouwd met de CLI (`npx @tailwindcss/cli -i src/input.css -o css/style.css --minify`). `src/input.css` bevat `@import "tailwindcss";` plus eventuele `@theme` tokens. Gebruik geen Play CDN.
- Eén `index.html`. Vanilla JS alleen waar het echt iets toevoegt, geen framework, geen build-tooling behalve Tailwind.
- Nederlands. Bestaande assets staan in `img/`: `logo_wit.png`, favicon, en de logo's van Pipedrive, n8n, Jira en Power BI.
- Webfonts via Google Fonts of gezelfhoste `woff2` in `img/` of `fonts/`. Beperk je tot twee families.
- Doelbrowsers: modern. Tailwind v4 vereist Safari 16.4+, Chrome 111+.

## Wat de pagina moet overbrengen

Vertaal dit naar eigen copy, neem niets letterlijk over. De huidige teksten zijn te vaag en leunen op emoji als decoratie; dat mag helemaal weg.

**Positionering.** Systemen die samenwerken, processen die kloppen, een team dat ermee overweg kan. Het resultaat is overzicht en rust, niet "digitale transformatie".

**Diensten.** Migratie van data uit oude systemen en Excel naar één omgeving. Procesanalyse en herontwerp. Dashboards en rapportage. Automatisering van repetitief handwerk. Koppelingen tussen systemen. Training en coaching van het team.

Deze zes vormen geen volgorde en geen menu waar je één ding uit kiest. Kijk of ze wel zes losse blokken moeten zijn, of dat een andere structuur waarheidsgetrouwer is.

**Werkwijze.** Eenvoud voorop, slim waar nodig. Taakgericht. Persoonlijke betrokkenheid, geen accountmanager tussen jou en het werk.

**Bewijs.** Er zijn geen klantcases of testimonials beschikbaar. Verzin ze niet. De toolstack is het enige harde bewijs dat er is; gebruik dat zorgvuldig en verzin geen certificeringen of partnerstatus.

## Kleurpalet

Vastgelegd. Afgeleid uit Van Gogh, Zelfportret met grijze vilthoed (1887, Van Gogh Museum, publiek domein). Niet willekeurig gekozen: Van Gogh komt uit Noord-Brabant, net als Jeau.st, en het schilderij is opgebouwd uit losse toetsen die op afstand één beeld vormen. Dat is precies wat het werk is.

| Token | Hex | Rol |
|---|---|---|
| `ink` | `#14202A` | Paginaachtergrond |
| `slate` | `#1E323B` | Kaarten, secties, verhoogde vlakken |
| `pigment` | `#274F5B` | Randen, dividers, subtiele vlakken |
| `oker` | `#D08A45` | Enige accentkleur: links, CTA, markeringen |
| `linnen` | `#E8E1CC` | Primaire tekst |
| `muted` | `#A8A48E` | Secundaire tekst, labels, captions |

Optioneel `teal #6FA0AC` voor een tweede tekstniveau of hoverstaat.

Definieer deze als `@theme` variabelen in `src/input.css`, bijvoorbeeld `--color-ink: #14202A;`, zodat je ze als `bg-ink` en `text-linnen` gebruikt. Geen losse hexwaarden in de HTML.

Contrastwaarden zijn nagerekend: linnen op ink is 12.7:1, muted op ink 6.6:1, oker op ink 5.8:1, en ink op oker 5.8:1 voor een gevulde knop. Allemaal ruim boven AA. Blijf binnen deze combinaties of reken nieuwe zelf na.

Gebruik oker spaarzaam. In het schilderij is het warme oranje maar 2,5 procent van het doek; die verhouding is precies waarom het opvalt.

## Vormgeving

Ga hier verder zelf over. Wat wel geldt:

Het bestaande logo is een wit blokkig, bijna terminal-achtig woordmerk `jeau.st`. Laat dat je richting informeren in plaats van dat je er een willekeurige stijl omheen bouwt.

Het palet is donker en gedempt, niet zwart met een schreeuwend accent. Als je het naar dat laatste toe trekt, verlies je de reden dat het gekozen is.

Vermijd de looks waar dit soort pagina's standaard in vervalt: het crèmekleurige canvas met serif-display en terracotta accent, het bijna-zwarte scherm met één felle acid-groene accentkleur, en de broadsheet-layout met haarlijnen en nul border-radius. Als je bij een van die drie uitkomt, moet je kunnen uitleggen waarom dat voor déze opdracht de juiste keuze is en niet gewoon de eerste ingeving.

Kies één element waar de pagina om onthouden wordt en houd de rest eromheen stil. Typografie mag karakter dragen; het hoeft geen neutrale doorgeefluik te zijn.

Animatie alleen waar het iets zegt. Een pagina vol scroll-reveals leest als gegenereerd.

## Kwaliteitsvloer

- Responsive vanaf 360px.
- Zichtbare keyboard-focus, semantische HTML, `alt` op alle afbeeldingen.
- `prefers-reduced-motion` gerespecteerd.
- Contrast minimaal WCAG AA.
- `<title>`, meta description, Open Graph tags, favicon.
- JSON-LD `ProfessionalService` met naam Jeau.st, KvK 88930343, plaats Den Bosch, e-mail joost@jeau.st.
- `robots.txt` en een `sitemap.xml`.
- Een `CNAME` bestand met de inhoud `jeau.st`.

## Werkwijze

Maak eerst een kort ontwerpplan: de gekozen typefaces met hun rol, het layoutconcept in een paar zinnen, en het signature-element. Het palet ligt al vast, dat hoef je niet opnieuw te bedenken. Leg dat naast deze brief en schrap wat je ook voor een willekeurige andere consultancysite had bedacht. Pas daarna bouwen.

Lever aan het eind een korte toelichting: welke richting je koos, waarom, en welk risico je hebt genomen.
