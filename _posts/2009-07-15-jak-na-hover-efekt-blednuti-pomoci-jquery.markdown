---
published: false
author: JackuB
comments: true
date: 2009-07-15 10:12:14+00:00
excerpt: Praktická ukázka easingu. Včetně zdrojových kódů.
layout: post
published: false
slug: jak-na-hover-efekt-blednuti-pomoci-jquery
title: Jak na hover efekt blednutí pomocí jQuery
permalink: /381-:slug.html
categories:
- Internet
tags:
- CSS
- easing
- HTML
- javascript
- jQuery
- použitelnost
- průhlednost
- web
- webdesign
---

Nedávno jsem psal o [easing](http://jedenbod.cz/384-take-it-easy.html)u. Na [Album dne](http://albumdne.jedenbod.cz/) také používám easing. Na hlavní stránce, v samostatných článcích, navigaci i v patičce. Ukážu vám jak na to. Za návod děkuji [HV-Designs.co.uk](http://hv-designs.co.uk/2009/01/19/jquery-fade-infade-out/). [Příklad](http://www.hv-designs.co.uk/tutorials/jquery/all.html) z webu [HV-Designs.co.uk](http://hv-designs.co.uk/).


## Jak na to






  1. [Stáhněte si jQuery](http://docs.jquery.com/Downloading_jQuery#Download_jQuery)


  2. Vytvořte si nový soubor a pojmenujeme ho _custom.js_


  3. Do custom.js vložte tento kód:


    $(document).ready(function(){
    $("OBJEKT").fadeTo("slow", 0.65);
    $("OBJEKT").hover(function(){
    $(this).fadeTo("slow", 1.0);
    },function(){
    $(this).fadeTo("slow", 0.65);
    $(this).stop();
    });
    });


Místo _OBJEKT_ můžete vložit jakýkoliv objekt. Pojmenujte ho přesně jako v CSS. Takže pro blednutí obrázků vložte _img_, pro div s ID test vložte _#test_ atd.


  4. Oba dva soubory (jquery.js a custom.js) nahrajte na web. Teď, v záhlaví _(před tag </head>)_ musíte vytvořit odkaz na custom.js a jquery.js. To lze jednoduše


    <script type="text/javascript" src="js/jquery.js"></script>
    <script type="text/javascript" src="js/custom.js"></script>







## Úprava efektu




### Více objektů


Pokud chcete nechat blednout více objektů, lze to jednoduše. V souboru custom.js zkopírujte kód z bodu 3 pod ten, který tam již máte a pouze vyplňte jiný objekt.


### Míra průhlednosti


Číslo v závorce za příkazem fadeTo určuje alfa kanál objektu, jinak řečeno, jeho průhlednost. Fungují hodnoty od 0 do 1. Můžete také změnit hodnotu 1.0, na 4. řádku, a nechat objekt přecházet například mezi průhledností 0,4 a 0,8.


### Rychlost efektu


V jQuery můžete rychlost zadat:




  1. Slow - pomalu _(standartně)_


  2. Fast - rychle


  3. Číslem


Určitě si vystačíte se slow/fast.


### $(this).stop();


Tento řádek v původním kódu nebyl, ale není na škodu. Ovlivňuje chování přechodu při hoveru.

Pokud tento řádek odstraníte, a přes objekt s tímto efektem několikrát rychle přejedete myší, bude chvíli _blikat, _což není zrovna žádoucí. Na druhou stranu, s tímto řádkem, pokud budete nad objektem s myší delší dobu, efekt se jakoby _zasekne _na 100% neprůhlednosti a _odblokuje_ se až při dalším přejetí myši. Ale stačí ho otestovat a uvidíte, co se vám více hodí.


## Přístupnost a použitelnost


S tímto efektem by žádné problémy nastat neměly. Obsah funguje i s vypnutým javascriptem.

A jako u všeho, i zde platí, že pokud ho budete používat rozumně, nebudou s ním mít vaši čtenáři žádné problémy.

**Dotazy?**
