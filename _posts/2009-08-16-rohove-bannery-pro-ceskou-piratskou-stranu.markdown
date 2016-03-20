---
published: false
author: JackuB
comments: true
date: 2009-08-16 11:36:18+00:00
excerpt: Vzpomínáte si na malé rohové bannery, které jste ještě před pár lety mohli
  vidět na každém blogu? Většinou to bylo něco jako <em>Podporuji _____</em> nebo
  <em>Jsem proti _____</em>. Napadlo mě oživit tento fenomén a vyrobil jsem několik
  bannerů pro <a href="http://www.ceskapiratskastrana.cz/">Českou Pirátskou Stranu</a>.
layout: post
published: false
slug: rohove-bannery-pro-ceskou-piratskou-stranu
title: Rohové bannery pro Českou Pirátskou Stranu
permalink: /439-:slug.html
categories:
- Internet
tags:
- Česká Pirátská Strana
- ČPS
- CSS
- HTML
- politika
---

Vzpomínáte si na malé rohové bannery, které jste ještě před pár lety mohli vidět na každém blogu? Většinou to bylo něco jako _Podporuji ______ nebo _Jsem proti ______. Napadlo mě oživit tento fenomén a vyrobil jsem několik bannerů pro [Českou Pirátskou Stranu](http://www.ceskapiratskastrana.cz/).

[caption id="attachment_457" align="aligncenter" width="570" caption="Rohové bannery pro ČPS"]![Rohové bannery pro ČPS](http://jedenbod.cz/wp-content/uploads/2009/08/cps-banners-570x372.PNG)[/caption]

Všech 28 bannerů si můžete stáhnout v jediném archivu: [ČPS rohové bannery](http://jedenbod.cz/wp-content/uploads/2009/08/CPS-rohove-bannery.rar).rar

Vložení do stránky je pak velmi jednoduché.




  1. Nahrejte vybraný banner na svůj web


  2. Do souboru CSS vložte:


    #cps-banner {
    position: absolute;
    right: 0;
    top: 0;
    display: block;
    height: 150px;
    width: 150px;
    background: url(jmeno-banneru.gif) no-repeat;
    text-indent: -999em;
    text-decoration: none;}







    * Pokud chcete banner vlevo, změňte _right: 0;_ na _left: 0;_


    * Pokud jste si vybrali menší banner, zmeňte velikost ze 150px na menší _(např. u banneru **100-jolly.gif** změňte width i height na 100px)_


    * Nezapomeňte také správně vyplnit cestu k banneru





  3. Do HTML, nejlépe na začátek nebo na konec, vložte tento kód:


    <a id="cps-banner" href="http://www.ceskapiratskastrana.cz/"></a>





Hotovo


### Výsledek


Zkuste si ho sami. Vpravo nahoře máte Jolly Rogera.



* * *

Za CSS kód pro umístění banneru děkuji [Exploding-boy.com](http://www.exploding-boy.com/2006/01/09/easy-top-corner-banners-with-css/)

Pokud chcete, můžete to ještě _okořenit_ pomocí [Javascriptu/jQuery](http://jedenbod.cz/381-jak-na-hover-efekt-blednuti-pomoci-jquery.html).
