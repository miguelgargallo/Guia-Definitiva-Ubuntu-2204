# 06 Cambiar hostname: ¿Cómo cambio el hostname a mi servidor VPS Ubuntu 22.04 LTS?

Paso 1: Vamos a este archivo y cambiamos lo que haya por el nombre que deseamos, por ejemplo "aws" de amazon:

    nano /etc/hostname

Paso 2: Vamos a estos dos archivos y cambiamos lo que haya por esta plantilla:

    nano /etc/hosts

Este otro archivo:

    nano /etc/cloud/templates/hosts.debian.tmpl

Notas: Primera zona # debe quedar así:

    127.0.1.1 server.visita.teide server
    127.0.0.1 localhost

Notas: Segunda zona # se debe añadir, no tocar lo que haya:

    123.123.123.123 server.visita.teide server
