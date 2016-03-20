---
author: JackuB
comments: true
date: 2010-06-27 19:21:12+00:00
excerpt: Inspirací k napsání toho článku pro mne bylo zjištění, že americká vláda
  v posledních letech investovala do protokolu Tor a začala monitorovat provoz na
  této síti. Je tedy Tor stále bezpečný?
layout: post
slug: jak-je-to-s-bezpecnosti-site-tor
title: Jak je to s bezpečností sítě Tor
permalink: /871-:slug.html
categories:
- Bezpečnost
- Internet
- Software
- Úvaha
tags:
- Bezpečnost
- Onion Routing
- P2P
- proxy
- sniffing
- SSL
- Tor
---

Inspirací k napsání toho článku pro mne bylo zjištění, že americká vláda v posledních letech investovala do protokolu [Tor](http://en.wikipedia.org/wiki/Tor_(anonymity_network)) a začala monitorovat provoz na této síti ((Nemohu přímo linkovat zdroj)).

Tento článek je jakýmsi volným pokračováním k mému staršímu návodu ohledně [skrývání IP a MAC adresy](http://jedenbod.cz/617-jak-skryt-adresu-sveho-pc.html). Hned na začátku v něm však chybí jedna důležitá informace: můžete být také **identifikováni podle odesílaných a přijímaných dat**.

Na začátek trocha teoretického tlachání:


## Jak vůbec funguje síť Tor?




### Nejdříve pár slovíček






  * **A**lice × **B**ob – dva uživatelé, kteří si posílají zprávu


  * **Tor Nod/Onion Router** – počítač/server, na kterém běží Tor ((Pokud nevíte co je Tor, přečtěte si můj starší článek, ve kterém je část věnová právě Toru - [Jak skrýt adresu svého PC](http://jedenbod.cz/617-jak-skryt-adresu-sveho-pc.html#tor))) nastavený tak, aby přijímal a přeposílal zprávy v Onion Cloudu


  * **Onion Cloud** – skupina Nodů, která si mezi sebou posílá šifrované zprávy _(působí jako poslové) _


  * **Exit Relay** – Druh Tor Nodu - Poslední Nod, než zpráva opustí Onion Cloud


  * **D**ave – Server, který zná adresy dalších Onion Nodů ((Ano, Tor není úplně decentralizovaný a má své vlastní Onion Proxy servery. Nebezpečí v případě většího DoS útoku.))




**(nebojte, začne to dávat smysl!)**





### Alice posílá Bobovi zprávu






  1. **Alice **(Client System) si od **Davea** (Onion Proxy) zjistí adresy **Tor Nodů** (Onion Router)


  2. **Alice** vyšle zprávu pro **Boba** (Target System) a ta vstoupí do **Tor (Onion) Cloudu**, kde tunely prochází přes počítáče sloužící jako **Tor Nody** (Onion Routery)[![Onion Routing](http://ntrg.cs.tcd.ie/undergrad/4ba2.05/group10/OnionRouting.png)](http://ntrg.cs.tcd.ie/undergrad/4ba2.05/group10/index.html)_Zdroj: _[_http://ntrg.cs.tcd.ie/undergrad/4ba2.05/group10/index.html_](http://ntrg.cs.tcd.ie/undergrad/4ba2.05/group10/index.html)


  3. Vše v této části je zašifrované. Data se posílájí šifrovanými tunely, které existují jen několik minut. Jednotlivé nody neznají ‘cestu zpět’, takže nemůžou zpětně vystopovat, odkud data přišla. **Onion Cloud je nejbezpečnější fází přenosu dat po síti Tor.**


  4. Nyní přichází klíčová fáze: zpráva pro Boba, která se doteď neustále přesouvala v šifrované podobě mezi jednotlivými Nody, vstoupí do posledního Exit Nodu_ (Na obrázku Exit Funnel)_, odkud má být předána přímo Bobovi. Zde se zpráva musí dešifrovat, aby ji Bob pochopil a až po dešifrování se odešle. A to je problém.




## Proč je to tak velký problém?


Dešifrovanou zprávu pro Boba může bez problémů přečíst:




  1. Správce Exit Nodu


  2. Útočník provádějící sniffing _(čmuchání)_ kolem portů Exit Nodu


Právě první možnost je ta, kterou používají americké zpravodajské služby. Spravují velké množství Exit Nodů, díky čemuž kontrolují provoz, který je prováděn skrze Tor sítě. V západních zemích pomalu ubývá Exit Nodů, které spravují soukromé osoby. Největší vinu na tomto úbytku mají především žaloby a policejní zásahy proti Exit Nodům _(spousta ilegálního provozu je vedena skrze Tor, takže o záminky na žaloby není nouze) _viz. článek [Why you need balls of steel to operate a Tor exit node](http://calumog.wordpress.com/2009/03/18/why-you-need-balls-of-steel-to-operate-a-tor-exit-node/) _(obvinění z šíření dětské pornografie)_. Případně článek [Because I ran Tor, the police took all my computers](http://toddsnotes.blogspot.com/2009/11/because-i-ran-tor-police-took-all-my.html) _(obvinění z napomáhání k únosu dítěte)_. Ano, i takové věci se dějí skrze Tor.

Ale samotný Tor nám ukazuje lepší stránku věci: [Kdo používá Tor](https://www.torproject.org/torusers.html.en). A jak ukazuje [Analýza provozu Tor Exit Nodu](http://www.omninerd.com/articles/What_Traffic_is_on_a_TOR_Relay), skutečně je využíván například k obcházení [Velkého čínské firewallu](http://en.wikipedia.org/wiki/Internet_censorship_in_the_People's_Republic_of_China) nebo i [v jiných zemích strádajících cenzurou internetu](http://en.wikipedia.org/wiki/Category:Internet_censorship_by_country). Přesně k těmto účelům byl Tor, jakožto i jiné projekty pro anonymní a necenzurovaný internet, vybudován. Samotní autoři si jsou vědomi, že Tor je využíván i ke špatným věcem, ale právě díky jednoduché obsluze z něj plyne více užitku pro lidi používající jej pro dobré účely. Zlý lidé mají mnohem více příležitostí maskovat své aktivity. Viz. [Zneužití Toru](http://www.torproject.org/faq-abuse.html.en).

To, že vláda, podle všeho zatím pouze ta americká, a v menší míře i čínská, dokáže kontrolovat odchozí provoz, je velmi limitující představa. Na The Hidden Wiki _(už podle názvu pochopíte, že ji nemohu přímo linkovat, je zkrátka ‘Hidden’ – naleznete ji na Tor síti)_ se píše dokonce o možnosti editovat přeposílanou zprávu. Tuto myšlenku podporuje také existence projektu [Metasploit](http://www.metasploit.com/) – více info v článku na ZDNetu o [chytání pedofilů na Toru](http://www.zdnet.com/blog/security/hacker-builds-tracking-system-to-nab-tor-pedophiles/114).


<blockquote>**2.** When child porn-related keywords are seen (either the Web request, or the response), inject a little extra HTML code into the response going back to the Web browser. This HTML code would connect to my decloaking engine.</blockquote>


Do odpovědi se zakomponuje například kousek [Javy](http://cs.wikipedia.org/wiki/Java_(programovac%C3%AD_jazyk)), která se na koncovém počítači připojí k serveru útočníka, čímž odhalí pravou IP adresu uživatele Toru. Samozřejmě, lze to obejít routováním **všech** připojení skrze Tor.

I v článku o [Toru na wikipedii](http://en.wikipedia.org/wiki/Tor_(anonymity_network)#Weaknesses) naleznete jeho další slabiny.


## Je tedy Tor nebezpečný?


**Odpověd je: Může být.**

Pokud z Exit Nodu odcházejí nešifrovaná data, je možnost odposlouchávání stejná, jako že vás odposlouchává váš ISP. Správcům Exit Nodů ([podle této analýzy provozu Tor Exit Nodu](http://www.omninerd.com/articles/What_Traffic_is_on_a_TOR_Relay)) se každou chvíli podaří zachytit nějaké to heslo, či zprávu _(například z IRC)._

Pokud však používáte end-to-end šifrování _([SSL](http://cs.wikipedia.org/wiki/Transport_Layer_Security)),_ [které byste používat měli](https://trac.torproject.org/projects/tor/wiki/TheOnionRouter/TorFAQ#CanexitnodeseavesdroponcommunicationsIsntthatbad) _(jdeli vám o bezpečnost tak moc, že používáte Tor),_ jste relativně v bezpečí.

Pokud navíc směrujete všechen provoz skrz Tor Proxy bránu, měli byste být téměř nevystopovatelní.

Občas se mluví o analýze provozu nebo o napadení Tor Nodů, ale i tak je bezpečnost Tor sítě, co se vystopovatelnosti týče, velmi velká. Více v [dokumentaci v sekci o útocích](https://svn.torproject.org/svn/tor/trunk/doc/design-paper/tor-design.html#sec:attacks). I když lze těžko zjistit, **kdo** daný obsah požadoval, je však relativně snadno možné monitorovat jaký obsah se po darknetu ((Skrytá část internetu)) pohybuje.

Záleží tedy primárně na:




  1. Zabezpečení vašeho PC – přesměrování DNS, používání nebezpečných ActiveX prvků, které se na vlastní pěst připojují mimo proxy, Spyware, Keyloggery atd.


  2. Šifrování posílaných informací – zabráníte odposlechu


  3. Možnosti útočníka – Má prostředky na sledování částí sítě? Může infikovat Tor Nody?


Samozřejmě záleží také na tom, co útočník chce. Buď si pouze ověřit, že s druhou stranou komunikujete _(toto, by se mu mohlo podařit, viz dokumentace Toru výše)_ nebo jaká data po síti přenášíte. Zkrátka záleží hodně na okolnostech. Avšak platí, že útoky, které by vás mohly na Toru ohrozit jsou mimo bezpečností rizika většiny uživatelů.

Samozřejmě existují i alternativy k Toru, ale ty jsou na tom s bezpečností _(z praktického pohledu)_ velmi podobně.




  * [Freenet](http://freenetproject.org/) – [wiki](http://en.wikipedia.org/wiki/Freenet) – skvělý na přenos souborů


  * [I2P](http://www.i2p2.de) – [wiki](http://en.wikipedia.org/wiki/I2P) – podobný na Tor _(viz. [srovnání I2P s Torem](http://www.i2p2.de/how_networkcomparisons))_


  * Případně menší [srovnání různých anonymních sítí](http://www.planetpeer.de/wiki/index.php/Main_Page)


Další materiály naleznete především na The Hidden Wiki a Onion Forum – pokud je máte pochopit, tak věřím, že si je bude schopni nalézt sami.

Hodně štěstí
