---
published: false
author: JackuB
comments: true
date: 2009-05-17 16:41:43+00:00
excerpt: Chyba, či záměrné pohrávání si s daty známého antispam Wordpress pluginu
  Akismet?
layout: post
slug: akismet-si-vytvari-spamy
title: Akismet si vytváří spamy?!
permalink: /236-:slug.html
categories:
- Internet
- Software
tags:
- Akismet
- antispam
- plugin
- spam
- Wordpress
---

Mnoho blogerů svěřuje své blogy pod ochranná křídla [Akismetu](http://akismet.com/), komentářovému antispamu. Formou [pluginů a knihoven](http://akismet.com/development/), ho můžete používat téměř v jakékoliv webové aplikaci. Stačí vám jen Akismet API klíč a je to. Jak snadné. Pak už jen sledujete, před kolika spamy, vás Akismet zachránil.

[caption id="attachment_237" align="aligncenter" width="157" caption="Ať žije Akismet"]![Ať žije Akismet](http://jedenbod.cz/wp-content/uploads/2009/05/122spamu.png)[/caption]

_Jenže._ 122 spam komentářů za pár dnů na blogu s mizivou návštěvností? Trochu mi to nesedělo.
Vzpomněl jsem si na jeden článek, který jsem napsal ještě na starém blogu. Díky záloze v Google Readeru jsem ho našel:


<blockquote>

>
> ## Velmi záhadná chyba ve Wordpresssu
>
>
**Akismet si vymýšlí vlastní spam komentáře?** Nemám žádné jiné logické vysvětlení jak by se mohly objevovat spam komentáře u článků, kterým jsem zakázal komentáře.

>
>

>   * Nejdříve jsem chtěl zamezit dalším spam komentářům u článku 'JackuB má good keyword value'. _“Chyba”_ nastala v tom, že jsem to udělal přes [plugin Comment Timeout ](http://wordpress.org/extend/plugins/comment-timeout/), což je kvalitní plugin na zakázání komentářů u starších článků. Zatím vše OK.
>

>   * Jenže kvůli tomu, že jsem komentáře zakázal netradičním způsobem, si Akismet jakoby _nevšiml_, že komentáře jsou uzavřené a nejde je tedy nijak přidat.
>

>   * U článku se začaly objevovat spam komentáře, které se tam **nemohly** z venku dostat. Tak kdo tedy? Jediná logická volba byl **Akismet**.
>

</blockquote>


Klikl jsem tedy na ono číslo 122, které mě přeneslo na stránku se zachycenými spamy.

[caption id="attachment_240" align="aligncenter" width="570" caption="Spam ve Wordpressu"]![Spam ve Wordpressu](http://jedenbod.cz/wp-content/uploads/2009/05/spam-570x553.png)[/caption]

Na první pohled jsem si ničeho nevšimnul. Málem jsem zavřel okno a už si toho nevšímal. Jenže když jsem roloval dolů, všiml jsem si určitých pravidelností.

[caption id="attachment_241" align="aligncenter" width="570" caption="Spam ve Wordpressu - označení pravidelností"]![Spam ve Wordpressu - označení pravidelností](http://jedenbod.cz/wp-content/uploads/2009/05/spamy-570x455.png)[/caption]

Všechny spamy byly koncipovány naprosto stejně. Vždy stejné rozložení textu a odkazů. Naprosto stejný počet slov.

Tady se mi něco přestalo líbit. Spamy se přece snaží _obelstít_ antispamy. Tak to na světě chodí. Proč spamovací roboti vrhají [milióny](http://akismet.com/stats/) identických spamů proti neproniktutelným zdem Akismetu?
Jen se podívejte do své spam složky na emailu a uvidíte, jak se emailové spamy _snaží_. Naproti tomu komentářový spam je stále jako přes kopírák.

A pokud by už nějaký spam náhodně prošel, nic se nestane. Proklikal jsem velké množství odkazů, jenže odhadem tak 95-99% jich bylo naprosto nefunkčních. Buď vedly na 404 stránky nebo na jakési testovací fóra, odkud jste byli během několika vteřin přesměrováni. Jen u několika _(asi tak 2)_ z nich jsem se dostal na jakési stránky propagující viagru.

Většina spam odkazů vedla na neexistující stránky na několika doménách. Buď [http://iwejri.com/](http://iwejri.com/), [http://eriejsw.com/](http://eriejsw.com/), [http://e89ru.com/](http://e89ru.com/) a dalších. Často také na jakási polská automaticky generovaná fóra, která mě přesměrovala zpět na Google.

[caption id="attachment_245" align="aligncenter" width="570" caption="Spam Site"]![Spam Site](http://jedenbod.cz/wp-content/uploads/2009/05/spam-site-570x371.jpg)[/caption]

Podle neměnícího se


    <!-- 21 queries. 0.282 seconds. -->


v patičce _(tento text se většinou dynamicky mění a informuje o tom, jak dlouho trvalo skritpu vygenerování stránky)_, odhaduji, že se jedná o statické, zkopírované stránky. V kódu jinak už není nic zajímavého, všechny odkazy, včetně odkazů na [Template.com](http://template.com/), která se tam dostaly nejspíše nahrazením originální URL, byly mrtvé. Taktéž vyhledávací pole, které mne na spam stránkách překvapuje vás vyhodí na 404 na Template.com. [Whois](http://who.is/) u žádné ze stránek taktéž nezjistil nic zajímavého, protože většinou byly detaily chráněné. _(Whois na IP adresy spamerů vedl jen na [RIPE NCC](http://www.ripe.net/))_

Žádná Viagra ani malware.
Podezdření ve mě narůstalo.

Vrátil jsem se zpět k Akismetu.
Sledoval jsem vývoj spamu, a 10.5. k večeru, po obdržení 11 spamů, vypnul Akismet. Výsledky mě poněkud překvapily:


![](http://chartgizmo.com/GenerateChart?id=6225)



Skutečně, **spamy přestaly chodit, po vypnutí antispamu**.
Zkusil jsem dokonce 11.5. napsat [článek o Facebooku](http://jedenbod.cz/252-kolika-zpusoby-jde-zrusit-ucet-na-facebooku.html), jestli tím náhodou spamboty nepřilákám. Jak vidíte, nic se nestalo. Další zvláštnost: přerušení mé denní dávky spamu, se mi, podle Google Analytics, nijak neprojevilo na návštěvnosti. _(spamy na blogu rozšiřovaly různé IP adresy, které by musel Google Analytics zaznamenat, a pokud by mne ze dne na den přestaly navštěvovat, tak si toho všimnu na grafu unikátních IP adres)_

Tohle už **JE** divné. Akismet jsem vypnul a používám antispam [Defensio](http://wordpress.org/extend/plugins/defensio-anti-spam/) _(přece jen, nebudu úplně bez obrany)_

Jestli máte blog, a divíte se, jak je možné, že Akismet vás během několika dnů/týdnů/měsíců ochránil už před tolika _milióny_ spamy, zkuste ho vypnout. O výsledky se můžete podělit v komentářích pod článkem.
Hodně štěstí.

Akismet jako antispam funguje výborně _(je pravda, že po dobu co jsem ho používal, neskončil žádný ham ve spamu a spam v hamu)_. Jenže software, který _lže_, aby vypadal dobře. To se mi moc nelíbí.


