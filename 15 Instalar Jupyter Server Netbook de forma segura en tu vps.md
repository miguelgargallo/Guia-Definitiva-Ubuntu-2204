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
