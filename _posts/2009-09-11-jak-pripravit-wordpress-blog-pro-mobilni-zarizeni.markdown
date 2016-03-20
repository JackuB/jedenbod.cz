---
author: JackuB
comments: true
date: 2009-09-11 07:00:59+00:00
excerpt: Přístup na web pomocí mobilních zařízení stále tvoří malou část návštěv.
  Nemá cenu ztrácet s optimalizací pro mobilní zařízení, jako telefony, PDA, iPhony
  apod. příliš času. Naštěstí, pokud používáte Wordpress, je optimalizace pro tyto
  zařízení otázkou několika minut.
layout: post
slug: jak-pripravit-wordpress-blog-pro-mobilni-zarizeni
title: Jak připravit Wordpress blog pro mobilní zařízení
permalink: /511-:slug.html
categories:
- Internet
- Software
tags:
- emulace
- Internet
- iPhone
- iPod
- mobil
- Opera Mini
- PDA
- Windows
- Wordpress
---

Přístup na web pomocí mobilních zařízení stále tvoří dost mizivou část návštěv (v řádu procent). Nemá cenu ztrácet s optimalizací pro malá mobilní zařízení, jako telefony, PDA, iPhony apod. příliš času. Naštěstí, pokud používáte Wordpress, je optimalizace pro tyto zařízení otázkou několika minut.


## Analýza


Nejdříve si odzkoušejte jak vypadá váš web v mobilním zařízení. Jestli nemáte žádné po ruce, můžete vyzkoušet [online verzi Opera Mini](http://www.opera.com/mini/demo/). Můj web vypadal asi takto.

![jedenbod-opera-mini-4.2-1](http://jedenbod.cz/wp-content/uploads/2009/09/jedenbod-opera-mini-4.2-1.PNG)![jedenbod-opera-mini-4.2-2](http://jedenbod.cz/wp-content/uploads/2009/09/jedenbod-opera-mini-4.2-2.PNG)

Jasně vidíte, že nic moc, abych tak řekl. Je to sotva na hranici použitelnosti. Naštěstí je tady řešení.


## Optimalizace pro všechny


Jedním pluginem můžete pokrýt téměř všechny mobilní zařízení. Stáhněte si [Wordpress Mobile Edition](http://wordpress.org/extend/plugins/wordpress-mobile-edition/) a rozbalte do adresářů podle návodu. Aktivujte plugin a utíkejte ho vyzkoušet na Operu.

Pohrál jsem si chvilku s lokalizací a web vypadal najednou takto:

![jedenbod-opera-mini-4.2-3](http://jedenbod.cz/wp-content/uploads/2009/09/jedenbod-opera-mini-4.2-3.PNG)![jedenbod-opera-mini-4.2-4](http://jedenbod.cz/wp-content/uploads/2009/09/jedenbod-opera-mini-4.2-4.PNG)

[Můžete se podívat sami](http://www.opera.com/mini/demo/).


## Optimalizace speciálně pro iPhone


Pokud máte nějaký čas navíc, můžete udělat speciální verzi jen pro iPhone. Testování je trochu komplikovanější emulací Safari z iPhonu.


### Emulace Safari iPhone na Windows


Nejdříve si musíte stáhnout [Safari pro Windows](http://www.apple.com/safari/). Poté tento [iPhone Web Simulator pro Windows](http://labs.blackbaud.com/NetCommunity/article?artid=662). Spustíte EXE a _voilà _máte **iPhone**_** **__(podle návodu z něj nemáte zkoušet volat, vážně to nefunguje)_.



[caption id="attachment_533" align="aligncenter" width="434" caption="iPhone web simulator"]![iPhone web simulator](http://jedenbod.cz/wp-content/uploads/2009/09/iphone-web-simulator.PNG)[/caption]

Teď si do Wordpressu stáhneme plugin [iWPhone](http://iwphone.contentrobot.com/), který aplikujete podobně jako Wordpress Mobile Edition. Zde si už můžete více vyhrát, kromě překladu, také s CSS. Můj web tedy na iPhonu vypadá přibližně takto:



[caption id="attachment_534" align="aligncenter" width="439" caption="iPhone web simulator - iWPhone"]![iPhone web simulator - iWPhone](http://jedenbod.cz/wp-content/uploads/2009/09/jedenbod-iphone-web-simulator.PNG)[/caption]

Pokud chcete, můžete využít také [speciální administrační rozhraní pro Wordpress](http://iphone.wordpress.org/), připravené pro iPhone/iPod.
