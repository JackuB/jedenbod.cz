---
author: JackuB
comments: true
date: 2011-06-14 18:01:19+00:00
excerpt: Proč bude budoucnost pro webdesignéry špatná?
layout: post
slug: slava-mobilnimu-internetu
title: Sláva mobilnímu internetu
permalink: /1141-:slug.html
categories:
- Internet
- iPhone
- Software
- Úvaha
tags:
- Android
- Firefox Mobile
- IE6
- Internet
- Internet Explorer
- iPhone
- Opera Mobile
- webdesign
- Windows Mobile
- Windows Mobile 7
- Windows Phone 7
---

[caption id="attachment_1142" align="alignright" width="240" caption="W3C vs. IE6 box model"]
![W3C vs. IE6 box model](http://jedenbod.cz/wp-content/uploads/2011/06/300px-W3C_and_Internet_Explorer_box_models.svg_.png)[/caption]


## Vzpomínáte na ty časy s IE6?


Naprosto **zkurvený box model**, desítky bugů, nepodpora PNG, zastavený vývoj _(protože i vývojáři věděli, jak velkou p******* udělali) _- hledání hacků bylo příjemné jako hledání min na Balkáně. O jejich užití a kompatibilitě se snad ani nebudeme bavit.

IE6 _bylo _zlo.

Sotva jsme [IE6 pohřbili](http://ie6funeral.com/) ([nebo ho teprve pohřbíme](http://www.ie6death.com/)) - webdesignéři a kódeři se mají zase na co těšit!

[![css mess](http://farm5.static.flickr.com/4007/4365152223_a026981156_z.jpg)](http://www.flickr.com/photos/atzu/4365152223/)

Nechám už plivání na nebožtíka.

[V roce 2015 bychom měli více používat mobilní zařízení než osobní počítače](http://mashable.com/2010/04/13/mobile-web-stats/). Jasně, žijeme v éře [post-pc](http://www.engadget.com/2011/03/03/editorial-its-apples-post-pc-world-were-all-just-living/) a [Microsoft](http://www.youtube.com/watch?v=p92QfWOw88I) i [Apple](http://www.apple.com/ipad/) nám chtějí tablety (a mobily) prostě prodat - takže je to částečně reálný odhad. Musíme ((MY, webdesignéři)) tedy čekat nárust poptávky po _mobile/tablet-ready_ webech. Jasně, [responsive webdesign](http://www.alistapart.com/articles/responsive-web-design/), HTML5/CSS3 - to půjde snadno.


## Déjà vu


Připravuji web, který bude_ mobile/tablet-ready_ a v rámci testování jsem otevřel několik emulátorů mobilních prohlížečů.

Testoval jsem _(obvinění zleva doprava)_




  * Safari na iOS ((testoval jsem ho více a hodnotím ho zatím nejvyšší známkou))


  * Firefox Mobile


  * Opera Mobile


  * Internet Explorer na Windows Phone 7 ((NAVÍC: trpí další spoustou (_vykreslovacích) _bugů, které na screenshotech nejdou vidět))





Světe div se, **mobilní prohlížeče jsou děsná sračka**. Nefunkční a nedostupné emulátory bych i omluvil _(*mávnutí rukou*)_, ale tohle:

[caption id="attachment_1150" align="aligncenter" width="570" caption="Jak vykreslují mobilní prohlížeče?"][![Jak vykreslují mobilní prohlížeče?](http://jedenbod.cz/wp-content/uploads/2011/06/mobilní-sračky-head-570x275.jpg)](http://jedenbod.cz/wp-content/uploads/2011/06/mobilní-sračky-head.jpg)[/caption]

**Každý prohlížeč vykresluje obsah po svém.** Ok, malé problémy. Chybějící text-shadow. Lištička i barvy půjdou opravit. Možná nějaký hack pro Operu Mobile? Hmmm? A zbytek půjde také opravit benevolentnějším přístupem k procentovým rozměrům. Zkusíme skrolovat dolů...

[caption id="attachment_1154" align="aligncenter" width="570" caption="Jak vykreslují mobilní prohlížeče?"][![Jak vykreslují mobilní prohlížeče?](http://jedenbod.cz/wp-content/uploads/2011/06/mobilní-sračky-bottom-570x275.jpg)](http://jedenbod.cz/wp-content/uploads/2011/06/mobilní-sračky-bottom.jpg)[/caption]

Yes! Yes! Yes! Vidíte to?!  Mám to snad komentovat? Jen se podívejte v plné velikosti. Jsme opět na začátku!

![Genious!](http://jedenbod.cz/wp-content/uploads/2011/06/genious128640853715840425-250x180.jpg)

Zase budu mít co dělat. **CSS a JS hacky pro různé verze prohlížečů, na různých platformách, s různými displeji a uživatelskými prvky.** Když se nemohou dohodnout ani na takových drobnostech, jako je **primitivní** layout několika divů, jak si asi poradí se složitějšími prvky? Nebo rovnou něčím interaktivním? To snad ani ne! Navíc, každý prohlížeč přijde se svou snůškou **vlastních a GENIÁLNÍCH **meta-tagů a CSS tříd. Nemluvě o úžasných standardech. Čekají nás _(zase) _křížové výpravy za správným vykreslováním?

Nutno podotknout, že jsem **ze srovnání vynechal**: **Android**, **WebOS**, speciální prohlížeče Motoroly, Nokie etc. Na ty už jsem neměl chuť.

Taky se těšíte?
