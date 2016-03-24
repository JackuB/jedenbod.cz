---
author: JackuB
comments: true
date: 2014-12-22 09:37:38+00:00
layout: post
slug: seznam-cz-prohlizec
title: Seznam.cz prohlížeč
permalink: /1583-:slug.html
categories:
- Bezpečnost
- Internet
- Software
tags:
- AngularJS
- Bezpečnost
- browser
- Google Chrome
- HTML5
- javascript
- Seznam.cz
---

Nejspíše vám neuniklo, že Seznam.cz [oznámil](http://seznam.seznamblog.cz/post/105271178401/seznam-cz-predstavuje-prvni-verzi-sveho-prohlizece) [vydání vlastního prohlížeče](https://www.seznam.cz/prohlizec). Zajímavé je, že nejde o _přebarvený_ Chrome/Firefox, ale o _vlastní prohlížeč_. Na české poměry poněkud nezvyklý projekt. Podíváme se, z jakého je těsta a co umí.



![Seznam.cz Prohlížeč](/uploads/2014/12/SnÃ­mek-obrazovky-2014-12-21-v-4.48.31.png) Seznam.cz prohlížeč po spuštění

Prohlížeč je dostupný jak pro desktop Windows/Mac, tak i pro Android a _brzy_ i iOS. Zaměřím se na Mac verzi.

Jádro aplikace je postaveno na [node-webkit](https://github.com/rogerwang/node-webkit) - tudíž se jedná o vykreslovací jádro Blink - de facto shodné s aktuální verzí Google Chrome, což potvrzuje i HTML5 Test. Dobrou zprávou je, že uživatelům budou fungovat všechny moderní vychytávky.

[![HTML5 test - Seznam.cz](/uploads/2014/12/SnÃ­mek-obrazovky-2014-12-21-v-5.38.28-570x386.png)](/uploads/2014/12/SnÃ­mek-obrazovky-2014-12-21-v-5.38.28.png)

Jak vůbec fungují node-webkit aplikace? Mají v zásadě 2 vrstvy:




  1. **Blink** (webkit) jádro, díky kterému máte k dispozici všechny současné možnosti HTML5 (jako např. WebGL, WebSQL, WebRTC…) k vytvoření aplikace. Samozřejmostí je podpora všech JS frameworků. Pracujete s klasickým DOMem, jakoby se jednalo o normální webovou aplikaci.


  2. Integrace s **Node.js**, které se může starat o _nižší_ věci jako integrace se systémem (např. zápis do registrů) nebo práce se soubory aj.


Node-webkit aplikace se skládají z HTML a JS souborů, takže se můžeme podívat jak vypadá inicializační stránka init.html:



[![init.html](/uploads/2014/12/SnÃ­mek-obrazovky-2014-12-21-v-6.20.22.png)](/uploads/2014/12/SnÃ­mek-obrazovky-2014-12-21-v-6.20.22.png)
Zde jsou moduly, které slouží jako globální objekty pro celý proces (historie, nastavení, autoupdate prohlížeče atd.). Lze vidět, že se při startu načítá i několik modulů, které ještě nejsou v současné verzi _(1.0.3)_ jako: synchronizace hesel, načítání favicon, registrace (?). Občas narazíte i na podivné kusy kódu jako:


    {% highlight js %}Favicon.Find.prototype.$constructor = function(data){
        if(data.favicoUrl=="http://www.minorit.com/favicon.ico"){ // wat?
            this.error(data)
        }else{
            // ...
            // generování náhledu favicony
            // ...
        }
    };
    {% endhighlight %}




Zajímavější kód najdeme na stránce nového (aplikačního) okna [win.html](/uploads/2014/12/SnÃ­mek-obrazovky-2014-12-21-v-6.20.36.png). Zaprvé: Seznam prohlížeč nevyužívá UI z node-webkit (které vypadá zkrátka jako defaultní prohlížeč), ale místo toho **implementuje celé uživatelské rozhraní pomocí [AngularJS](https://angularjs.org)** (s rozdílným CSS pro Windows a Mac, aby ovládací prvky odpovídaly platformě).



![Seznam.cz prohlížeč s node-webkit chrome](/uploads/2014/12/seznam-chrome.png)
Jak vidíte, je to vcelku rozsáhlá aplikace. Nechal jsem zdrojové kódy projet nástrojem [Plato](https://github.com/es-analysis/plato) pro analýzu JS kódu a výsledkem (po vynechání knihoven) je 12588 řádků s průměrem 143 řádků na soubor. Projevuje se, že aplikaci nejspíše psalo více týmů, které se neshodly, protože chybí jednotný styl zápisu. Používají se různé typy komentářů - většina funkcí je však úplně nekomentovaná. Občas se používají $constructory, občas ne. Občas se používá [JAK](http://jak.seznam.cz), občas ne. Což se poté projevuje na [JSLint](http://www.jslint.com) chybách. Nejspíše se tlačilo na vydání k určitému datu.

![Plato report](/uploads/2014/12/SnÃ­mek-obrazovky-2014-12-21-v-7.01.04-e1419146497410.png)

Jak jsem říkal, celé UI je vybudováno přes AngularJS, takže máte přístup i k Developer toolbaru (ctrl+shift+j) můžete se podívat, jak vše funguje. Většina ovládacích prvků je řešena přes Angular direktivy, místo UI routeru se používají node-webkit okna.

Samotná okna stránek využívají node-webkit nw.gui.window - což je speciální iframe, který umí několik triků - jako fejkování window.top, ignorování X-FRAME-OPTIONS (takže lze do iframe načítat i stránky, které to obvykle nepovolují) nebo oddělení od node-webkit, aby stránka nemohla přebrat kontrolu nad celou aplikací. Což se hned po vydání úplně nepovedlo. Stačil tento kód:


    {% highlight js %}nwDispatcher.requireNwGui().Window.get().eval(null, "alert(nwDispatcher.requireNwGui().Window.get().window.localStorage.favorites)");{% endhighlight %}


https://twitter.com/jedenbod/status/544679528715804672



Seznam.cz dále vyzdvihuje bezpečnost prohlížeče - což dokazuje tím, že zakázal doplňky _(nikdo snad adblock nečekal)_. Jenže tento prohlížeč je dle mého zatím jeden z nejnebezpečnějších, který si můžete nainstalovat. Část z jeho zranitelnosti vyplývá ze samotné platformy node-webkit. Tak například to, že jednotlivé záložky nejsou sandboxované, takže vám v systému běží jeden proces, ale jakmile ho sestřelíte, například tímto JS kódem na stránce, tak přijdete o všechny záložky.


    {% highlight js %}var a = "a";
    while(1){
        a = a += "a";
    }
    {% endhighlight %}

<video src="/uploads/2014/12/crash-small.mp4" loop="true" autoplay="true" preload="auto"></video>

Například v Chrome, díky sandboxu vás pád jedné neohrozí a ostatní záložky bez problému fungují dále.

[![Chrome Sandbox](/uploads/2014/12/SnÃ­mek-obrazovky-2014-12-21-v-7.57.37-570x391.png)](/uploads/2014/12/SnÃ­mek-obrazovky-2014-12-21-v-7.57.37.png) Chrome Sandbox

<del>Ale tím největším nebezpečím, na které jsem v současné verzi Seznam.cz prohlížeče narazil, je **neomezený přístup k uživatelským datům**. Přes HTML5 API, má stránka přístup k webkameře, mikrofonu atd. Prohlížeč na to nijak neupozorní, ani uživatele nevyzve k potvrzení přístupu.</del>

<del>Takže zatímco ve všech ostatních prohlížečích JavaScript čeká, zdali dostane povolení k přístupu k webkameře, Seznam.cz prohlížeč ho automaticky stránce vydá, aniž by něco řekl. A pokud vás na to neupozorní něco jiného (software webkamery, dioda na stroji), tak to ani nezjistíte.</del>

<del>Takže stránka může na pozadí dělat screenshoty, zatímco si ji čtete. Což tato stránka dělá, pokud si ji čtete v Seznam.cz prohlížeči :)</del>

[Přístup k getUserMedia je podle všeho už opravený](http://jedenbod.cz/1583-seznam-cz-prohlizec.html#comment-82237)

Stejně snadno stránka vydá vaši pozici přes HTML5 geolocation API. Stažení prohlížeče je omezeno pouze na uživatele v České republice - otázkou je, jestli vycestování za hranice zablokuje automatické aktualizace, což by mohlo znamenat ještě další bezpečnostní riziko.

Webkit/Blink jádro samo o sobě uživatele chrání před různými typy útoků - ale implementace v node-webkit některé věci obchází pro snadnější vývoj desktop aplikací. Tak například můžete simulovat click pro jakýkoliv element. [Třeba filepicker s display:none](http://jsfiddle.net/0104bhnc/1/), což je věc, kterou vám žádný jiný prohlížeč nepovolí (z dobrých důvodů). Seznam prohlížeč poslušně otevře dialog pro výběr souborů, aniž by ho uživatel nějak inicializoval. A takovýchto změn je bohužel vcelku dost.

![Seznam.cz prohlížeč - filepicker](/uploads/2014/12/SnÃ­mek-obrazovky-2014-12-21-v-16.24.20-570x360.png)

<del>Verdikt: jedná se o **nebezpečný, nedokončený produkt** a jeho vydání je spíše hrozbou pro uživatele, než zárukou bezpečí a rychlosti. Jeho spásou můžou být rychlé a časté aktualizace, ale Seznam má co dohánět.</del>
