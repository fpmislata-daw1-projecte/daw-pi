---
title: Desplegament
icon: material/cloud-upload
alias: desplegament
---

# :material-cloud-upload: Desplegament
Una vegada implementada l'aplicació, cal __desplegar-la__ en un servidor
perquè estiga disponible i es puga utilitzar en un entorn real.

## Servidors de desplegament
L'aplicació es desplegarà utilitzant __:simple-docker: Docker__ per a
empaquetar i executar l'aplicació (servidor, base de dades, etc.) de manera
aïllada i reproduïble, en els següents servidors:

- __:simple-proxmox: Proxmox__: servidor virtualitzat allotjat al
    __CIPFP Mislata__. Aquest és el servidor de desplegament requerit
    per al projecte.
- __:material-aws: Amazon Web Services (AWS)__: com a __ampliació__, una
    vegada l'aplicació funcione correctament en Proxmox, es pot desplegar
    també en AWS, per a practicar el desplegament en un entorn de núvol
    públic.

## Desplegament automatitzat
El desplegament es pot incloure com una tasca més dins de
l'[[automatitzacio|:fontawesome-solid-gears: automatització]] del projecte,
utilitzant :octicons-play-16: GitHub Actions per a publicar automàticament
una nova versió de l'aplicació en el servidor cada vegada que es crea un nou
[:material-tray-arrow-up: Llançament (_Release_)][releases], seguint les
pràctiques de __CI/CD__.

[releases]: https://docs.github.com/en/repositories/releasing-projects-on-github/about-releases
