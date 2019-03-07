---
layout: project-item
title: SIMwear
url_path: simwear
image_path: /images/simwear.png
carousel: 
    - /images/simwear1.png
    - /images/simwear2.png
technologies: "Laravel, Vue, CSS&HTML"
date: 10/2018
tag: solved
---

SIMwear je e-shopový systém na oblečenie. Bol vytvorený na predmet Webové technológie, tvorí ho klientska časť a administrátorské rozhranie.<br>

KLIENTSKA ČASŤ 

Klientska časťje postavená na príncípe klient-server. O serverovú časť sa stará jazykPHP, nad ktorým je postavený framework Laravel. Perzistentné úložisko predstavuje relačná databáza MySQL. Na klientskej strane je použitý štruktúrovaný jazyk HTML spolu s CSS. Pre jednoduchšiu prácu s grid systémom, navigáciou a inými známymi komponentmi využíva CSS framework-Bootstrap.Interaktívnosť stránky zabezpečuje Javascript s knižnicou jQuery a http knižnicou axios.

ADMINISTRÁTORSKÁ ČASŤ

Administrátorska časť je zostavovaná na strane klienta (SPA). Celý frontend je postavený vo frameworku Quasar, ktorý komunikuje so serverom skrz API. Na komunikáciu využíva HTTP knižnicu axios. Reaktívne správanie aplikácie zabezpečuje knižnica Vue.js. Autorizácia je vykonávaná pomocou HTTP autorizačnej hlavičky. Autorizačný kľúč (API token) je získany po prihlásení a uložený do Cookies. Následne pri akejkoľvek požiadavke na server je autorizačná hlavička automaticky pridaná do požiadavky. API kľúč je po úspešnom prihlásení používateľa uložený v databáze. Navigácia v administrátorskom rozhraní je riešená cez vuerouter. Každácesta máurčenéči vyžaduje, aby bol užívateľautentifikovanýalebo nie. Pokiaľ užívateľnie je autentifikovaný, je presmerovanýna prihlasovaciu stránku.
