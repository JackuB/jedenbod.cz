---
author: JackuB
comments: true
date: 2009-09-07 20:34:24+00:00
excerpt: Možná jste jen <em>paranoidní</em> nebo skutečně máte v PC něco, co by se
  nemělo dostat ven. Tak jako tak, pokusím se vám pomoci. Praktické rady pro zabezpečení
  PC.
layout: post
slug: jak-skryt-a-zabezpecit-soubory
title: Jak skrýt a zabezpečit soubory
permalink: /538-:slug.html
categories:
- Hardware
- Internet
- Software
tags:
- Bezpečnost
- CyberShredder
- HDD
- jpg
- rar
- TrueCrypt
- Windows
---

Možná jste jen _paranoidní_ nebo skutečně máte v PC něco, co by se nemělo dostat ven. Tak jako tak, pokusím se vám pomoci.


## Primitivní metody - Proti zvídavým uživatelům




### Změňte jméno a atributy souboru


Pokud potřebujete ukrýt například soubor fotka.jpg před jiným uživatelem PC, není nic jednoduššího než změnit název na něco nesmyslného. Včetně koncovky. Pro inspiraci například _DtcInstall.log_, _Ultimate.xml_ nebo _rasauto.dll (náhodně vybrané názvy souborů ze složky Windows)._

Pokud máte na PC vypnuté zobrazování systémových a skrytých souborů, klikněte pravým na přejmenovaný soubor -> vlastnosti a v atributech zaškrtnětě _**Skrytý**._

[caption id="attachment_539" align="aligncenter" width="387" caption="Vlastnosti - Skrytý"]![Vlastnosti - Skrytý](/uploads/2009/09/atributy-skrytý.PNG)[/caption]

Soubor naoko zmizí. Můžete ho znovu zobrazit, když v průzkumníkovi zvolíte Nástroje - Možnosti složky - Zobrazení a povolíte zobrazování skrytých souborů. Pro použití musíte souboru opět přidat správnou koncovku.



[caption id="attachment_540" align="aligncenter" width="353" caption="Upřesnit nastavení"]![Upřesnit nastavení](/uploads/2009/09/upřesnit-nastavení.PNG)[/caption]


### Schovejte soubor hluboko do systémových adresářů


Takto upravený soubor můžete schovat do nějakého náhodného adresáře například ve složce Windows. Kdo neví přesně co hledá, tak takový soubor nemá šanci odhalit.

Toto byly základní metody pro chytré děti.


## Středně bezpečné - Proti zvídavým policistům


Zde se již nabízí více cest. Vybírám jen několik.


### Schování rar do jpg


Pokud přece jen nepotřebujete až takovou ochranu stačí schovat **rar **archiv, s libovolným obsahem, do **jpg**. Není to nic složitého. Podívejte se na tento obrázek: [vysledek.jpg](/uploads/2009/09/vysledek.jpg). Stáhněte si jej na plochu a zkuste jej otevřít jako normální obrázek. Vše OK. A teď jej otevřete ve WinRaru.

Jak na to?

Vše lze bez nějakého programu, stačí příkazová řádka ve Windows. Vložte obrázek i rar do jedné složky. Použil jsem _c:\rar-test_.

[caption id="attachment_545" align="aligncenter" width="570" caption="Rar v jpg"]![Rar v jpg](/uploads/2009/09/rar-v-jpg-570x333.PNG)[/caption]

Pomocí příkazu


    cd


přejděte do správné složky a pak použijte


    copy /b soubor.jpg + soubor.rar vysledny_soubor.jpg


Není problém opatřit rar heslem a výslednou fotografii umístit mezi 1000 fotek z dovolené nebo můžete použít jednu z výše uvedených metod.


### Šifrování souboru


Praktická metoda. Již mnoha lidem se osvědčil program [TrueCrypt](http://www.truecrypt.org/). Obsahuje i klikací UI, takže s ním není problém dobře zašifrovat vše, od malých souborů až po celé disky. Už se základním [AES ](http://cs.wikipedia.org/wiki/Advanced_Encryption_Standard)šifrováním jsou vaše soubory prakticky v bezpečí. Pro paranoidnější z vás však TrueCrypt nabízí i trojité šifrování pomocí AES-Twofish-Serpent. Alternativní program: [FreeOTFE](http://www.freeotfe.org/).


### Šifrování celého disku


Použití TrueCryptu pro zašifrování systémového disku, mi přijde jako dobrá alternativa. Je to docela riskantní krok _(nikdy nevíte co se může při šifrování semlít)_, takže pokud to _**skutečně **_potřebujete, tak do toho. Ale nezapomeňte na kompletní zálohu. Míra takového zabezpečení je velmi vysoká. Šifra je v podstatě neprolomitelná _(pozor na uhádnutelná hesla!)_. Z disku se dá přečíst jen počáteční zápis TrueCryptu. K vašim bajtům se nikdo nedostane.

Nezapomínejte také na to, že šifrování znamená zpomalení výkonu vašeho systému.


## Velmi bezpečné - Proti VELMI zvídavým lidem


Občas se stane, že máte něco, co je skutečně důležité. Ne, nemyslím vaše nahé fotky před zrcadlem. Ale něco **SKUTEČNĚ** důležitého. Zabezpečit něco takového není zrovna jednoduché. Předchozí metody, kromě šifrování, jdou prohlédnout a co se šifrování týče, můžete být donuceni říct heslo. Ať už vládními agenty nebo sociohackingem.![FBI Party Van](/uploads/2009/09/FBI-570x324.jpg)

Mezi nejbezpečnější cesty pro zabezpečení se jeví použití TrueCryptu s možností skrývaní partition nebo celých operačních systémů. Ze zkušeností ostatních vím, že se vyplatí mít nějaká data, _jakože _skrytá. Klidně zašifrovaná pomocí TrueCryptu, jen na odvedení pozornosti. Když vydáte tyto, nemusí se nikdo dozvědět o dalších zašifrovaných datech na vašem PC.

Nějaký jednoduchý návod neexistuje. Nemůžete vědět, do jaké situace se můžete dostat, ale jedno je jisté. Pokud máte něco _nebezpečeného_, dejte si se zabezpečením na čas.


## A pár tipů navíc




### Jak skutečně _odstranit_ soubory


Určitě víte, že smazáním souboru pomocí průzkumníku, se souboru nezbavíte. Jen se vymaže z indexu souborů. Na disku stále zůstává. Aby se soubour nedal obnovit, musíte ho přepsat nějakými daty. K tomu se hodí jednoduchý program [CyberShredder](http://www.cylog.org/utilities/cybershredder.jsp), který právě toto umí.

[caption id="attachment_551" align="aligncenter" width="318" caption="CyberShredder"]![CyberShredder](/uploads/2009/09/CyberShredder.PNG)[/caption]

Přepisování daty sice chvíli trvá, ale ani forenzní analýza by neměla odhalit, jaká že data tam byla předtím.


### Jak správně vymazat kompletní obsah pevných disků


[Ultimate Boot CD](http://www.ultimatebootcd.com/) _(UBCD)_, je záchranné CD pro administrátory. Obsahuje také několik nástrojů pro vymazání disku, aby z něj již nešlo číst. Velmi dobře funguje [Darik's Boot And Nuke](http://www.dban.org/). Ten funguje stejně jako CyberShredder, přepíše disk náhodnými daty.


### Jak se rychle zbavit pevného disku


Správné vymazání chce čas, ale pokud vám již někdo klepe na dveře, tak jej moc nemáte. Fungovat by měly silné magnety a kladivo/šroubovák. Pravděpodobnost obnovení není malá, ale pokud byl disk zašifrován, jste téměř v bezpečí.

Osvědčily se také různé kyseliny schopné rozleptat HDD.

Oheň ani vodu nezkoušejte, nefungují příliš spolehlivě. Armáda Spojených Států doporučuje jako rychlý správný způsob použití [něčeho takového](http://www.semshred.com/content56.html).

Hodně štěstí.
