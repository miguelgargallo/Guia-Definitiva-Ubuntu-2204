# 09 Añadir ram: ¿Cómo añadir de forma segura más ram a mi servidor VPS Ubuntu 22.04 LTS?
### Notas: Ahora añadiremos mas ram, sí. Este tipo de VPS, por lo general suelen venir con poca ram, 1GB, 2GB o 4GB, incluso si crees que te vas a quedar corto de ram con 8gb, podemos añadir más ram, gracias a nuestra memoria SSD.

Paso 1: Ejecutamos:

    fallocate -l 8G /rammg

Después:

    chmod 600 /rammg

Finalmente:

    mkswap /rammg  && sudo swapon /rammg

Paso 2: Editamos con el editor nano:

    /etc/fstab

Comando referenciado en la lección 99 Glosario, link en el pié de la página de esta lección.

Paso 3: Añadimos al final del documento:

    /rammg swap swap defaults 0 0

Paso 4: Guardamos y salimos:
Comando referenciado en la lección 99 Glosario, link en el pié de la página de esta lección.

PAso 5: Ejecutamos:

    swapon --show

Liberamos memoria

    free -h
    
Reiniciamos

    reboot

En el documento 98 Tablas de ram: Encontraremos las equivalencias de memoria y ram.
