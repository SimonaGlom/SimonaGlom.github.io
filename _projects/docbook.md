---
layout: project
title: DocBook
url_path: docbook
image_path: /images/docbook.png
carousel:
    - /images/docbook1.png
    - /images/docbook2.png
technologies: "Docbook"
date: 03/2019
state: "Vyriešený"
---
Na vygenerovanie zo zdrojového formátu DocBook do PDF som použila odporúčanú šablónu od Jířiho Kostku. Táto šablóna je pevný základ môjho PDF dokumentu, avšak dizajn som trošku upravila. Na prvé stránky a to titulnú a anotácie (element abstract) som zabalila do element bookinfo. Titulná stránka obsahuje elementy affiliation, orgname či orgdiv, ktoré majú atribúty role. Podľa tých atribútov v thesis-tp-fo.xsl je zaručené štýlovanie. Na štýlovanie som použila vlastnosti font-weight: normal a ďalšie iné. Zakladnými elementami v .xml dokumente  je semantický element chapter, title, para či section.  Obrázky sú zabalené do element figure a v texte majú referenciu pomocou element  xref s použitím atribútov linkend a xrefstyle. Nechýba varianta alternatívneho textu pre nenačítanie obrázku pomocou element textObject. Tabuľky sú odkazovateľné takým istým spôsobom, ale sú umiestnené v texte aj pomocou členiacich elementov table, colspec a row. Takisto je v tabuľke využité zarovnanie dostredu. Element unlink je zaujímavým prvkom, ktorý je využívaný na referenciu url stránky.  Využívam ho napríklad v bibliografii na referencovanie online zdrojov. 
Zaujímavým prvkom, na ktorý by som chcela upozorniť je nastavenie nadpisov tabuliek a obrázkov pomocou thesis.xsl. Kde sa pomocou element xsl:if dá jednoducho pristúpiť iba k určitým tagom. 




