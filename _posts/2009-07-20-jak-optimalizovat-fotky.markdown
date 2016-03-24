---
published: false
author: JackuB
comments: true
date: 2009-07-20 09:12:15+00:00
excerpt: "<em>Rychlý tip.</em> \n \nVčera jsem připravoval svůj <em>cestovatelský\
  \ web</em>, na kterém se budou, kromě jiného, také zobrazovat fotky nahrané na <a\
  \ href=\"http://www.flickr.com/\">Flickr</a>. Jak je tam dostat rychleji?"
layout: post
slug: jak-optimalizovat-fotky
title: Jak optimalizovat fotky
permalink: /409-:slug.html
categories:
- Internet
- Software
tags:
- Flickr
- fotky
- freeware
- Software
---

_Rychlý tip._

Včera jsem připravoval svůj _cestovatelský web_, na kterém se budou, kromě jiného, také zobrazovat fotky nahrané na [Flickr](http://www.flickr.com/). Flickr má výhodu v tom, že má dobrou API, se kterou nebude problém zobrazovat aktuální fotky. Jenže má to i háček, za _(kalendářní)_ měsíc na něj můžete přenést jen 100 MB. Což je docela problém. Když si vezmeme +/- 70 fotek nafocených v 8Mpix rozlišení, dostaneme se na velikost 200 MB. Flickr má samozřejmě [Pro](http://www.flickr.com/upgrade/) program, kdy je vše neomezené, ale nabízí pouze předplacení na celý rok. Bohužel, zrovna teď na kartě 25$ nemám, takže se budu muset vlézt do těch 100 MB.

A tím se dostáváme k tomu, **jak zoptimalizovat **_**(zmenšit)**_** fotky**.

Byl jsem zděšen tím, že jsem nemohl najít nějaký jednoduchý program, do kterého bych _naházel_ fotky, určil jak moc je chci zmenšit, zmáčknul tlačítko a bylo by hotovo.

Nakonec jsem naštěstí našel výborný český freeware **[JPEG Resampler](http://software.macek.cc/resamplercz.php).**

[caption id="attachment_410" align="aligncenter" width="569" caption="JPEG Resampler"]![JPEG Resampler](/uploads/2009/07/jpeg-resampler.PNG)[/caption]

**JPEG Resampler** podporuje všemožné optimalizace, přesně podle toho, jak potřebujete. Můžete si vybrat dokonce kvalitu výsledné fotky. Dále se určitě hodí možnost přidání vlastního loga do optimalizovaných fotek nebo nové pojmenování souborů.

Zkusil jsem převést 1 GB 8Mpix fotek _(tj. 280 fotek)._ Zmenšil jsem je na 800×600 pixelů, což je velikost, která pro Flickr, potažmo web, bohatě stačí. Kvalita byla nastavena na 80 _(dobrých výsledků dosáhnete klidně i s kvalitou 65)._ Operace trvala něco mezi 10-15 minutami. A výsledná velikost? 21 MB. To jsou nějaké 2% z původní velikosti.

Je rozdíl nahrávat na web 1 GB nebo 21 MB.

Kvalita je samozřejmě dobrá, tady se můžete podívat na [příklad](http://www.flickr.com/photos/30548236@N02/3733965071/), jak nakonec vypadá optimalizovaná fotka přímo na Flickru. Pro rychlé sdílení s přáteli, výborné.
