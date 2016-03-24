---
author: JackuB
comments: true
date: 2010-01-31 17:49:14+00:00
excerpt: Je možné použít průhlédné PNG soubory pro vytvoření paralaxního skrolování
  na stránce?
layout: post
published: false
slug: paralaxne-skrolujc-pozad-pomoc-css-a-jquery
title: Paralaxně skrolující pozadí pomocí CSS a jQuery
permalink: /836-:slug.html
categories:
- Internet
- Software
tags:
- CSS
- HTML
- javascript
- jQuery
- web
- webdesign
---

Když jsem si v [tomto tvítu povzdechnul](http://twitter.com/jedenbod/status/8458213115), bylo to po několika hodinovém zápasu s kódem, který jsem stejnak prohrál kvůli zastaralosti PC.



Zajímalo mě, zdali je možné rozhýbat PNG obrázky na pozadí a tím vytvořit zajímavý efekt – [paralaxní skrolování](http://en.wikipedia.org/wiki/Parallax_scrolling).



Paralaxní skrolování není vůbec nic nového:



[![](/uploads/livewriter/ParalaxnskrolujcpozadpomocCSSajQuery_FF1D/video2e8e43ffa0a2.jpg)](http://www.youtube.com/watch?v=4vN9h7N-z_E)



Současné implementace Paralaxního skrolování jsou mizivé – například [www.silverbackapp.com](http://www.silverbackapp.com), [dromaeo.com](http://dromaeo.com), [css-tricks.com](http://css-tricks.com/examples/StarryNight/). Žádného efektu si ani nevšimnete, poněvadž byste pro to museli měnit velikost okna, ale kdo to dneska dělá? Paralaxní skrolování je tedy rázem degradováno na určitý _easter egg_. Přitom si umím představit pořádné využití takového efektu.



Našel jsem několik návodů a podařilo se mi vytvořit 2 příklady:




  1. [jedenbod.cz/port](http://jedenbod.cz/port/) – pomalu skrolujte dolů

  2. [jedenbod.cz/paralax](http://jedenbod.cz/paralax/) – hýbejte s myší




V Google Chrome vše funguje bezvadně a už jsem uvažoval i o širším nasazení, ovšem když jsem otevřel Firefox, framerate šel rapidně dolů a vytížení procesoru vyskočilo na 100%.



Provedl jsem několik testů s různými prohlížeči a weby, které paralaxní skrolování používají – výsledky jsou velmi špatné. Firefox (i IE) měl problémy s pohyblivým průhledným *.PNG – dokonce i na [thebeatlesrockband.com](http://www.thebeatlesrockband.com/videos/cinematic) byl framerate téměř na nule. Velmi špatně dopadl také s použitím kódu [v prvním příkladu](http://jedenbod.cz/port/ ) (z [inner.geek.nz](http://inner.geek.nz/javascript/parallax)).



V současné době je tedy paralaxní skrolování naprosto nepoužitelné. Sice se mi menšími úpravami podařilo zvýšit framerate v obou případech, ale i tak zůstává velké vytížení procesoru.



Snad jen tento příklad [www.csslab.cl](http://www.csslab.cl) dosáhnul alespoň trochu použitelných výsledků i ve Firefoxu. Mimochodem, další příklady paralaxního skrolování: [www.kremalicious.com](http://www.kremalicious.com)



Je docela škoda že i v roce 2010 drží kreativitu na uzdě technika – i když překryv PNG s alfa kanály musí být naprosto snadný výpočet v porovnání s jinými věcmi, které jsou pro dnešní PC naprosto běžné.
