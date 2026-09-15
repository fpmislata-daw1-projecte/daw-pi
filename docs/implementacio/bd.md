---
title: Base de dades
icon: material/database
alias: bd
---

*[SGBD]: Sistema Gestor de Bases de Dades

# :material-database: Base de dades
Una __base de dades ben dissenyada__ és fonamental per a garantir la
integritat, la coherència i el bon rendiment de l'aplicació, sobretot
tenint en compte que hi accediran diversos usuaris de manera concurrent.

## Disseny de la base de dades
Abans de començar a implementar l'aplicació, cal dissenyar la base de
dades seguint aquestes passes:

- __Model relacional__: identificar les entitats del sistema, els seus
    atributs i les relacions que hi ha entre elles. Definir
    les __claus primàries__ i __claus foranes__ que garanteixen la
    integritat referencial entre elles.
- __Normalització__: revisar l'estructura de les taules per a evitar
    redundàncies i anomalies.


## Sistemes gestors de bases de dades
L'aplicació accedirà a __dos sistemes gestors de bases de dades__ diferents,
cadascun pensat per a un tipus de dades concret:

- __:simple-mariadb: MariaDB__: base de dades __relacional__, per a les
    dades estructurades de l'aplicació que requereixen integritat
    referencial i consultes complexes (usuaris, comandes, etc.).
- __:simple-mongodb: MongoDB__: base de dades __NoSQL__ orientada a
    documents, per a les dades amb una estructura més flexible o canviant
    (per exemple, registres, historials o continguts sense un esquema fix).

## Accés a les dades des del servidor
Seguint l'[[arquitectura|:material-layers: arquitectura per capes]] del
servidor, l'accés a la base de dades es realitzarà des de la capa de
__Persistència__, mitjançant:

- __Repositoris__: defineixen les operacions disponibles sobre cada entitat
    (crear, consultar, actualitzar, eliminar), independentment de si les
    dades es guarden en __:simple-mariadb: MariaDB__ o en
    __:simple-mongodb: MongoDB__.
- __DAOs__: implementen els repositoris. Segons el sistema gestor de bases
    de dades, s'implementaran amb __:simple-spring: Spring JDBC__ (per a
    executar sentències SQL sobre MariaDB) o amb el __driver de MongoDB__
    (per a executar consultes sobre documents).
- __RowMappers__: converteixen cada fila (MariaDB) o document (MongoDB)
    del resultat d'una consulta en una entitat de domini.
