# 16 Instalar Certbot LetsEncrypt de forma segura en tu vps

Comenzamos a ejecutar:

    sudo apt install certbot -y

Abrimos puerto 80:

    sudo ufw allow 80

Abrimos puerto 443:

    sudo ufw allow 443

Ejecutamos: (si te pide un correo es para que te lleguen alertas de renovar el certficado, es gratis, tu dale uno el que sea y ya vale)

    sudo certbot certonly --standalone

Escribimos el dominio web al que queremos poner el canadito o candado verde de ssl:

    miguelgargallo.com

Le dices que "yes" o "a" de agree, que es estar de acuerdo a todo y listo:

    yes

o

    a

Comprobamos que todo esté correcto:

    sudo ls -a /etc/letsencrypt/live/miguelgargallo.com

Si te salen los archivos es que está correcto.
