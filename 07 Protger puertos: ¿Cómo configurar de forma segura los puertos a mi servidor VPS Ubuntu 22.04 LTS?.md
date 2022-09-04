# 07 Puertos: ¿Cómo configurar de forma segura los puertos a mi servidor VPS Ubuntu 22.04 LTS?

Paso 1: Ejecutamos estos comandos repetidas veces

    ufw allow http

Este:

    ufw allow https

Y finalmente

    ufw allow 25472
