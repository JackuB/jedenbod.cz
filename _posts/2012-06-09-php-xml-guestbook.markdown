---
published: false
author: JackuB
comments: true
date: 2012-06-09 14:51:33+00:00
layout: post
published: false
slug: php-xml-guestbook
title: PHP / XML Guestbook
permalink: /1464-:slug.html
categories:
- Software
tags:
- databáze
- Guestbook
- návštěvní kniha
- PHP
- responsive
- XML
- XSS
---

Nedávno jsem vytvořil malý guestbook fungující bez databáze - pouze s pomocí XML a PHP. Možná se někomu může hodit.
**Celý kód je na GitHubu - [PHP/XML Guestbook](https://github.com/JackuB/PHP-XML-Guestbook)**


## Zpracování XML -> PHP


Nejdůležitější funkce je: `[simplexml_load_file](http://php.net/manual/en/function.simplexml-load-file.php)` která ze souboru _comments.xml_ načte komentáře. Zbytek je už jen zpracování a výpis pole. Stránkování je matematika pro ZŠ.


## Co Guestbook umí






  * Nastavitelné stránkování


  * Gravatary


  * Ochrana před XSS


  * Zachování zalomení řádků - (funkce `[nl2br](http://php.net/manual/en/function.nl2br.php)`)


  * Základní layout je responsivní


K nahlédnutí je na **[http://jedenbod.cz/gb/](http://jedenbod.cz/gb/)**



[![PHP / XML Guestbook bez databáze](/uploads/2012/06/guestbook-570x373.png)](http://jedenbod.cz/gb/)
