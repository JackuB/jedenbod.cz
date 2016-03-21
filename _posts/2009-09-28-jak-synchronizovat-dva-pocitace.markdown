---
author: JackuB
comments: true
date: 2009-09-28 11:21:31+00:00
excerpt: 'Pokud máte dva nebo více počítačů, určitě víte, jaký občas bývá problém
  udržet všechna data aktuální.

  Několik tipů jak na lepší synchronizaci.'
layout: post
slug: jak-synchronizovat-dva-pocitace
title: Jak synchronizovat dva počítače
permalink: /580-:slug.html
categories:
- Internet
- Software
tags:
- G.ho.st
- GoodSync
- Google Docs
- gOS
- LAN
- Live Mesh
- RJ-45
- Software
- synchronizace
- WAN
- Windows
- Windows Live
---

Pokud máte dva nebo více počítačů, určitě víte, jaký občas bývá problém udržet všechna data aktuální.

Na notebooku máte starší verzi několika dokumentů, ale na velkém PC zase nemáte fotky, které jste nafotili včera a dali je jen na notebook. Časem v tom budete mít _bordel_. Manuální aktualizace jsou zkrátka nepohodlné, nepraktické a neefektivní.

Když jsem se poprvé setkal s tímto![Live Mesh preview](http://jedenbod.cz/wp-content/uploads/2009/09/live-mesh-preview.jpg) problémem neaktuálnosti, doufal jsem, že mi Google poradí mnoho různých kvalitních synchronizačních nástrojů. Bohužel, skoro všechny jsou k ničemu. Předem říkám, neexistuje skutečně kvalitní synchronizační nástroj. Skutečně, je to rána, ale není nic s čím bych byl skutečně spokojen. Ale buďme rádi alespoň za těch několik kvalitních.


## Trocha teorie


Při synchronizaci nám jde o to, aby se změny, které provedem na jednom PC, okamžitě, bez uživatelského zásahu, přenesly na druhé PC.


> _Zkrátka_: na PC číslo 1 napíšete odstavec do nějakého dokumentu, dáte uložit změny, a během několika vteřin se změny v dokumentu projeví na PC číslo 2.


Přenos dat mezi synchronizovanými počítači může být proveden:




  * **[LAN ](http://cs.wikipedia.org/wiki/Local_Area_Network)**- síťovým kabelem


  * **[WAN ](http://cs.wikipedia.org/wiki/WAN)**


    * Přes server 3. strany - data z PC1 se nahrají nejdříve na server poskytovatele služeb a poté se stáhnou do PC2


    * Pomocí P2P protokolu - zde je také potřeba serveru 3. strany, ale ten působí pouze jako prostředník, k vašim datům se nedostane





LAN samozřejmě vede stabilitou a rychlostí, bohužel PC musí být, logicky, propojeny kabelem, což je


  1. Na dálku nemožné


  2. Nepraktické


Naopak WAN - Internet je sice pomalejší, ale vhodnější pro menší soubory.


### Alternativy k synchronizaci dat mezi PC


Mít vše online.

Díky [gOS](http://www.thinkgos.com), [G.ho.st](http://g.ho.st/) nebo [Google Docs](http://docs.google.com/) si můžete být jisti, že dokumenty se kterými pracujete, jsou aktuální. Nevýhoda je zřejmá - žádný internet, žádné dokumenty.

[caption id="attachment_584" align="aligncenter" width="570" caption="G.ho.st"]![G.ho.st](http://jedenbod.cz/wp-content/uploads/2009/09/ghost-570x442.jpg)[/caption]


## Synchronizujeme menší data - dokumenty


Nejlepší volbou pro snadné a rychlé synchronizování menšího objemu dat je [Live Mesh](http://www.mesh.com) od Microsoftu. Dokáže synchronizovat složku mezi několika PC a online úložištěm - **Live Desktop**, takže se k souborům kdykoliv dostanete i z jiného PC.

[caption id="attachment_585" align="aligncenter" width="570" caption="Live Mesh Beta"]![Live Mesh Beta](http://jedenbod.cz/wp-content/uploads/2009/09/live-mesh-570x441.jpg)[/caption]

Do každého PC, které chcete synchronizovat, nainstalujete malou aplikaci, která se o vše postará automaticky a na pozadí. Výhodou je, že díky Live Desktop ani nemusí být druhé synchronizované PC online.

![Live Mesh Beta](http://jedenbod.cz/wp-content/uploads/2009/09/live-mesh-taskbar.PNG)

Nejlepší řešení je v rámci Dokumentů vytvořit složku, kterou chcete mít synchronizovanou a do ní pak ukládat vše důležité.

Synchronizace je skutečně rychlá, a i přes nálepku _Beta_, jsem nezaznamenal žádný problém. Navíc můžete využít i funkci vzdáleného přístupu, takže můžete používat druhé PC na dálku.

Microsoft ještě nabízí [Live Sync](http://www.foldershare.com/) a [SkyDrive](http://skydrive.live.com/). SkyDrive je pouhé online úložiště, ale Live Sync v teorii vypadá lépe než Live Mesh, bohužel, měl jsem s ním jen problémy.

Jiné služby blížící se kvalitou Live Mesh jsem nenašel.


## Synchronizujeme ve velkém - hudba, filmy


Tady je už synchronizace přes internet vyloučena. Přenášet desítky gigabajtů dat na dálku není příjemné. Je to pomalé, spojení se může přerušit atd.

Zde musíme přistoupit k síťovému _([LAN](http://cs.wikipedia.org/wiki/Local_Area_Network)) _připojení. Stačí použít síťový kabel [RJ-45](http://cs.wikipedia.org/wiki/RJ-45). Ten koupíte všude, kde se prodává něco s technikou.

[caption id="attachment_601" align="aligncenter" width="570" caption="RJ-45"][![RJ-45](http://jedenbod.cz/wp-content/uploads/2009/09/rj45-570x313.jpg)](http://cs.wikipedia.org/wiki/RJ-45)[/caption]

Pro základní synchronizaci, stačí soubory pouze zkopírovat po síti, ale pokud hledáte poněkud sofistikovanější způsob, který zkontroluje verze souborů, je tady [GoodSync](http://www.goodsync.com/).

Vyberete pouze cesty k synchronizovaným složkám a stisknete _Sync_. [GoodSync](http://www.goodsync.com/) automaticky porovná verze _(čas poslední změny)_ a vše synchronizuje.

[caption id="attachment_605" align="aligncenter" width="570" caption="GoodSync"]![GoodSync](http://jedenbod.cz/wp-content/uploads/2009/09/sync2.jpg)[/caption]


Například první synchronizace mé hudební knihovny _(skoro 50 Gb a 11 000 souborů)_ trvala něco málo přes hodinu a půl. Příště už bude čas znatelně kratší, protože se budou přenášet jen nové skladby.




![GoodSync](http://jedenbod.cz/wp-content/uploads/2009/09/good-sync.PNG)





## Závěrem


Kombinace neustálé synchronizace dokumentů s [Live Mesh](http://www.mesh.com/) a občasné manuální synchronizace pomocí [GoodSync](http://www.goodsync.com/) se mi jeví jako nejlepší možnost.

Synchronizujete PC? Jaké nástroje používáte?
