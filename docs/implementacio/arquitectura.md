---
title: Arquitectura per capes
icon: material/layers
alias: arquitectura
---

*[DAO]: Data Access Object

# :material-layers: Arquitectura per capes
El servidor és el nucli de l'aplicació, ja que és l'encarregat de gestionar
tota la lògica de negoci i l'accés a les dades. Per a mantindre'l organitzat,
mantenible i fàcil d'ampliar, la seua implementació ha de seguir una
__arquitectura per capes__, que permeta separar les diferents responsabilitats
de l'aplicació i facilite la seua evolució i manteniment.


## Capes de l'arquitectura

![Arquitectura per capes de l'aplicació](img/arquitectura.light.png#only-light)
![Arquitectura per capes de l'aplicació](img/arquitectura.dark.png#only-dark)
/// figure-caption : Arquitectura per capes de l'aplicació.

Les capes que s'han de definir en el servidor són les següents:

- __Controladors__: és la "cara visible" del servidor. Defineix les rutes
    (_endpoints_) de l'API REST i s'encarrega de gestionar les peticions
    de l'usuari i de retornar les respostes adequades.

    Responsabilitats:

    - Definir les rutes (`/productes`, `/usuaris`, etc.).
    - Extraure les dades de la petició (paràmetres de la URL, cos JSON, capçaleres).
    - Cridar a la funció corresponent de la capa de __Domini__.
    - Retornar el codi d'estat HTTP adequat (`200`, `201`, `400`, `404`, `500`).

- __Domini__: és el "cervell" de l'aplicació, on resideix la lògica de negoci.
    Ací es decideix què es pot fer i què no, seguint les regles del projecte.

    Aquesta capa conté:

    - __Entitats__: Classes que representen els objectes de negoci de l'aplicació.
    - __Serveis__: Classes que contenen la lògica de negoci de l'aplicació.

    Responsabilitats:

    - Realitzar validacions de seguretat o de coherència.
    - Processar dades (filtrar, ordenar, transformar).
    - Coordinar múltiples operacions.
    - Cridar a la capa de __Persistència__ per llegir o guardar informació.

- __Persistència__: és l'única capa que té permís per a parlar amb la base
    de dades. El seu objectiu és abstreure la resta de l'aplicació dels
    detalls concrets de com es guarden i es consulten les dades.

    Aquesta capa conté:

    - __Repositoris__: Classes que s'encarreguen de gestionar l'accés a les
        dades de l'aplicació.
    - __DAOs__: Classes que s'encarreguen de realitzar les consultes a la
        base de dades.
    - __RowMappers__: Classes que s'encarreguen de mapar les files de la base
        de dades a entitats de domini.

    Responsabilitats:

    - Executar les consultes SQL.
    - Convertir el resultat de les consultes a entitats de domini.
    - Gestionar la connexió amb la base de dades.

## Importància de les interfícies
Dins d'una arquitectura per capes, les interfícies actuen com un
__contracte__ entre les diferents capes del sistema: defineixen __què__
fa un component sense determinar __com__ ho fa.

L'ús d'interfícies aporta:

- __Desacoblament__: la implementació de cada capa és independent de les
    altres, i es pot canviar sense afectar la resta del sistema.

    > Per exemple, si es vol canviar la base de dades de MariaDB a MongoDB,
    > sols cal modificar la capa de persistència.

- __Facilitat per a fer proves__: permeten substituir una implementació real
    per un [[proves|:material-marker-check: objecte simulat (_mock_)]]
    que emula el seu comportament, per a provar cada capa de manera aïllada.

- __Inversió de dependències__: seguint els principis SOLID, les capes
    superiors no depenen de les capes inferiors, sinó d'abstraccions. Això
    minimitza l'impacte de futurs canvis o migracions de tecnologia.
