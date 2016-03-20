---
published: false
author: JackuB
comments: false
date: 2009-03-24 21:16:36+00:00
excerpt: <p>Jednoduchý návod, jak nezapočítávat do statistik vlastní návštěvy, ale
  pouze návštěvy jiných uživatelů.</p>
layout: post
slug: vyskrtnete-se-z-vlastnich-statistik
title: Vyškrtněte se z vlastních statistik
permalink: /84-:slug.html
categories:
- Internet
tags:
- cookies
- Google
- Google Analytics
- HTML
- IP
- PHP
- Wordpress
---

Nedávno jsem řešil, jak se zbavit zkreslování statistik v různých monitorovacích službách, které jsem si způsoboval sám, když jsem používal své stránky. V **[Google Analytics](http://www.google.com/analytics/)** můžete svou **IP adresu** odfiltrovat přes filtry. Tato metoda mi však zůstala utajená, poněvadž jsem nepochopil jak na to. Druhá zásadní nevýhoda tohoto řešení je ta, že pokud používáte pro monitorování více služeb, musíte filtrování nastavit ve všech, nemluvě o tom, že některé tuto možnost nemají vůbec.





Osobně používám **[Google Analytics](http://www.google.com/analytics/)** a **[Crazy Egg](http://crazyegg.com/)**. Obě služby, stejně jako další podobné používají pro svou činnost krátký JavaScriptový kód umístěný v zápatí stránky. Řešení je jednoduché, stačí, aby se _vám _tento kód na stránce nezobrazil. Což lze jednoduše s trochou PHP:





    <?php if ($_SERVER["REMOTE_ADDR"] != "xxx.xxx.xxx.xxx") { ?>
    --- Měřící kód(y) ---
    <?php } ?>






Místo xxx.xxx.xxx.xxx vložíte svou IP adresu, kterou můžete zjistit například na [WhatsMyIP](http://whatsmyip.org/). A je to.

**_Ne! Moment!_**

Co?

**_Co když nemám statickou IP adresu, ale dynamickou? Ha?_**

No, v tom případě je toto řešení ve velké části případů nepoužitelné. Avšak, někdy máte sice dynamickou IP adresu, ale mění se např. pouze poslední trojčíslí. Nebo se střídá jen několik adres. To pak můžete udělat pole vašich IP a ty následně odfiltrovat. Nebo mě napadá, že byste mohl využít **cookies**.

**_To zní složitě._**

Moment, tak mě napadlo... **Wordpress **přece umí:






    <?php  if (current_user_can('level_10')) : ?>
    <?php print"admin is home" ?>
    <?php else : ?>
    <?php echo"
    --- Měřící kód(y) - Musíte vše převést na entity ---
    "; endif; ?>




Za _current_user_can_ děkuji [BraveNewCode](http://www.bravenewcode.com/2008/05/02/how-to-show-content-for-specific-users-in-wordpress-templates/)



Kdykoliv se přihlásíte, tak vás Analytics ani nic jiného co umístíte _echa_ nebude započítávat. Tak a je to.

**_Co když nepoužívám Wordpress?_**

Můžete použít tu první metodu s IP adresou.

**_Co když nepoužívám Wordpress a mám dynamickou adresu?_**

Tak to běžte [někam](http://www.google.cz) prosím vás! Já už jdu spát.
