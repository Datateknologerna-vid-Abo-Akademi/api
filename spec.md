# DaTe API-specifikation
**Författare:** *toasplun*, *lsundman*

Vi behöver en API för att  kunna plocka loss vår webbsida från hur vi hanterar databasen och hur vi skapar händelser och anmälningar. Med en välplanerad API kunde vi stöda olika sätt att hantera vår information, utan att behöva vara rädd att något går sönder. Vi kunde också vara mera säkra på att det också i framtiden går att upprätthålla en något modern hemsida för DaTe.

Idén med det här dokumentet är att på en abstrakt nivå beskriva det vi behöver åstadkomma med vår API, men också att detaljerat beskriva hur implementationen borde se ut. 


## Funktioner

Hemsidan, och därav också i förlängningen API:n, borde ge användaren tillgång till följande DaTe-resurser:

- Statisk information om föreningen, “Pages”:
  > Användaren Olle vill hitta mer information om DaTe före han bestämmer sig för vilket universitet han söker till. Olle kommer oberoende inte in någon annanstans än ÅA
  > Tekn. Stud. Lisa är singel och vill bli stödjande medlem i DaTe, hon hittar nöjt alla information hon behöver på DaTes fina hemsida, och betalar redan dagen efter medlemsavgiften
- Informationsflöde, uppdateringar, “Posts”:
  > Olle vill veta när styrelsen äntligen håller knaslidejour igen. Ordförande Odvard har gått in och lagt till ett blogginlägg där han förklarat att dejouren börjar igen efter sommaren i november. Olle upptar informationen.
- Evenemang med anmälningar, “Events”:
  > Hikko Mupa arbetar som rektor vid Åbo Akademi och skall bestämma vilken dag som skall bli alla utbildningslinjers officiella tentdag. Hans högsta önskan är att alla tenter skrivs i krapula och besöker datateknologernas hemsda för att få en överblick över vilka veckodagar evenemang ofta ordnas på.
- Medlemsregister med hantering av medlemmar, deras klasser och övrig info, “Members”
- Statiskt innehåll i from av tent-pdf:er och bilder, “Assets”:
  > Kikael Murula jobbar som lektor vid Åbo Akademi. Han söker sig till Datateknologernas hemsidor för att se om de elaka studerandena laddat upp hans tenter i sitt tentarkiv.


## RESTfull-ish
- /pages
  - ger alla pages, med limit x
  - en page har subpages i viss kategori (inte nödvändigtvis enligt representation i UI)
  - innehåller enhetliga block som kan användas i UI var det passar
  - /:id specifik page
- /posts
  - ger alla posts, med limit y
  - /:id specifik post
  - JSON, texten själv som plaintext med Markdown markup
- /events
  - ger alla events, med limit x
  - /:id specifik event
- /members (users?)
  - denhär e lite fittigare
- /assets
- /r
  - diverse random saker man vill ha
  - /name 
    - Slumpat namn för anonyma/non-visible anmälda till events
  - /versions
    - Olika användares versioner av UI som finns tillgängliga
    - link till entrypoint (tex 
    - Date users borde kunna publisha egna frontends som använder APIn 


## Minimun Viable Product: 
- /pages (/pages/:id inte nödvändigt)
- /posts (/posts/:id inte nödvändigt)
-  UI: events → link till gamla sidans  events


## Milestones
1. Pages, Posts
2. Assets
3. Events
4. Members

