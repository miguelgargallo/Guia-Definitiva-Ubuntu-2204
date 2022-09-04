# 08 Proteger puerto entrada: ¿Cómo configurar de forma segura el puerto de entrada a mi servidor VPS Ubuntu 22.04 LTS?

Paso 1: Entramos en el archivo siguiente y cambiamos lo siguiente

    nano /etc/ssh/sshd_config

Y cambiamos el puerto:

    #Port 22

por

    Port 25472
