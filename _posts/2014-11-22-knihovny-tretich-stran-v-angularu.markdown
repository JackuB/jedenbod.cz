---
author: JackuB
comments: true
date: 2014-11-22 19:31:34+00:00
layout: post
slug: knihovny-tretich-stran-v-angularu
title: Knihovny třetích stran v Angularu
permalink: /1703-:slug.html
categories:
- JavaScript
tags:
- AngularJS
- HTML5
- javascript
---

Při stavění [Click and Study](http://clickandstudy.com) s [Digital Wizards](https://www.dwgroup.cz) jsem narazil na to, že moje Angular aplikace závisela na hned několika knihovnách 3. strany. Firebase, Facebook SDK, Keen.io, Recurly atd.

Žádná z nich není nutná pro start aplikace, takže nemá smysl je přidávat hned na začátku nebo je mít součástí build procesu. Angular takovou funkci defaultně nemá, takže si musíme vytvořit vlastní službu.


## Minimální řešení


Vždycky rád začínám s minimálním řešením/mockem, abych vůbec věděl, jak ho budu používat.

Každou knihovnu budeme chtít načíst pouze jednou, což zajistíme tím, že budeme kontrolovat, jestli už je v okně zaregistrován její globální objekt, načež spustíme callback. Nevyužívám [$document](https://docs.angularjs.org/api/ng/service/$document), protože neumí createElement a volání přes [angular.element](https://docs.angularjs.org/api/ng/function/angular.element) se mi moc nelíbil.


    {% highlight js %}/**
     * Load JavaScript file, if his global name isn't registered already
     * @param  {string}   scriptUrl   URL to JS file
     * @param  {string}   nameToCheck Name that should be checked in global scope
     * @param  {Function} callback    Callback function on success
     */
    app.service("loadJS", function($window) {
    	return function(scriptUrl, nameToCheck, callback) {
    		if(typeof $window[nameToCheck] !== "undefined") {
    			return callback();
    		}

    		var script = document.createElement("script");
    		script.src = scriptUrl;
    		script.onload = callback;
    		document.head.appendChild(script);
    	};
    });
    {% endhighlight %}


Použití je potom přímočaré:


    {% highlight js %}loadJS("//cdn.firebase.com/js/client/1.0.21/firebase.js", "Firebase", loadNotifications);
    {% endhighlight %}


Jenže, pro takovéto asynchronní operace se více hodí promise a Angular služba $q.


## Řešení s $q


Předělání na [promise](https://docs.angularjs.org/api/ng/service/$q) je jednoduchá záležitost. Navíc získáme jednodušší error handling a možnost navazovat další větve s konstruktem .then(). Takže je například jednodušší načíst knihovnu, inicializovat a až potom použít.


    {% highlight js %}/**
     * Load JavaScript file, if his global name isn't registered already
     * @param  {string}   scriptUrl   URL to JS file
     * @param  {string}   nameToCheck Name that should be checked in global scope
     * @return {promise}              Promise
     */
    app.service("loadJS", function($q, $window, $log) {
    	return function(scriptUrl, nameToCheck) {
    		var deferred = $q.defer();

    		if(typeof $window[nameToCheck] !== "undefined") {
    			deferred.resolve();
    		}

    		var script = document.createElement("script");
    		script.src = scriptUrl;
    		script.onload = function() {
    			deferred.resolve();
    		};
    		script.onerror = function(e) {
    			$log.warn("Failed to load script: " + e.target.attributes[0].value);
    			deferred.reject(e);
    		}
    		document.head.appendChild(script);

    		return deferred.promise;
    	};
    });
    {% endhighlight %}


Což nám umožní knihovny volat takto:


    {% highlight js %}loadJS("//cdn.firebase.com/js/client/1.0.21/firebase.js", "Firebase")
    	.then(setupFirebase)
    	.then(loadNotifications)
    	.catch(function(e) {
    		console.warn("Failed to load script: " + e.target.attributes[0].value);
    	});
    {% endhighlight %}




## Unit test


Jasmine test pro $q je také _skoro_ přímočará záležitost. Stačí si jen dát pozor na to, že Angular dělá resolve při `$rootScope.$apply();` a že zaregistrování `onerror` chyby potřebuje obalit vyhodnocení do `setTimeout()`


    {% highlight js %}describe('loadJS service', function () {
        var $scope,
            loadJS,
            $window,
            handler,
            controller;

        beforeEach(function () {
            module('app');

            inject(function(_$q_, $rootScope, _$window_, $controller, _loadJS_) {
                handler = {
                    thenPromise: function() {},
                    catchPromise: function() {}
                };
                loadJS = _loadJS_;
                $window = _$window_;
                $scope = $rootScope.$new();
                controller = $controller('mainController', {
                    '$scope': $scope
                });
            });
        });

        it('Service loaded', function () {
            expect(loadJS).toBeDefined();
        });

        it("Reject promise", function(done) {
            spyOn(handler, "catchPromise");
            loadJS("xxx", "TEST") // this should throw onerror call
                .catch(handler.catchPromise);
            setTimeout(function() { // let's wait for deferred call, so code coverage is happy
                $scope.$root.$apply();
                expect(handler.catchPromise).toHaveBeenCalled();
                done();
            });
        });

        it("Resolve promise", function() {
            spyOn(handler, "thenPromise");
            $window.TEST = true;
            loadJS("http://example.com/script.js", "TEST")
                .then(handler.thenPromise);
            $scope.$root.$apply();
            expect(handler.thenPromise).toHaveBeenCalled();
        });
    });
    {% endhighlight %}


Tento test také zajistí 100% code coverage v [Istanbulu](http://gotwarlost.github.io/istanbul/).



![AngularJS - loadJS code coverage](/uploads/2014/12/SnÃ­mek-obrazovky-2014-12-21-v-23.57.02.png)
