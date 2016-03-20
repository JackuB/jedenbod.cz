---
author: JackuB
comments: true
date: 2009-10-16 19:24:22+00:00
excerpt: 'Nedávno jsem psal o tom, <a href="http://jedenbod.cz/538-jak-skryt-a-zabezpecit-soubory.html">jak
  skrýt a zabezpečit lokální soubory</a>. Teď se zaměříme na bezpečnost na internetu. '
layout: post
slug: jak-skryt-adresu-sveho-pc
title: Jak skrýt adresu svého PC
permalink: /617-:slug.html
categories:
- Internet
- Software
tags:
- Bezpečnost
- cookies
- Google Chrome
- Internet
- IP adresa
- MAC adresa
- PC
- proxy
- Sociologie
- soukromí
- Tor
- Windows
---

Nedávno jsem psal o tom, [jak skrýt a zabezpečit lokální soubory](http://jedenbod.cz/538-jak-skryt-a-zabezpecit-soubory.html). Teď se zaměříme na bezpečnost na internetu.

Důležité je, aby servery nezjistily, kdo ve skutečnosti jste. Na internetu můžete být identifikováni podle 3 věcí:




  1. [Cookies](http://cs.wikipedia.org/wiki/Cookies)


  2. [MAC adresa](http://cs.wikipedia.org/wiki/MAC_adresa)


  3. [IP adresa](http://cs.wikipedia.org/wiki/IP_adresa)


Podíváme se postupně na všechny.


## Cookies


Naprosto základní _sledovací_ _pes_. Malé soubory, obsahující informace _(většinou jakýsi kód)_, pro vaši identifikaci. Používá je váš oblíběný eshop, vyhledávač, firmy zaznamenávající statistiky pohybu uživatelů, ale klidně i _zlí lidé_. Obrana proti tomuto sledování je primitivní - zkrátka prohlížeči **zakažte cookies používat**. Není to nic složitého, stačí se proklikat nastavením prohlížeče.


## MAC adresa


Je fyzická adresa vašeho počítače _(odkazuje přímo na jeden určitý stroj - ne např. celou síť, jak je tomu u IP adresy)._ Na internetu ji většinou nikdo nevidí, ale občas, za speciálních podmínek, je možné, že ji někdo _z venku_ zjistí. Není to zrovna pravděpodobný případ, ale stát se to může.

Obrana je opět, naštěstí, relativně snadná. Některé síťové karty umí MAC adresu měnit samy, jinak to zvládne i [software](http://www.google.cz/search?hl=cs&safe=off&rlz=1C1GGLS_csCZ327CZ327&q=mac+address+change&btnG=Hledat&lr=).


## IP adresa


Na internetu je IP adresa v podstatě vašim občanským průkazem. Říká o vás mnoho, proto je dobré ji chránit. Obrana je v tomto případě poněkud větší oříšek. Získat IP adresu uživatele není problém. Například [tento web](http://whatismyipaddress.com/) dokáže podle IP adresy většinou relativně přesně určit její pozici.

[caption id="attachment_619" align="aligncenter" width="570" caption="Lokace podle IP adresy"]![Lokace podle IP adresy](http://jedenbod.cz/wp-content/uploads/2009/10/lokace-ip-adresy-570x268.PNG)[/caption]


### Základní ochrana přes webové proxy


Pokud jen potřebujete anonymně navštívit několik webů _(byli jste někde zabanováni - nebo jen nechcete, aby se o vás vědělo)_ stačí vám použít jeden z mnoha online proxy serverů. Např.: [Anonymouse.org](http://anonymouse.org/anonwww.html), [Free Web Proxies](http://proxy.org/cgi_proxies.shtml) a [další](http://www.google.cz/search?rlz=1C1GGLS_csCZ327CZ327&sourceid=chrome&ie=UTF-8&q=web+proxy).


<blockquote>**Proxy server** funguje jako prostředník mezi klientem a cílovým počítačem (serverem), překládá klientské požadavky a vůči cílovému počítači vystupuje sám jako klient. Přijatou odpověď následně odesílá zpět na klienta.

Zdroj: [Wikipedie](http://cs.wikipedia.org/wiki/Proxy_server)</blockquote>


Rychlost je většinou nic moc a málokterá webová proxy s nadpisem _"free"_ je skutečně bezpečná. Možností je zaplatit si některou z _profi_ proxy, u které máte jakoustakous jistotu _(pokud by se však ptala policie, proxy-neproxy, vaše záznamy se jim do rukou dostanou - snad jen některé proxy v jiných státech, nemají povinnost skladovat záznamy)._


### Softwarový proxy switcher


V podstatě stejný princip jako **web proxy**, jen s tím rozdílem, že vše ovládate z PC. [Je z čeho vybírat](http://www.google.cz/search?hl=cs&safe=off&rlz=1C1GGLS_csCZ327CZ327&q=proxy+switcher+software&btnG=Hledat&lr=), avšak softwarové proxy switchery jsou však již _profláklé_, používá je až příliš lidí, z čehož vyplývá nižší reliabilita.


### Tor


[Tor](https://www.torproject.org/) _(The Onion Router)_ je výborná věc. Nebudu se moc rozepisovat o jeho teorii - zkrátka, je to vysoce anonymní, šifrovaná síť, založená na spolupráci mnoha počítačů. Více o něm v obsáhlém článku na [Security Portalu: ](http://www.security-portal.cz/clanky/tor-onion-router-syst%C3%A9m-pro-vysoce-anonymn%C3%AD-%C5%A1ifrovan%C3%BD-p%C5%99%C3%ADstup-k-internetu)[TOR (The Onion Router) - systém pro vysoce anonymní a šifrovaný přístup k Internetu](http://www.security-portal.cz/clanky/tor-onion-router-syst%C3%A9m-pro-vysoce-anonymn%C3%AD-%C5%A1ifrovan%C3%BD-p%C5%99%C3%ADstup-k-internetu) nebo na [CZ & SK Tor komunitě](http://tor.security-portal.cz/).

Tor můžete používat jako plugin do Firefoxu, kdy po stisku jediného tlačítka začne být vaše aktivita anonymní. Avšak s použitím programu Privoxy _(je přímo v instalačním balíku Toru)_ můžete anonymizovat i další aplikace.



[caption id="attachment_625" align="aligncenter" width="570" caption="Tor, Privoxy a IE Proxy Changer"]![Tor, Privoxy a IE Proxy Changer](http://jedenbod.cz/wp-content/uploads/2009/10/tor-privoxy-proxy-changer-570x395.PNG)[/caption]

Stačí spustit Tor a Privoxy a jako adresu proxy _(v nastavení připojení)_ nastavit:


    127.0.0.1:8118


Já používám pro rychlou změnu proxy [IE Proxy Changer](http://www.allscoop.com/dotnet-software/proxy-changer.php) _(změna proxy v IE ovlivní nastavení mnoha programů - včetně Google Chrome)_. A výsledek?

[caption id="attachment_631" align="aligncenter" width="570" caption="Nová IP adresa"]![Nová IP adresa](http://jedenbod.cz/wp-content/uploads/2009/10/nová-ip1-570x271.PNG)[/caption]

Bohužel, jakousi _daň za bezpečnost_ platíte v podobě velmi malé rychlosti. Na druhou stranu jste však v podstatě nevystopovatelní.


## Další možnosti


Nyní znáte základy toho, jak se schovat na internetu.

Důležitou součástí správného zabezpečení je také schopnost smazat cache prohlížeče. V zásadě se doporučuje používat **prohlížeč spouštěný z flash paměti, se zákazem zápisu a s automatickým mazaním historie a cache**.

Dalším důležitým bodem je **vypnutí všech pluginů** - včetně flashe a javy. Některé pluginy se připojují na vlastní pěst nebo přeposílají vaši reálnou IP adresu. Pro zkušeného administrátora by nebyl problém vás najít.

Hodně štěstí.
