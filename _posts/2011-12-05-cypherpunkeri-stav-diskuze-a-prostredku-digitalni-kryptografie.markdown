---
author: JackuB
comments: true
date: 2011-12-05 22:50:36+00:00
layout: post
slug: cypherpunkeri-stav-diskuze-a-prostredku-digitalni-kryptografie
title: 'Cypherpunkeři: Stav diskuze a prostředků digitální kryptografie'
permalink: /1262-:slug.html
categories:
- Bezpečnost
- Internet
- Sociologie
- Úvaha
tags:
- Bezpečnost
- budoucnost
- cypherpunk
- Internet
- Julian Assange
- kryptoanalýza
- NSA
- PGP
- soukromí
- web
---

Na žádost [Bystroushaaka](http://kitakitsune.org/) přidávám seminární práci o cypherpunku.

Pokud ji vážně hodláte číst doporučuji [PDF verzi](/uploads/2011/12/Crypto.pdf) (je hezčí).

Pokud ji _vážně_ budete číst, berte na vědomí,




  * že jsem si vědom chyb a nepřesností (klidně je opravím, pokud na ně ukážete)


  * že jsem práci psal v rámci _de facto_ uměnovědného oboru, nemohl jsem se pouštět do technických detailů - šlo o _představení_ cypherpunku


  * že se můžete vyjádřit nebo doptat na mém [Twitteru](http://twitter.com/jedenbod), [emailu](mailto:jakub@jedenbod.cz)





* * *





##




## Úvod


Milan Kundera ve své knize _Nesmrtelnost_ připomíná, že v křesťanském desateru neexistuje přikázání _„Nezalžeš!“_. Je to velmi zvláštní poznatek, že křesťan nemá povinnost říkat pravdu. Ale je vcelku logický, pokud Bůh stejně všechno ví – a ostatní lidé _nemají právo_ se na nic ptát. Museli by se nejdříve zeptat, aby mohli požadovat pravdu. Kundera dále tuto myšlenku rozpracovává na moderní žurnalismus, ale mě spíše zaujala skutečnost, že lidská společnost nikdy nebyla založena na _nutnosti říkat pravdu_ – vynechme prosím dystopické, utopické a totalitní systémy. A pokud společnost nemá nárok na pravdu, vzniká soukromí – tedy možnost mít tajemství a možnost sdělit tajemství (jen komu uznám za vhodné).

Ochrana soukromí je v nás však mnohem hlouběji než křesťanská nauka. Snad proto odedávna vznikaly technologie, které nás měly chránit pouze fyzicky, ale později sloužily i jako ochrana našeho soukromí a našich tajemství. Skrýše, dveře, zámky, sejfy a šifry – tyto a další technologie nás posunuly až k deklaraci práva na soukromí jako základního lidského práva ((Listina základních práv a svobod: Článek 7 : (1) Nedotknutelnost osoby a jejího soukromí je zaručena.)).

Druhá půlka 20. století přichází s digitálními médii, která nás nutí přehodnotit dosavadní způsoby zajištění a ochrany soukromí. V této práci bych chtěl alespoň z části prozkoumat diskuze o soukromí a jejich aplikace ve věku výpočetní technologie.


##  Stručné dějiny kryptografie a kryptoanalýzy


Jak jsem naznačil v úvodu, historie kryptografie zasahuje hluboko do minulosti, až někam do doby mezi 50 a 100 tisíci lety před naším letopočtem, kdy vzniklo abstraktní myšlení ((Modern human behaviour. In Wikipedia : the free encyclopedia [online]. St. Petersburg (Florida) : Wikipedia Foundation, [cit. 2011-06-26]. Dostupné z WWW: <http://en.wikipedia.org/wiki/Modern_human_behaviour>.)), které nám umožnilo uvažovat o vlastnictví. Něco co je jen vaše – jméno (které určuje váš vztah ke světu), myšlenka, předmět. Z vlastnictví vychází soukromí, tedy možnost jedince nebo skupiny selektivně odhalovat určitá vlastnictví – říct někomu své jméno, podělit se o nápad. Ve chvíli, kdy je tato úvaha možná, přichází čas pro další otázku – jak si své soukromí chránit? Jsou doloženy vaky a měchy pro ochranu osobního vlastnictví. Dalším důkazem jsou hroby a pohřebiště s osobními věcmi, které si zemřelí brali i do posmrtného života ((ELIADE, Marcea. Dějiny náboženského myšlení : Od doby kamenné po eleusinská mystéria. 3. opr. vyd. Praha : OIKOYMENH, 2008. 518 s.)). S domestifikací (okolo roku 10 000 př.n.l) vznikají ohrady, dveře a skrýše ((ELIADE, Dějiny náboženského myšlení)). Později přicházejí zámky, sejfy a bezpečnostní systémy. A kryptografie je pouze rozšíření snah o ochranu soukromí.

Kryptografii jde v zásadě rozdělit na kryptografii klasickou a moderní. Ještě do roku 1949 jsme mohli mluvit o kryptografii klasické – tedy založené na čistě mechanickém principu. Moderní kryptografie pracuje s digitálními daty a bez použití výpočetních strojů je práce s ní téměř nereálná. Klasická kryptografie sahá několik tisíc let do minulosti – použití šifer v Mezopotánii a Egyptě není do dnes příliš jasné, ale od dob Řecka a Říma se můžeme skutečně bavit o kryptografii.


### Klasická kryptografie


Historie šifer je od počátku silně provázaná s armádou. Šifry používali Sparťané ((YOUNG, Gary De. Dr. Gary De Young [online]. X [cit. 2011-06-19]. Spartan Scytale. Dostupné z WWW: <http://courses.gdeyoung.com/pages.php?cdx=168>.)), aby jimi předávali rozkazy a válečné zprávy. Jednalo se o jednoduchou transpoziční šifru, kdy se papír omotaný kolem válečku popsal a po jeho rozložení zůstala pouze řada náhodně vypadajících znaků. Dalším známým příkladem je klasická Caesarova šifra ((Caesar cipher. In Wikipedia : the free encyclopedia [online]. St. Petersburg (Florida) : Wikipedia Foundation, [cit. 2011-06-19]. Dostupné z WWW: <http://en.wikipedia.org/wiki/Caesar_cipher>.)), která je snadno použitelná (i prolomitelná), ale občas se používá dodnes – jde o posun písmene v abecedě, takže z A je B, z B je C atd. Další zájem o kryptografii přichází v 19. století. Není náhoda, že ze stejné doby pochází i Baggageho Difference Engine. Kryptografii se dostává jak systematického zájmu ze strany matematiků tak i pozornosti širší veřejnosti - o kryptografii píše například i Edgar Allan Poe ve své povídce Zlatý brouk ((POE, Edgar Allan. Zlatý brouk. Praha : Argo, 2010. 108 s.)) z roku 1843 (Kryptografie zde hraje klíčovou roli pro rozluštění případu).

Větší zvrat nastává s příchodem druhé světové války. V této době již existovaly mnohé elektromechanické šifrovací systémy, avšak pozornost se věnovala především rozluštění Enigmy, která se používala již od 20. let 20. století. Právě její prolomení a praktické dopady práce kryptoanalytiků v Polsku a britském Bletchley Parku ukázaly na důležitost dobrého šifrování v armádě – nebo alespoň dobré kryptoanalýzy. Během války se toto potvrdilo ještě například v bitvě o Midway, kde prolomení japonské šifry ((Cipher Machines [online]. 2006 [cit. 2011-06-14]. Japanese Purple Cipher. Dostupné z WWW: <http://ciphermachines.com/ciphermachines/purple.html>.))znamenalo rozdíl mezi výhrou nebo porážkou.


### Moderní kryptografie


Od druhé světové války byly na tvorbu šifer (především v USA) vydávány obrovské sumy vládních peněz ((History of cryptography. In Wikipedia : the free encyclopedia [online]. St. Petersburg (Florida) : Wikipedia Foundation, [cit. 2011-06-20]. Dostupné z WWW: <http://en.wikipedia.org/wiki/History_of_cryptography>.)). Do kryptografie investuje především námořnictvo a tajná služba. V roce 1949 vzniká útvar AFSA (Armed Forces Security Agency), předchůdce dnešní National Security Agency (NSA), založené v roce 1952. V roce 1949 se však stala ještě jedna důležitá věc – vyšla kniha Communication Theory of Secrecy Systems ((SHANNON, Claude. Communication Theory of Secrecy Systems. New Jersey : Bell Labs, 1949. 60 s.)). Claude Shannon – „otec informačních technologií“ pracoval během Druhé světové války na projektech spojených s kryptografií a binární logikou. Jeho návrh řešení problémů booleanovy logiky v binárních systémech se stal základem pro práci pozdějších matematiků. Jeho práce je považována za počátek moderní kryptografie. Shannon navrhuje využití informačních technologií ((Je v tomto ohledu důležité si uvědomit v jaké fázi vývoje byly informační systémy v roce 1949)) pro lepší šifrování. Jeho výsledky velmi zaujaly AFSA – a tak se počítalo s tím, že (digitální) šifrování bude primárně armádní záležitostí. A skutečně tomu tak bylo – nejpokročilejší šifrování měla americká NSA a britská GCHQ (Government Communications Headquarters).

![Shh](/uploads/2011/12/0905-shh-dont-tell-sm1.jpg)

Polovina 70. let však přinesla změnu, kterou pociťujeme až dodnes. Nejdříve v roce 1976 vznikl Data Encryption Standard ((SMID, Miles; BRANSTAD, Dennis. The Data Encryption Standard : Past and Future. Proceedings of the IEEE. 1988, s. 43-65.)) – veřejná šifra vyvinutá IBM a propagovaná vládou a Národním institutem standardů a technologie. Bohužel se nikdy ve velkém neuchytila ((Používala se pouze asi do poloviny 80. let)), částečně také ze strachu z backdooru ((Nedokumentovaná cesta, jak napadnout systém. V případě DES byl problém v _podezřelých _code blocích)), který by do ní teoreticky mohla umístit NSA, aby měla přístup k zašifrovaným datům. Důležité bylo, že sama vláda prosazovala standardizovanou šifru pro privátní sektor. Sama vláda chtěla, aby si občané alespoň nějak svá data (jako firemní tajemství atd.) šifrovali.

Druhým, mnohem důležitějším, zvratem byl vynález asymetrické (public key) kryptografie. Whitfield Diffie a Martin Hellman ((Oba byli součastí hackerské komunity na MIT v 60. letech)) přišli se systémem veřejného a soukromého (asymetrického) klíče, který zaručoval bezpečnou komunikaci i když byl komunikační kanál celou dobu konverzace odposloucháván. Co bylo však důležitější, tento systém nevyvinula žádná vladní organizace ((I když Bobby Inman (bývalý ředitel NSA) oznámill, že NSA měla Public Key již v roce 1966 (viz. The Cyphernomicon níže) )), ale lidé z civilního/akademického sektoru. S příchodem RSA ((Algoritmy.net [online]. 2011 [cit. 2011-06-29]. Algoritmus RSA. Dostupné z WWW: <http://www.algoritmy.net/article/4033/RSA>.)) (aplikace asymetrické kryptografie) v roce 1978 měla veřejnost v ruce velmi silný nástroj pro ochranu soukromí. Dokonce tak silný, že jej nedokázaly prolomit ani vládní organizace. Což se samozřejmě vládě nelíbilo, uvalila tedy embargo na vývoz šifrovacích algoritmů delších než 40bitů (což už v roce 1978 byla slabá šifra). Zákaz trval v podstatě až do roku 2000.

V tomto okamžiku je důležité si uvědomit, že v jednu dobu existovaly dva velmi protichůdné názory na použití kryptografie v civilním sektoru: na jedné straně vláda, která by ráda zamezila tomu, aby si kdokoliv mohl cokoliv zašifrovat tak, aby k tomu žádná vládní organizace neměla teoretický přístup. Na druhé straně je nově vznikajicí skupina, která by ráda měla kontrolu nad svým digitálním soukromím. Z druhé skupiny vznikne jakýsi odboj-hnutí:


Cypherpunk





## Cypherpunkeři


Cypherpunkeři byli většinou technicky znalí uživatelé, kteří měli aktivní vztah k matematice a výpočetním technologiím. Možnost aktivně participovat v boji proti policejnímu státu, jak jej ukazuje Orwell, pro ně byla revoluční myšlenkou. Studená válka nevypadala, že by měla skončit a s trochou fantazie se mohla přirovnat k Udržovací válce. Právě tito lidé a právě v takové době zničehonic disponovali nástroji, které jim dovolovaly obranu proti všemožným vládním aktivitám zaměřeným proti jejich soukromí.


> I zákony proti kryptografii sahají pouze tak daleko, kam státní hranice a násilí.
Eric Hughes - Cypherpunk’s manifesto ((HUGHES, Eric. Activism.net [online]. 1993 [cit. 2011-05-29]. A Cypherpunk's Manifesto. Dostupné z WWW: <http://www.activism.net/cypherpunk/manifesto.html>.))


Historii, důležité postavy a souboje cypherpunkerů a vlády popisuje Steven Levy v knize Crypto: How the Code Rebels Beat the Government Saving Privacy in the Digital Age ((LEVY, Steven. Crypto : How the Code Rebels Beat the Government Saving Privacy in the Digital Age. [s.l.] : Penguin, 2002. 368 s. ISBN 978-0140244328.)). Bylo to období skutečné války mezi cypherpunkery a NSA. NSA chránila monopol na kvalitní kryptografii a národní zájmy – cypherpunkeři bojovali spíše za ideály, než za nějaké konkrétní (revoluční) myšlenky. Mnoho prominentních cypherpunkerů skončilo ve vězení ((Například Jim Bell _(autor Assasination politics)_je v něm dodnes)). Cypherpunkeři nikdy nebyli nijak organizovaní a jejich názorové spektrum zasahovalo od krajní levice přes krajní pravici až po anarchismus ((Viz. Crypto-anarchismus jako ideologie postavená na kryptografii.)). Cypherpunkery ze začátku spojoval především zájem o civilní kryptografii, public key a možnosti nasazení kryptografie v reálném životě. Další témata přišla až na konci 80. let a začátku 90. Základní sdílená ideologie cypherpunkerů byla postavena na knihách jako Orwellův 1984, The Shockwave Rider, True Names ((Ačkoliv jsou na kvalitu Vingeho povídky různé názory, na cypherpunkery zapůsobila velmi podmanivě. Což lze doložit na častém odkazování k textu v cypherpunkových textech. To, že si musíme chránit naše Pravé jméno je to, co cypherpunkery velmi vystihuje.)), Ender's Game, Snowcrash, The Cryptonomicon nebo The Puzzle Palace. A samozřejmě odborná literatura o kryptografii a matematice a velké množství čistě cyberpunkových textů.

Avšak na důležitosti cypherpunkeři skutečně získali až v roce 1992. Vznikl totiž Cypherpunk mailing list. Mailing list ((Mimochodem: dodnes funkční. Je to jeden z nejdéle funkčních mailing listů - cypherpunks@al-qaeda.net mailing list původně vznikl pod doménou toad.com – ano, web Johna Gilmora)), který svými tématy o několik let předběhl dobu. Vznikl v San Franciscu z iniciativy Erica Hughese ((Matematik z Berkeley a autor A cypherpunk’s manifesto)), Timothy C. Maye ((Matematik, výzkumník Intelu, autor The Cyphermoniconu, The crypto anarchist’s manifesto a True Nyms and Crypto Anarchy. Výčet jeho důležitých textů by však byl mnohem delší.)) a Johna Gillmora ((Zakladatel Electronic Frontier Foundation, výzkumník u Sun Microsystems a známý aktivista.)). Všichni 3 byli finačně zajištění a úspěšni ve svých oborech. Založili si malý diskuzní kroužek, který se scházel jednou měsíčně v kanceláři Johna Gilmora. Z těchto mítinků pochází i označení Cypherpunk ((Název je samozřejmě odvozen od populárního žánru: cyberpunk.)), který vymyslela Jude Milhon ((V hackerské komunitě známá také jako _St. Jude_. Editor časopisu Mondo 2000 (který zakládala) )). Brzy po prvním setkání vznikl Mailing list. Diskuze cypherpunkerů se stále točily kolem posledního vývoje v oblasti techniky, tím se nelišily od jiných technicky zaměřených mailing listů, rozdíl byl v přítomnosti diskuze o ochraně soukromí v digitální době, o nebezpečí policejního státu a o změnách, které mohou přijít. Přispěvatelé mailing listu ((http://www.cypherspace.org/adam/cp-stats.txt - seznam přispěvatelů mailing listu (nepodařilo se mi přímo zjistit data záznamu). Seznam obsahuje mnoho zajímavých jmen – Bruce Schneier, David Wagner, Adam Shostack, Steven Bellovin a samozřejmě i Julian Assange. Na listu lze najít i několik českých (ne však příliš důležitých) jmen.)) byli především odborníci, od čehož se odvíjela i úroveň diskuze.

Jak poznamenal Will Rodger:


> „Byla to směs revoluční politiky a pokročilé matematiky“
- Will Rodger ((RODGER, Will. SecurityFocus [online]. 2001 [cit. 2011-06-21]. R.I.P. Cypherpunks. Dostupné z WWW:.))


Mezi archaickými cypherpunkery existovaly v podstatě 2 možnosti, jak bude vypadat budoucnost ((MANNE, Robert. Cryptome [online]. 2011 [cit. 2011-06-14]. The Cypherpunk Revolutionary Julian Assange. Dostupné z WWW: <http://cryptome.org/0003/assange-manne.htm>.)):




  1. Stát pomocí digitálních technologií a neustálého sledování zničí osobní svobodu a soukromí.


  2. Nebo stát bude zničen (nebo alespoň minimalizován) za pomoci digitálních technologií jako kryptografie.


Ale témata se dotýkala i využití a zneužití technologií nebo úloha techniky pro běžného člověka. Nekompletní archiv mailing listu je stále k dohledání ((Mailing list ARChives [online]. 2001 [cit. 2011-06-21]. Dostupné z WWW: <http://marc.info/?l=cypherpunks>.)). Dodnes obsahuje zajímavé podněty. Zajímavý je i pohled na počet odběratelů, který už v roce 1994 dosáhl 700 lidí a v roce 1997 (vrchol) až 2000 čtenářů. Pokud uvážíme, jaká byla penetrace inernetovým připojením mezi obyvatelstvem (až od roku 1997 se jednalo o 11% populace 1. světa) ((Internet users per 100 inhabitants 1997-2007 ITU.png. In Wikipedia : the free encyclopedia [online]. St. Petersburg (Florida) : Wikipedia Foundation, [cit. 2011-06-29]. Dostupné z WWW: <http://cs.wikipedia.org/wiki/Soubor:Internet_users_per_100_inhabitants_1997-2007_ITU.png>.)) a odbornost diskuze, jsou to čísla ukazující na opravdový zájem o tuto tématiku.

Kolem cypherpunku vzniklo několik velmi důležitých textů: předně The Cyphernomicon ((MIT Project on Mathematics and Computation [online]. 1994 [cit. 2011-06-10]. The Cyphernomicon. Dostupné z WWW: <http://groups.csail.mit.edu/mac/classes/6.805/articles/crypto/cypherpunks/cyphernomicon/CP-FAQ>.)) – cypherpunkerský FAQ z roku 1994 o cypherpunku, cryptoanarchii a soukromí. Je to velmi obsáhlý a místy nepřehledný ((Přece jen, je to cypher_punkový_text)) dokument, který dává i po více než 15 letech možnost lépe se vcítit do jejich uvažování, kdy nikdo s nikým v podstatě nesouhlasí ((Mailing obsahoval z nemalé části i osobní útoky, hádky apod. – nutno říct, že si ale stejně udržovaly určitou úroveň)), ale všichni vědí, že přece jen sdílí určité ideály. Vcelku trefně poukazuje na cypherpunkery jako skupinu počítačových punkerů. The Cyphernomicon dále vysvětluje motivace pro vznik mailing listu atd. Obsahuje také rady ohledně kryptografie a etikety mailing listu.

A Cypherpunk's Manifesto také přináší několik zajímavých názorů:


> Soukromí v otevřené společenosti vyžaduje kryptografii. Pokud něco řeknu, chci, aby to slyšeli jen ti, jimž je to určeno.
Eric Hughes - Cypherpunk’s manifesto


Cypherpunkeři skutečně dlouhou dobu věřili v rychlé vítězství individuálního nad státním. Podporovalo je v tom zjištění, že public-key je největší vynález v oblasti kryptografie od renesance. A vznik PGP na počátku 90. let, který měl přiblížit kryptografii masám, je dále podporoval v jejich snažení. Stejně tak se často ve svých textech oháněli až romantickými představami o korporacích, policejních státech apod. Z cypherpunku lze často cítit aktivistická rétorika 90. let. Naštěstí se nedrží jen té, ale posunují diskuzi konstruktivnějším směrem.


> Cypherpunkeři píší kód. Víme, že někdo musí psát software na ochranu soukromí. A nebudeme mít soukromí, dokud to nebudeme dělat všichni, a proto ho budeme psát.
Eric Hughes - Cypherpunk’s manifesto


_„Cypherpunks write code“_se stalo jakýmsi heslem cypherpunkerů. Další důležitý text vycházející z cypherpunkerské ideologie je Assassination politics ((BELL, Jim. Outpost of Freedom [online]. 1997 [cit. 2011-06-14]. Assassination Politics. Dostupné z WWW: <http://www.outpost-of-freedom.com/jimbellap.htm>.)). Assassination politics Jima Bella je zajímavý myšlenkový experiment, který počítá se vznikem anonymního ((S použitím anonymních platebních metod, aby nebylo možno vystopovat účastníky)) _Dead Poolu_ ((Seznam lidí, u kterých „tipujete“ kdy zemřou. Správné uhádnutí se rovná výhře.)), který nám v konečném důsledku má přinést otevřenou společnost, minimální stát apod. Zajímavostí je, že vznikl také pornofilm, který vyšel v malém nákladu a pro cypherpunkery – Cryptic seduction ((Mail-archive.com [online]. 2000 [cit. 2011-05-30]. CRYPTIC SEDUCTION -- CYPHERPUNK SPECIAL. Dostupné z WWW: <http://www.mail-archive.com/cypherpunks@algebra.com/msg04068.html>.)). Podle popisu je rozdíl mezi klasickým porno filmem a krypto porno filmem například v několika odkazech k backdoorům ((ORLOWSKI, Andrew. The Register [online]. 2002 [cit. 2011-05-30]. Alice, Bob and Eve too. Dostupné z WWW: <http://www.theregister.co.uk/2002/03/16/alice_bob_and_eve/>.)).

![WIRED - Crypto Rebels](/uploads/2011/12/Image-570x427.jpg)

Důležitým bodem byl také článek Crypto Rebels ((LEVY, Steven. Crypto Rebels. Wired 1.02. 1993, 1, 2. Dostupný také z WWW: <http://www.wired.com/wired/archive/1.02/crypto.rebels_pr.html>.)) v tehdy začínajícím časopisu Wired – který cypherpunkerům přinesl větší podporu veřejnosti. Je to obsáhlý článek osvětlující důvody a způsob jejich vzniku. Obsahuje také vyjádření NSA k cypherpunkerům, informace o zatčení Johna Gillmora nebo zamyšlení nad budoucností cypherpunkerů v době přicházejících mobilních telefonů.




## Současný cypherpunk


Cypherpunk nezanikl. Mailing list je stále aktivní a vzhledem k tomu, jaká je základna jeho přispěvatelů a fakt, že je moderovaný, udržuje si určitou úroveň. Od konce 90. let se termín přestal používat, ale jejich myšlenky přetrvaly. Objevovaly se nové projekty, koncepty a postupy při využívání kryptografie ((Zajímavý je například Assangeho systém Marutukku - Rubberhose (file system). In Wikipedia : the free encyclopedia [online]. St. Petersburg (Florida) : Wikipedia Foundation, [cit. 2011-06-15]. Dostupné z WWW: <http://en.wikipedia.org/wiki/Rubberhose_(file_system)>.)). Co se primárně změnilo?




  1. Rozšířenost internetu (trochu paradoxně) vedla k tomu, že nemůže vzniknout centralizovaná diskuze o kryptografii:



    * a. buď bude skupina příliš malá, než aby měla nějaký hmatatelný efekt na globální diskuzi nebo snad i smýšlení.


    * b. nebo je tak velká, že se diskuze rozpadá a ztrácí koncentraci na jedno (i když rozsáhlé) téma.



  2. Téma šifrování mimo-internet se přesunulo do pozadí ((Nemyslím šifrování v _meatspace_, ale šifrování pevných disků apod. zařízení, která nejsou online)). Může za to především kvalita dnes dostupných nástrojů pro šifrování ((Za mnohými z nich stáli právě cypherpunkeři)). Například svobodný software TrueCrypt je při správném použití v dnešní době neprolomitelný (neexistuje ani teoretická možnost prolomitelnosti šifry AES – navíc TrueCrypt umožňuje kombinovat více vrstev obrany)


  3. Diskuze se také přenesla od policejního státu, který občany fyzicky kontroluje v jejich domech apod. k policejnímu/korporátnímu kyberprostoru – každý pokus o monitorování internetu přináší protesty a petice ((Jak se mimochodem nedávno stalo i v ČR)).


  4. Poslední změnou je zjednodušení a zlevnění kryptografie. Jestliže v 90. letech byla kryptografie doménou armády, tajných služeb, matematiků a počítačových odborníků – dnes je šifrování přístupné i pro méně zasvěcené. A právě toto byl jeden z cílů cypherpunků – vytrhnout kryptografii vládě a dát ji uživatelům, aby se mohli bránit před kontrolou, opresemi nebo nátlakem. Kryptografie může být dnes velmi levná - pokročilý software jako TrueCrypt ((TrueCrypt [online]. 2011 [cit. 2011-06-10]. TrueCrypt. Dostupné z WWW: <http://www.truecrypt.org/>.)) je zdarma. Další šifrovací software je zdarma dostupný například pro OS Linux, který je také zdarma. I cena potřebného hardwaru klesla. Pro rychlou a bezpečnou práci se zašifrovanými soubory stačí i podprůměrný hardware. To samé platí i pro software, který nás má chránit na internetu – např. Vidalia ((Tor Project [online]. 2011 [cit. 2011-06-09]. Vidalia. Dostupné z WWW: <https://www.torproject.org/projects/vidalia.html.en>.)) (Tor + Privoxy + Firefox) nebo I2P ((I2P [online]. 2011 [cit. 2011-06-10]. I2P Anonymous Network. Dostupné z WWW: <http://www.i2p2.de/>.)).




### Cypherpunkeři v kyberprostoru


Prvně je nutné si uvědomit, před kým se vlastně máme v kyberprostoru bránit šifrováním. (1) Vlády, které cenzurují přístup k internetu ((Internet censorship by country. In Wikipedia : the free encyclopedia [online]. St. Petersburg (Florida) : Wikipedia Foundation, [cit. 2011-06-21]. Dostupné z WWW: <http://en.wikipedia.org/wiki/Internet_censorship_by_country>.)). Každou chvíli se objeví návrh na sledování uživatelů, omezení přístupu k nebezpečným webům. Ať už se tak děje kvůli válce proti terorismu, pedofilům nebo jen kvůli zdanění internetových kasin (to se netýká jen ČR, podobné návrhy zaznívají i v USA, UK, Německu atd.) (2) Bezpečnostní složky, které chtějí vědět, co děláte.


> Pokud vážně chceš posílat všechny své zprávy nezašifrované a skrz veřejné kanály, dobře. Ale nestěžuj si prosím, až zjistíš, že já (nebo kdokoliv jiný) si je čteme.
- MrKite ((Tachyon [online]. 2006 [cit. 2011-06-26]. [cspace-users] Re: Cspace. Dostupné z WWW:.))


Mezi cypherpunkery platí, že pokud je komunikace nazašifrovaná, někdo cizí ji čte. Je to čistý racionální předpoklad, který počítá s tím, že číst nezašifrovanou komunikaci je velmi jednoduché (což skutečně je). A právě vlády mají zdroje monitorovat i velké objemy komunikace. Nebo si rovnou mohou zajistit přístup k vašim online službám ((ICAZA, Miguel de. Miguel de Icaza [online]. 2011 [cit. 2011-06-23]. Dropbox Lack of Security. Dostupné z WWW: <http://tirania.org/blog/archive/2011/Apr-19.html>.)). Samozřejmě to platí analogicky i pro nebezpečí v podobě black hat hackerů, malwarů apod.

Jak se tedy dnes aplikují cypherpunkerské postupy? Co hmatatelného nám poskytl cypherpunk? Předně vznikly projekty jako TrueCrypt nebo Tor.


### Tor


Tor je anonymní síť založená na technologii Onion Routingu ((Onion routing. In Wikipedia : the free encyclopedia [online]. St. Petersburg (Florida) : Wikipedia Foundation, [cit. 2011-06-28]. Dostupné z WWW: <http://en.wikipedia.org/wiki/Onion_routing>.)). Její důležitost spočívá především




  * v (relativně) nízké odezvě, díky čemuž se dá použít i k anonymnímu používání aplikací


  * ve schopnosti spolupracovat v podstatě se všemi aplikacemi na všech důležitých operačních systémech


  * v jednoduchém a rychlém nastavení. Doslova během několika minut můžete obejít vládní cenzuru nebo pomoct jiným uživatelům obejít cenzuru


  * v ceně – je zdarma.


Tor dovoluje komunikaci jak pouze v rámci Tor sítě (chová se v tomto ohledu jako _darknet_ ((Zvenčí nepřístupná síť)) ), ale i anonymní komunikaci na klasickém internetu.


#### Uvnitř Tor sítě


V Tor síti se nacházejí tzv. Hidden services, což jsou technicky vzato klasické webové servery, pouze s přidanou vrstvou anonymity. Komunikace sama v rámci Tor sítě je anonymnější a teoreticky nelze sledovat ((Existují pouze modely sledování založené na statistických modelech sledování provozu a jeho rozložení. Stále se zkoumají.)).

Nabídka takových služeb je vcelku široká. Knihovny, nabízející knihy od klasických až po návody na sestrojení výbušnin. Diskuzní fóra a stránky aktivistů, kteří mají strach z perzekuce. Občas lze najít i diskuzní fóra disidentských skupin. Odbornější technické diskuze nejsou přístupné bez pozvánky ((Vzhledem k tvaru odkazů v Tor síti (např. The Hidden Wiki - http://kpvz7ki2v5agwt35.onion) je nepravděpodobné, že by někdo zvenčí náhodně objevil funkční web.)) – obvykle pozvánka znamená URL adresa. Vnitřní Tor síť je totiž v podstatě čistý hypertext, kdy se bez odkazu k dalšímu zdroji nikam nedostanete ((Existovaly pokusy zavést vyhledávací engine v Onionlandu (označení pro darknetovou složku Tor sítě), ale ty vždy zkrachovaly a k dnešnímu dni nefunguje ani jeden.)). Při prvním příchodu na Tor vidíte jen stránky, které se implicitně zviditelňují ((Na rozdíl od internetu, kde nejdou vidět ty weby, které se skrývají. Stránky, které se propagují, jsou často s pornografickým obsahem, proto mnoho lidí po příchodu do Onionlandu nabývá dojem, že Tor je jen síť pro sdílení (pedofilní) pornografie)). Takže získávání informací dostává, paradoxně k tomu, že je to anonymní síť, více lidský rozměr, kdy se často musíte zeptat někoho a ne mechanického vyhledávače. Vnitřní Tor síť je tedy výborným místem pro různé niché-skupiny, které si nepřejí být rušeny a pro které je anonymita jen další plus. O jaké skupiny se jedná? Často to jsou pedofilové a jejich uzavřené komunity. Dále určité množství webů v neevropských jazycích – což zahrnuje informační body několika teroristických organizací ((Na Tor fóru talk.masked se nějakou dobu diskutovalo o pravosti těchto webů – samozřejmě se ukázalo, že je nemožné to potvrdit nebo vyvrátit)), politické aktivisty a fóra s neznámým obsahem. V Onionlandu mají zastoupení také 2 české projekty: PirateLeaks.cz ((http://qyy2n2lqpc5l524q.onion:8080/)) a KinderPorno.cz ((http://n4k727nqnwkvb4g6.onion/d/)).

Podle několika zdrojů, které provedly analýzu provozu na Toru, je však většina provozu směřována ven ze sítě do normálního internetu. Jde tedy vidět, že většině uživatelů stačí normální internet, jen ho chtějí používat anonymně. Lepší odhady by však vyžadovaly výzkum Tor a I2P sítě v takovém rozsahu, v jakém doposud nebyly provedeny.


## Co přinesl cypherpunk?


Jak stručně zhodnotit uplynulých 20 let cypherpunku?

Cypherpunkerům se rozhodně povedlo, alespoň částečně, zvrátit tlak NSA (i jiných vládních agentur) o omezení kryptografických nástrojů dostupných pro veřejnost ((Dnešní šifry nemají vládní backdoory, ani není limitované jejich použití nebo vývoz.)). Nezanedbatelný je také jejich přínos v ohledu ochrany soukromí na webu. Dalším podstatným důsledkem je tvorba ideového základu pro práce jako Assasination politics nebo WikiLeaks. Bez cypherpunkerů by nevznikla tato nová vlna digitálních revolucionářů, jako je Julian Assange.


![](/uploads/2011/12/assange.png)


Nesmíme zapomínat také na to, že heslo cypherpunkerů bylo: „We write code“ – a tak také činili. Cypherpunk nebyl pouze myšlenkovým experimentem nebo kecacím pláckem. Během let vzniklo mnoho projektů, od malých a zaměřených přímo na odbornou komunitu ((Jako různé druhy pokročilých anonymních remailerů)), až po velmi praktické projekty s obrovským dopadem. Kupříkladu PGP ((Pretty good privacy – velmi populární program pro použití asymetrických klíčů – sice vyvinutý už na počátku 90. let, ale s myšlením blízkým cypherpunkerům.)), Tor a v poslední době BitCoin ((Systém anonymní měny – podobné, jakou popisoval Jim Bell ve své Assasination politics)).

Budoucnost cypherpunku?

Poslání cypherpunkerů nekončí. Technologicky je čeká hledání náhrady za public-key kryptografii například na poli kvantové matematiky. Ale hlavně je čeká boj se snahami o okleštění internetu. Boj o zavedení kryptografie jako něčeho běžného, co bude součástí softwaru. Je možné, že nás čeká boj o kyberprostor – Timothy C. May se v tomto smyslu vyjádřil ((MAY, Timothy C. Mail-Archive.org [online]. 2001 [cit. 2011-06-14]. Why I'm Not Writing Impassioned Essays in Defense of Crypto and Privacy. Dostupné z WWW: <http://www.mail-archive.com/cypherpunks@minder.net/msg08217.html>.)).

Je možné, že s příchodem cloud-computingu, kdy se naše data přesunou někam do mraků (lépe řečeno na něčí mrak) budeme opět potřebovat lidi jako cypherpunkery. O naše soukromí bude stále zájem.




