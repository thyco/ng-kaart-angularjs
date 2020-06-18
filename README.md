## Starten

npm install, dan npm start. Start op poort 8001

### Probleem

De kaart component werkt enkel wanneer de kaart is gebruikt op de index pagina.
Ik heb de kaart op 2 plaatsen geinclude. Een keer in index.html en 1 keer in view1.html.

De kaart op index.html wordt getoond, voor de kaart in view1.html wordt er een fout gegooid in de ng-kaart-webcomponent.js (te zien in chrome console).

<pre>
<code>
Uncaught Error: StaticInjectorError(Z0)[iN]: 
  StaticInjectorError(Platform: core)[iN]: 
    NullInjectorError: No provider for iN!
    at pi.get (ng-kaart-webcomponent.js:3)
    at ng-kaart-webcomponent.js:3
    at e (ng-kaart-webcomponent.js:3)
    at Si.get (ng-kaart-webcomponent.js:3)
    at ng-kaart-webcomponent.js:3
    at e (ng-kaart-webcomponent.js:3)
    at Si.get (ng-kaart-webcomponent.js:3)
    at Fm (ng-kaart-webcomponent.js:3)
    at sg.get (ng-kaart-webcomponent.js:3)
    at Object.Sg [as resolveDep] (ng-kaart-webcomponent.js:3)
</code>
</pre>

Ik heb ook geprobeerd om de applicatie te runnen met een not minified versie van ng-kaart-webcomponent.js en dan is het duidelijk dat er in deze case een issue is met vinden van de KaartClassicComponent.

<pre>
<code>
Uncaught Error: StaticInjectorError(AppModule)[KaartClassicComponent]: 
  StaticInjectorError(Platform: core)[KaartClassicComponent]: 
    NullInjectorError: No provider for KaartClassicComponent!
    at NullInjector.get (ng-kaart-webcomponent.js:38309)
    at resolveToken (ng-kaart-webcomponent.js:38628)
    at tryResolveToken (ng-kaart-webcomponent.js:38559)
    at StaticInjector.get (ng-kaart-webcomponent.js:38420)
    at resolveToken (ng-kaart-webcomponent.js:38628)
    at tryResolveToken (ng-kaart-webcomponent.js:38559)
    at StaticInjector.get (ng-kaart-webcomponent.js:38420)
    at resolveNgModuleDep (ng-kaart-webcomponent.js:58730)
    at NgModuleRef_.get (ng-kaart-webcomponent.js:59814)
    at Object.resolveDep (ng-kaart-webcomponent.js:60312)
</code>
</pre>

