---
published: false
author: JackuB
comments: true
date: 2009-04-13 14:32:50+00:00
excerpt: '<p>Přicházející <strong>Windows 7</strong> nejspíše bude jeden z nejlepších
  systémů, jaký <strong>Microsoft</strong> kdy vůbec vypustil. Jsou rychlé, přehledné
  a stabilní. Šly by ještě zlepšit?</p> '
layout: post
slug: 3-napady-pro-zlepseni-gui-windows-7
title: 3 nápady pro zlepšení GUI Windows 7
permalink: /143-:slug.html
categories:
- Software
- Úvaha
tags:
- Microsoft
- PC
- použitelnost
- Start menu
- taskbar
- Windows
- Windows 7
- Windows Vista
---

Přicházející **Windows 7** nejspíše bude jeden z nejlepších systémů, jaký **Microsoft** kdy vůbec vypustil. Jsou rychlé, přehledné a stabilní. Používám je už několik měsíců, jak na _velkém_ PC tak i na menším **netbooku Acer Aspire One**. Na obou, velmi rozdílných strojích, fungují skvěle.



[caption id="attachment_161" align="aligncenter" width="300" caption="Windows 7"][![Windows 7](/uploads/2009/04/windows7-300x240.jpg)](/uploads/2009/04/windows7.jpg)[/caption]



Přece jen, po nějaké době používání, mě napadlo pár věcí, které by šly zlepšit.





## Koncept - Expanzivní virtuální plocha




### Trocha teorie




Ještě nedávno jste při návrhu **GUI** pro desktopové aplikace nemuseli moc brát ohledy na místo. Monitory byly čím dál větší a těch malých ubývalo. Aplikace začaly mít až monstrózní okna a ovládací prvky _(ve stylu 2.0)_. Nikomu to nevadilo, místa bylo na ploše dost.

Jenže, nastává zlom s příchodem miniaturních **netbooků**. Jak jsem již psal, [místa na netboocích až tolik není](http://jedenbod.cz/56-office-2007-acer-aspire-one.html). Najednou nastává problém, protože na jedné straně máte obrovské monitory, na kterých není potřeba šetřit místem a na druhé straně miniaturní displeje netbooků, kde se hodí každý ušetřený pixel. U návrhu GUI lze naštěstí udělat kompromis, protože malé okno aplikace na velkém monitoru není až takový problém.





Něco podobného se děje i s chováním uživatelů.





#### Více prostoru -> více oken




Na velkých monitorech jsou zvyklí mít otevřené větší množství oken a překlikávat mezi nimi. To však na menších netboocích není tak dobře možné. A máme tady menší konflikt. Hardwarově se displej netbooku zvětšit nedá _(možnost tahat s sebou monitor pošlapává celou myšlenku netbooku)_. **Softwarově už ano.**





#### Virtuální plochy




Jednou z možností jsou virtuální plochy. Ale ouvej. Kdo s nimi déle pracoval, ví, že to není zrovna to nejlepší řešení. Přepínání mezi nimi není nic pro obyčejného uživatele.



[caption id="attachment_154" align="aligncenter" width="400" caption="Virtuální plochy"]![Virtuální plochy](/uploads/2009/04/virtualni-plochy.jpg)[/caption]



### Expanzivní virtuální plocha




Co takhle mít více prostoru, aniž by bylo nutné měnit/přidávat monitor nebo přepínat na _novou_?



[caption id="attachment_155" align="aligncenter" width="292" caption="Expanzivní virtuální plocha"]![Expanzivní virtuální plocha](/uploads/2009/04/exp-virt-plocha1.jpg)[/caption]



#### Horizontální expanze




Část vaší plochy by byla _schovaná_ mimo monitor. **Windows by pak připomínal nějakou RTS**. Po přisunutí okna k pravému _(dále od startu)_ okraji obrazovky _(až by okno sahalo trochu "za" obrazovku)_, by se vše začalo posouvat doprava. Pohybovalo by se vše, pozadí _(bylo by nutné použít nějaký širokoúhlý wallpaper, který by klidně mohl navozovat i 3D efekt)_, taskbar i ikony. Posouvání by muselo být limitováno, např. pouze do zdvojnásobení základní velikosti monitoru.

Druhý monitor zdarma? Super. Zvláště na netbooku bych to ocenil.





#### Horizontální i vertikální expanze




Stejný koncept, jen pro zkušenější uživatele, protože běžné BFU, by se mohlo snadno _ztratit_. _Reálný_ monitor, by byl vždy v levém dolním rohu, pro lepší orientaci, takže žádná expanze doleva ani dolů.





#### Doplňky




##### Minimapa




Miniaplikace, běžící nejspíše v nějakém rohu obrazovky. Ukazovala by rozmístění oken _(s ikonkou nebo thumbnailem - přes Aero)_. Možnost základní interakce s oknem.



[caption id="attachment_162" align="aligncenter" width="300" caption="Minimapa"][![Minimapa](/uploads/2009/04/exp-virt-plocha-minimapa-300x240.jpg)](/uploads/2009/04/exp-virt-plocha-minimapa.jpg)[/caption]



##### Zapojení taskbaru




Pokud ve **Windows 7** najedete myší na spuštěnou ikonku programu v taskbaru, všechna ostatní okna zmizí a na ploše zůstane jen to okno, na které jste ukázali. Něco podobného by šlo i s expanzivní plochou. Po najetí na ikonku by se na ní monitor rovnou vycentroval.





##### Easing




Ať to všechno dobře vypadá, dodáme ještě easing pro _hezké_ posouvání. _(posouvání s "rozjezdem" a "bržděním")_





#### Maximalizoavné okno




Tady nastává trochu logický problém. Pokud maximalizujete okno, je nějaké posouvání znemožněno. To by šlo. Jenže když se chcete dostat k nějakému oknu, které je za ohybem? Zamezit jakémukoliv posunu, je-li nějaké okno maximalozované? Povolit posun? A taky, při maximalizaci okna, nezískáte ani pixel navíc. To by snad vyřešilo nějaké delší testování, které bohužel nemůžu provést.





* * *





## Koncept - Taskbar podle aktivity




Na **taskbar **se postupem času nabaluje čím dál více ikon. Některé používáme neustále _(jako prohlížeč, přehrávač hudby)_ některé jen při práci _(více prohlížečů, editory)_ a některé jen pro zábavu _(hry, IM programy)_. Na taskbaru jsou všechny tyto ikonky různě pomíchané.



[caption id="attachment_166" align="aligncenter" width="300" caption="Taskbar"][![Taskbar](/uploads/2009/04/heatmap-taskbar-300x23.jpg)](/uploads/2009/04/heatmap-taskbar.jpg)[/caption]



Tady vidíte menší pokus o _něco-jako-heatmapa_, toho jak vypadal můj taskbar. _Červená _jsou často používané ikonky, _modrá_ práce a _zelená_ zábava _(heh, to zní jako nový slogan SZ)_. Ikonky jsou uspořádané, jenže i tak je práce s nimi poněkud chaotická. Pokud pracuji, musím myší projíždět i přes aktuálně nepoužívané ikonky. A když nepracuju, nepotřebuji _pracovní_ ikonky. Přilepovat ikonky na taskbar je navíc silně návykové, takže za chvíli vám dojde i místo.





**Řešení:** mít na taskbaru několik setů ikonek.

Přepínání by se dělo pouhým stisknutím tlačítka. Po pravém kliknutí na ikonku by se kromě Pin/Unpin to/from taskbar objevila i možnost **Shared icon**, takže by byla v obou setech. Uživatel by si jen vytvořil 2 profily, pak do každého natáhnul, co chce, několika ikonkám by dal _"Shared"_ a bylo by to. Přehlednější taskbar je na světe.





* * *





## Koncept - Start Menu jako ovládací středisko




Osobně mi příjde potenciál Start menu dost nevyužitý. Spíše bych ho viděl jako něco, odkud bych měl být schopen ovládat celý PC, z jediného bodu. Ve** Windows Vista **se mi líbí **Welcome Screen** _(na **Windows 7 **je to "**Getting Started**")_.



[caption id="attachment_168" align="aligncenter" width="300" caption="Windows 7 Getting Started"][![Windows 7 Getting Started](/uploads/2009/04/getting-started-300x240.jpg)](/uploads/2009/04/getting-started.jpg)[/caption]



_Welcome Screen/Getting Started _vám nedává moc možností, ale směřuje to tam, kam chci teď dojít.



[caption id="attachment_171" align="aligncenter" width="426" caption="Windows 7 Start Menu"]![Windows 7 Start Menu](/uploads/2009/04/start-menu.jpg)[/caption]



Takto vypadá **Start Menu ve Windows 7**. Je to jen jakýsi rozcestník. Nic s ním neuděláte, jen vás může nasměrovat, ale co takhle změnit koncepci z rozcestníku na **velitelské stanoviště**?





Šlo by jen o dodání možnosti provádět základní úkony s PC jen ze Start Menu. Takže připojení k wifi by se už neřešilo z pravého dolního rohu apod. Přidala by se i možnost _pluginů _a mohli byste ze Start Menu ověřovat nové emaily nebo vytížení procesoru. Možná by šly i integrovat Gadgety, takže pouhým přetažením na start si do Start Menu doplníte co potřebujete.





* * *




## Pod čarou




Je docela možné, že nějakou podobnou vymoženost už má nějaký jiný OS. Pokud o něčem víte, podělte se v komentářích.



