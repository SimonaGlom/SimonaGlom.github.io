# Zadanie 1: Osobná webová prezentácia na GitHub pages

Vytvorte webovú prezentáciu (webové sídlo) o sebe. Zamerajte sa jednak na vaše profesné záujmy (napr. projekty, ktoré riešite/riešili ste, čo vás v informatike najviac baví, fascinuje = váš developerský profil) a jednak vaše osobné záujmy, hobby.
V rámci developerského profilu vytvorte sekciu Webové publikovanie, kde budete publikovať všetky tri vaše vypracované zadania z predmetu.
Využite pritom technológie Git + GitHub Pages + Jekyll + Markdown. Využite potenciál statického generátora Jekyll a jeho templatovacích možností.
Podrobné požiadavky na vypracovanie a odovzdanie zadania (priemerná úroveň kvality):
-	Sídlo musí obsahovať aspoň 5 podstránok, pri využití aspoň 3 rôznych rozložení (layout-ov)
-	V rámci šablon musí byť použité:
	aspoň 5 premenných
-	kolekcie alebo dátové súbory
-	aspoň 5 filtrov alebo tagov
-	aspoň 1 plugin (okrem pagination)

## Opis riešenia

### Podstránky

**Úvodná stránka** - uvítacie slová a linky na ďalšie podstránky   
**Kto som?** - pár viet o mne, mojich záujmoch a charakteristikách   
**Čo robím?** - vymenovanie programovacích jazykov a technológií spolu s komentárom o tom koľko sa im venujem a ako ich ovládam    
**Moje projekty** - vymenovanie projektov, ktoré som robila     
**Projekt** - bližšie oboznámenie sa s projektmi, ich stav, dátum začatia, opis, použité technológie

### Rozloženie stránok (Layout-y)

**default.html** - zahŕňa head, navigáciu, pätičku a skripty (v includes)    
**home.html** - toto rozloženie sa používa na úvodnej stránke, neobsahuje navigáciu ani pätičku   
**about.html** - použiva sa na stránke Kto som?  
**devtech-item.html** - používa sa na stránke Čo robím?, je to rozloženie jednej technólogie (logo, nadpis, komentár)  
**project.html** - šablóna na stránkach detailu projekov

### Premenné

**image_path** - v devtechs alebo projects, cesta k logám a obrázkom   
**technologies** - v projects, prístup k technológiách, v ktorých bol písaný projekt  
**date** - v projects, približný čas vytvorenia projektu   
**state** - v projects, je už ukončený vývoj alebo ešte prebieha   
**carousel** - v projects, pole obrázkov, ktoré sú využité v slideshow   
**devtechs, projects** - vytvorené kolekcie  
**project, image, devtech** - slúžia na iteráciu  

V _config.yml sa nachádzajú ďalšie premenné opisujúce doménu.

### Kolekcie alebo dátové súbory

**_projects** - kolekcia projektov  
**_devtechs** - kolekcia tecnológií 

### Filtre alebo tagy

Stránka obsahuje množtvo tagov a filtrov.  
**Najčastejšie tag-y**:
```
{% include file_name.html %}
{% if something %} {% endif %}
{% for item in items %} {% enfor %}
```

### Plugin

[**Slick**](http://kenwheeler.github.io/slick/) - vytvorenie slideshow na stránke detailu projektu (nachádza sa v priečinku /slick-carousel/)

[**Collapse**](https://getbootstrap.com/docs/4.1/components/collapse/) - pri mobilnej verzii sa skryje navigácia, plugin podporuje skrytie a ukázanie navigácie (nachádza sa v priečinku /js/collapse.js)

## Záver

SIMfólio obsahuje aj mobilnú verziu a  všetky obrázky prešli kompresiou  pomocou nástroja (https://tinypng.com/). Projekt je podporovaný prehliadačom Firefox. Webové sídlo je vytvorené pomocou Boostrap 4.




