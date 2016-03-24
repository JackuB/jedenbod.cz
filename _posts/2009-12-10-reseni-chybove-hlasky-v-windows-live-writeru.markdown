---
author: JackuB
comments: true
date: 2009-12-10 09:06:00+00:00
excerpt: <p>O <a href="http://jedenbod.cz/709-windows-live-writer-a-wordpress.html">Windows
  Live Writeru</a> jsem psal již dříve, od té doby jej používám, ale narazil jsem
  na problém při nahrávání většího obrázku. Řešení pomocí FTP přístupu.</p>
layout: post
slug: reseni-chybove-hlasky-v-windows-live-writeru
title: Řešení chybové hlášky v Windows Live Writeru
permalink: /794-:slug.html
categories:
- Internet
- Software
tags:
- FTP
- PHP
- Windows Live Writer
- Wordpress
---

O [Windows Live Writeru](http://jedenbod.cz/709-windows-live-writer-a-wordpress.html) jsem psal již dříve, od té doby jej používám, ale narazil jsem na problém, u článku s [receptem na chilli krůtu](http://jedenbod.cz/786-chilli-kruta.html), jsem měl několik větších obrázků a při publikaci mi Live Writer vrátil chybovou hlášku:


> Odpověď na metodu metaWeblog.newMediaObject přijatá ze serveru blogu byla neplatná:
>
> Invalid response document returned from XmlRpc server


## Řešení



V hlavním okně Windows Live Writeru zvolte **Nástroje –> Účty**. Otevře se vám následující okno:



![Možnosti Writeru](/uploads/livewriter/eenchybovhlkyvWindowsLiveWriteru_133B6/01.png)



Zde si vyberte svůj blog a zvolte **Upravit**.



![Konfigurace](/uploads/livewriter/eenchybovhlkyvWindowsLiveWriteru_133B6/02.png)



V dalším okně vyberte záložku **Obrázky** a **Odeslat obrázky na server FTP**.



![Nastavení FTP](/uploads/livewriter/eenchybovhlkyvWindowsLiveWriteru_133B6/03.png)



Zde již pouze zadáte přihlašovací údaje na svůj server a zvolíte složku, kam se budou obrázky ukládat _(klidně může být mimo instalaci Wordpressu)_.



Potvrdíte a obrázky se budou nahrávat bez problémů.



_Inspirováno z [troublefixers.com](http://www.troublefixers.com/solved-live-writer-error-the-response-to-the-metaweblog-newmediaobject-method-received-from-the-weblog-server-was-invalid-invalid-response-document-returned-from-xmlrpc-server/#comment-4879)._
