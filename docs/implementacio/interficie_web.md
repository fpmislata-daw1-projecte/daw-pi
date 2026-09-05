---
title: Interfície web
icon: fontawesome/solid/laptop-code
alias: interficie-web
---

# :fontawesome-solid-laptop-code: Interfície web
El client és l'aplicació que utilitzarà l'usuari final. Ha de proporcionar
una __interfície moderna i responsiva__, i comunicar-se amb el servidor
mitjançant l'[[estructura-client-servidor|:material-lan-connect: API REST]].


## Tecnologies
- __:simple-html5: HTML__: estructura el contingut de cada pàgina amb
    etiquetes semàntiques.
- __:simple-css: CSS__: dona estil a la interfície i defineix com
    s'organitzen i s'adapten els elements a la pantalla.
- __:simple-typescript: TypeScript__: implementa la lògica de la interfície
    com la interacció amb l'usuari o consum de l'API.


## Requisits de la interfície
La interfície ha de complir els següents requisits:

- __Prototip__: abans de maquetar, cal dissenyar un __prototip__ (_mockup_) de
    cada pantalla, per a definir quina informació i quines accions ha de
    mostrar.
- __Responsiva__: la interfície s'ha d'adaptar a les mides de
    pantalla de diferents dispositius, com mòbils, tauletes o escriptoris.
- __UI moderna i bones pràctiques__: mantindre una imatge visual coherent
    (colors, tipografies, espaiats), seguir criteris bàsics d'accessibilitat
    i evitar duplicar estils o codi entre pantalles.
- __Animacions__: incorporar transicions i animacions que milloren l'experiència d'usuari, sense abusar-ne.


## Consum de l'API des del client
- __Peticions HTTP__: l'aplicació ha de realitzar peticions HTTP a
    l'API REST del servidor per a obtenir o enviar dades.
- __Tractament de la resposta__: convertir la resposta JSON en objectes de
    TypeScript.
- __Gestió d'errors__: comprovar el codi d'estat HTTP de la resposta i
    mostrar a l'usuari un missatge adequat en cas d'error.
- __Actualització de la interfície__: modificar el DOM per a reflectir les
    dades rebudes del servidor, sense necessitat de recarregar la pàgina.
