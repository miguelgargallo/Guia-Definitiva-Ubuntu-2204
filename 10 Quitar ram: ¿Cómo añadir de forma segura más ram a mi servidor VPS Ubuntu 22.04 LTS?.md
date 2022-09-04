# 10 Quitar ram: ¿Cómo añadir de forma segura más ram a mi servidor VPS Ubuntu 22.04 LTS?

Paso 1: Ejecutamos:

    swapoff -v /ramr

Después:

    sudo nano /etc/fstab

Paso 2: Borramos la linea que hemos escrito

    /ramr swap swap defaults 0 0

Paso 3: Ejecutamos:

    rm -f /swapfile

Reiniciamos

    Reboot

