---
title: Estructura client-servidor
icon: material/lan-connect
alias: estructura-client-servidor
---

# :material-lan-connect: Estructura client-servidor
Hui en dia, la majoria de les aplicacions informàtiques es dissenyen amb una
__estructura client-servidor__, on el __client és la interfície que utilitza
l'usuari__ (navegador web, aplicació mòbil, etc.) i el __servidor és
l'aplicació que processa les peticions, gestiona la lògica de negoci i
retorna les dades necessàries__.

Com que els clients poden ser molt diversos, el servidor s'organitza
mitjançant una __API REST__. Aquesta és una capa d'intermediació estàndard
que permet la comunicació independentment de la tecnologia utilitzada en el
client. El funcionament és el següent:

- __Peticions HTTP__: el client envia sol·licituds (utilitzant mètodes com
    `GET`, `POST`, `PUT` o `DELETE`).
- __Processament__: el servidor rep la petició, valida l'accés i executa
    l'acció corresponent.
- __Resposta JSON__: el servidor retorna una resposta HTTP que inclou un
    codi d'estat (com `200 OK` o `404 Not Found`) i la informació
    sol·licitada, normalment en format JSON, per la seua lleugeresa i
    facilitat de lectura.

![Estructura d'una aplicació client-servidor](img/api.light.png#only-light)
![Estructura d'una aplicació client-servidor](img/api.dark.png#only-dark)
/// figure-caption : Estructura d'una aplicació client-servidor.

## En aquest projecte
En aquest projecte, el client i el servidor es desenvoluparan per separat,
cadascun amb les seues pròpies tecnologies:

- __:material-monitor: Client__: aplicació web feta amb __:simple-html5: HTML__,
    __:simple-css: CSS__ i __:simple-typescript: TypeScript__.

    Responsabilitats:

    - Mostrar la interfície d'usuari.
    - Recollir les dades introduïdes per l'usuari i validar-les.
    - Enviar peticions HTTP a l'API REST del servidor i tractar-ne la resposta.
    - Actualitzar la interfície amb les dades rebudes del servidor.

    Podeu consultar com s'organitza el codi del client a la
    [[interficie-web|:fontawesome-solid-laptop-code: Interfície web]].

- __:material-server: Servidor__: API REST feta amb __:simple-spring: Spring__.

    Responsabilitats:

    - Exposar els _endpoints_ de l'API REST.
    - Aplicar la lògica de negoci del projecte.
    - Gestionar l'accés a la [[bd|:material-database: base de dades]].
    - Retornar les dades en format JSON.

    Podeu consultar com s'organitza el codi del servidor a
    l'[[arquitectura|:material-layers: Arquitectura per capes]].
