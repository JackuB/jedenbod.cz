---
author: JackuB
comments: true
date: 2009-10-19 05:45:33+00:00
excerpt: Praktické rady a ukázky jak zrychlit web poháněný Wordpressem.
layout: post
slug: optimalizujeme-wordpress
title: Optimalizujeme Wordpress
permalink: /633-:slug.html
categories:
- Internet
- Software
tags:
- CSS
- domény
- HTML
- javascript
- optimalizace
- PHP
- plugin
- webhosting
- Wordpress
---

## Analýza




### Co způsobuje zpomalení načítání stránek






  * **Webhosting**


  * Web


    * Obecně


      * **HTML, CSS a JS soubory**


      * **Obrázky**





    * **Wordpress **


      * **Pluginy**








Takto by se v základu daly shrnout příčiny pomalého načítání _(a celkově odezvy) _vašeho webu na Wordpressu.


## Řešení




### Webhosting


Internet je považován za médium, které _kašle_ na jakékoliv geografické hranice. Není tomu tak vždy. Je pravdou, že pokud se podíváte na nabídku webhostingu např. v USA, kde, doslova, za pár dolarů měsíčně, dostanete doménu, neomezený webový prostor a databází kolik jen chcete, můžete nad nabídkou českých webhostérů ohrnovat nos a rovnou přejít pod křídla zahraničních webhostérů. Jenže na geografické pozici vašeho serveru záleží. Zkusil jsem pingovat můj web [JedenBod.cz](http://jedenbod.cz) u českého [ONEbit](http://www.onebit.cz/) a americký webhosting [GoDaddy](http://www.godaddy.com/default.aspx).

[caption id="attachment_637" align="aligncenter" width="570" caption="Ping na JedenBod.cz a GoDaddy.com"]![Ping na JedenBod.cz a GoDaddy.com](/uploads/2009/10/ping-570x348.PNG)[/caption]

Průměrná odezva pro server v ČR je **desetkrát menší** než odezva ze serveru v USA. Ani nemusím zdůrazňovat, jak je odezva důležitá.

Je tedy dobré zvážit, odkud _(geograficky)_ očekávate nejvíce návštěvníků a podle toho vybírat webhosting.


### HTML, CSS a JS soubory × Obrázky




#### Menší web = rychlejší web = lepší web


V mnoha přířučkách pro optimalizaci webu vám doporučují zmenšovat CSS sooubory. Odstraňovat přebytečné třídy, dávat dohromady podobné vlastnosti a podobně. Jenže, **ruční optimalizace CSS vám zabere dlouhou dobu a ušetříte sotva pár kb**. CSS pro celý můj web má přibližně 15 kb _(nijak jsem ho neoptimalizoval a je v něm docela nepořádek)_.

![CSS](/uploads/2009/10/css1.jpg)

Dejme tomu, že dobrou optimalizací, která by trvala nejspíše několik hodin, by jste velikost srazili na 8 kb a ušetřili tím tedy _celých_ 7 kb. Pro představu o těchto velikostech, v článku o [Wordpressu a mobilních zařízeních](http://jedenbod.cz/511-jak-pripravit-wordpress-blog-pro-mobilni-zarizeni.html), jsou 4 malé náhledy Opery Mini. Každý z nich má více než 15kb, v průměru asi 16-17. Pod nimi je náhled emulátoru safari z iPhonu - ten má dokonce 300 kb. Optimalizace CSS je tedy zbytečná ztráta času. Ušetříte pár kb a web zkrátka rychlejší nebude.

To už je lepší volba zaměřit se na optimalizace JavaScriptu. Na webech lidé často souběžně používají [jQuery](http://jquery.com/), [Prototype](http://www.prototypejs.org/), [MooTools](http://mootools.net/) a podobné JS frameworky. Každý z nich má desítky kb a přitom by stačilo vše omezit na 1 až 2. Stačí dobře vybírat pluginy a _vychytávky_, jako různé skrolovátka, boxy nebo přepínače, tak aby fungovaly na jednom společném frameworku. Používáte-li například něco, co využívá jQuery a rádi byste ještě přidali [Lightbox](http://www.huddletogether.com/projects/lightbox2/), nemusíte do svého webu přidávat Prototype, Scriptaculous a Lightbox JS - stačí použít tento [lightBox napsaný pro jQuery](http://leandrovieira.com/projects/jquery/lightbox/).

![Download](/uploads/2009/10/net.jpg)

Optimalizace HTML je na Wordpressu poněkud jednodušší, stačí použít [plugin pro GZipování](http://www.ilfilosofo.com/blog/2008/02/22/wordpress-gzip-plugin/) stránek. Na mém webu to snížilo velikost HTML **z 45 kb na 14 kb**.

Něco o [optimalizaci obrázků](http://jedenbod.cz/409-jak-optimalizovat-fotky.html) jsem již psal. Je lepší uživatelům nabídnout spíše **rychlejší web s méně kvalitnějšími obrázky**. Uživatelé web nečtou, prolétavají ho - nevšímají si detailů.


#### Důležitý tip


Projděte si svůj web se zapnutým [Firebugem](http://getfirebug.com/) a zkontrolujte, zdali neodkazujete na neexistující soubory _(zbytečně zpomalují načítání)_. S Firebugem také můžete analyzovat rychlost vašeho webu a odhalit místa, která jej brzdí.


### Wordpress


**Je důležité mít Wordpress a pluginy stále aktuální.** Každá nová verze přináší nějaké zlepšení - vyplatí se aktualizovat. Důležitým pluginem je určitě [WP Super Cache](http://ocaoimh.ie/wp-super-cache/), pokud jej ještě nepoužíváte, tak si jej stáhněte.


### Pluginy ve Wordpressu


Pluginy nám mají pomáhat, ale občas mohou škodit. Prohlédněte si všechny zapnuté pluginy a postupně si u všech řekněte: _"Je to nutné?_ _Budou z toho mít nějaký prospěch uživatelé nebo já?"_ Mnoho pluginů je sice důležitých, ale pokud vám na blog píšou lidé komentáře jen občas, nemusíte mít plugin pro [ajax editaci komentářů](http://wordpress.org/extend/plugins/wp-ajax-edit-comments/). A podobně. Několik jich vypněte a v budoucnu si každý nový promyslete.

Vyhnete se tak hlavně [nedostatku paměti ve Wordpressu](http://jedenbod.cz/311-wordpress-fatal-error-allowed-memory-size-of-33554432-bytes-exhausted.html).

![Wordpress Memory](/uploads/2009/10/wordpress-memory1.jpg)

Existují další metody, jak zrychlit Wordpress _(doporučuje se například omezení dotazů na databáze (místo PHP funkcí pro volání hodnot jako název blogu atd. je vložte přímo do kódu))_, ale tyto vám jako základ určitě postačí.
