# 17 Configurar Jupyter Server Netbook de forma segura en tu vps

Reemplaza las siguientes lineas:

El certificado, donde pone miguelgargallo.com pon tu dominio web.

    c.NotebookApp.certfile = '/etc/letsencrypt/live/miguelgargallo.com/fullchain.pem'

Ponemos asterisco para que se pueda acceder desde cualquier ip.

    c.NotebookApp.ip = '*'

El certificado, donde pone miguelgargallo.com pon tu dominio web.

    c.NotebookApp.keyfile = '/etc/letsencrypt/live/miguelgargallo.com/privkey.pem'

Si tu server no tiene GUI, ponle esto o petará la pestaña al acceder a Jupyter desde el buscador.

    c.NotebookApp.open_browser = False

Aquí va la contraseña Hasheada, recuerdas? entre los ''.

    c.NotebookApp.password = 'ESTO ES EL HASH QUE HEMOS COPIADO ANTES PONLO AQUI'

Le decimos que apunte al puerto 9000, seguramente esté escrito 8888, tu cámbialo.

    c.NotebookApp.port = 9000

Ejecutamos:

    sudo chmod 750 -R /etc/letsencrypt

Y luego, cuidado aquí escribe UsuarioActual donde pone: UsuarioActual

    sudo chown UsuarioActual:UsuarioActual -R /etc/letsencrypt

Ejecutamos:

    jupyter lab

Y nos vamos a tu IP o dominio web con el buscador y listo!!!

LETSGO!
