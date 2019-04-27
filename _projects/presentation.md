---
layout: project
title: Presentation
url_path: presentation
image_path: /images/presentation.png
carousel:
    - /images/presentation1.png
    - /images/presentation2.png
    - /images/presentation3.png
    - /images/presentation4.png
    - /images/presentation5.png
    - /images/presentation6.png
technologies: "XSLT  transformation, XHTML, CSS, XML"
date: 04/2019
state: "Vyriešený"
---

Cieľ zadania 3 z predmetu Webové publikovanie je vytvoriť možnosť zápisu prezentácie v jazyku XML a navrhnúť elementy pre ich označkovanie. Návrh elementov zrealizovat opísaním typu dokumentu pomocou vybraného jazyka (DTD, XSD, RELAX NG) spolu s vysvetlením účelu jednotlivých elementov.  Vytvoriť XSLT šablóny pre konverziu prezentácie z XML do XHTML+CSS a pre konverziu prezentácie z XML do PDF. 

Splnenie jednotlivých požiadaviek zadania je nasledovné. Ako prvé by som chcela opísať moje navrthuté tagovacie elementy, ktoré opisujú xml prezentáciu.

Navrhla som a na obrázkoch v slideshow je vidieť 7 možných rôznych slidov prezentácie. Koreňovým elementom prezetácie je element presentation.
Každý element slide má dieťa, ktoré opisuje aký typ slidu chceme použiť. 

**TYPY SLIDOV:**
- *title-slide* 

Je vhodný na titulný slide. Tento typ slidu má 2 povinné elementy: title a author. Avšak má aj jede nepovinný element, ktorým je subtitle. 
 
- *only-title-slide*

Tento typ slidu obsahuje iba povinný element title. Adekvátnosť použitia je napríklad v prezentácii, kde chceme uviesť nejaký celok slidom s názvom celku.

- *comparison-slide*

Comparison slide je navrhnutý svojím layoutom na porovnávanie dvoch prístupov. Napríklad pri porovnávaní plusov a mínusov alebo vymenúvavaní vlastností, ktoré navzájom porovnávame. Na slide je povinný element title a samotné dva listy, ktoré chceme porovnávať. Pričom je nutné v každom liste uviesť aspoň jeden list-item. Nepovinný element je description, ktorý je vhodný pri charakterizovaní porovnávania alebo pre bližší opis.

- *title-content-slide*

Tento slide je vhodne použiť pri možnosti title a ejakého jedného povinného element. Môžeme si vybrať medzi elementmi: table-wrapper, paragraph, list alebo image. Na slide tohto typu sa môže nachádzať ln jeden z týchto elementov a aj ten v počte jeden, aby bol dokument valídny.

Table wrapper je element, ktorý predstavuje tabuľku má povinné elementy row a cell. Atribúty elementu cell sú table-title, čím označíme titulné bunky a table-link, ktorým označíme ak sa v bunke nachádza link.

Paragpraph označuje súvislý text, ktorý chceme dať na slide. V komtexte title-content-slide môže byť tento paragraph len jeden.

List je list alebo zoznam. Je vhodný na vymenúvavanie.

Image je obrázok s atribútmi width, height a src, ktorý linkuje zdroj obrázka.

- *title-two-content-slide*

Povinné elementy v tomto type sú title a content, ktorý je obaľovacím elementom pre ďalšie medzi, ktorými si môžeme vybrať. Nachádza sa tu aj nepovinný element description, ktoý je umiestnený pod nadpicsom a upresňuje nadpis alebo obsah slidu.
Two content slide je adekvátny ak na slide chceme mať kombináciu elementu image a elementov list alebo paragraph.

- *blank-slide*

Blank slide neobsahuje žiadny element, tým pádom je primerané ho použiť ak chceme čistý slide.

- *bibliography-slide*

Bibliography slide je navrhnutý na vymenúvavanie literatúry, ktorá bola použitá pri prezentácii. Povinným elementom je element title a aj list bibliografických zdrojov. Bibliography, bibliography-item a source. v source sa môže nachádzať nepovinný element source-link, ak mám možnosť linku na stránku kde sme údaj našli.

Na opis dokumentu som použila jazyk RELAX NG (schema.rng). Následne som vytvorila xml dokument (presentation.xml), kde som ukázala demo prezentáciu. tento dokument prešiel validáciou RELAX NG validátora. Na vytvorenú prezentáciu som použila XSLT transformácie pričom som XML transformovala na XHTML+CSS PDF.

**XHTML + CSS (style.xsl, style.css)**

Pomocou elementu xsl:dokument jednotlivé slidy z xml dokumentu rozdeľujem na viac výstupov - XHTML stránok. Následne pomocou xsl:apply-templates axsl_template sa a atribútom match umožňuje xlt procesor prejsť všetky prvky a vygenerovať ich. Pridaní CSS súboru  dostane prezentácia štýly a zároveň je zaručené oddelenie obsahu od formy. Ďalšími elementami, ktoré som použila sú xsl:choise a xsl:if. Tieto procedurálne konštrucie som sa snažila používaťe len na miestach kde sú potrebné a radšej využiť silu xsl transformácií. Pravdaže ešte som pri tejto časti zadania využila elementy a atribúty typické pre XHTML.

**PDF (style-fo.xsl)**

Je dôležité podotknúť, že spracovanie od xml až k pdf potrebuje 2 procesy. Pomocou XSL transformácií si xml dokument upravíme do formátu xml dokumentu, ktorý označkujeme na pdf výstup. Tak ako v XHTML používame podobné konštrukcie a logiku, len namiesto XHTML tagov používvame tagy akými sú napríklad fo:block, fo:inline, fo:list-block, fo:basic-link, fo:exteranal-graphic či fo:table.

Pri oboch vyššie uvedených transformáciách je možná parametrizácia a vstup od používateľa. V súbore config.xml si môže používateľ zadefinovať pozadia slidov pri jednotlivých typoch, farbu či hrúbku písma názvu. 

**ZHRNUTIE**

Výstpy transformácií sú dosť podobné samotnej prezentácii. Pokúšala som sa vyhnúť redundancii a vhodne použiť jednotlivé tagovacie konštrukcie. Riešenie je moždulárne a ľahko rozšíriteľné  ďalšie možné elementy či atribúty. 



