# 15 Instalar Jupyter Server Netbook de forma segura en tu vps

Le decimos que queremos generar un archivo por defecto de configuración:

      jupyter notebook --generate-config

Le configuramos la contraseña:

      jupyter notebook password

Ponemos una Contraseña segura que nos acordemos:

    C0nT3A5ena$egura

Le pedimos la contraseña Hasheada para ponerla en el archivo de configuración:

    cat /home/TuUsuario/.jupyter/jupyter_notebook_config.json

Si no tienes instalado certbot, visita el próximo capítulo, sino ve directamente al segundo link.

[16 Instalar Certbot LetsEncrypt de forma segura en tu vps](https://github.com/miguelgargallo/Configurar-Ubuntu-22.04-LTS-Server-VPS/blob/main/16%20Instalar%20Certbot%20LetsEncrypt%20de%20forma%20segura%20en%20tu%20vps.md)

[17 Configurar Jupyter Server Netbook de forma segura en tu vps](https://github.com/miguelgargallo/Configurar-Ubuntu-22.04-LTS-Server-VPS/blob/main/17%20Configurar%20Jupyter%20Server%20Netbook%20de%20forma%20segura%20en%20tu%20vps.md)

