# 04 Acceso Root: ¿Cómo acceder con root por ssh en mi servidor VPS Ubuntu 22.04 LTS?

Paso 1: Editamos sshd_config ejecutando

    sudo nano /etc/ssh/sshd_config

Paso 2: Cambiar

    #PermitRootLogin prohibit-password

por

    PermitRootLogin yes

Paso 3: Control X, Y y aceptar para guardar el archivo.

Paso 4: Ejecutamos

    sudo service ssh restart

Paso 5 ejecutamos para salir:

    Exit

Paso 6:

    ssh root@123.123.123.123
