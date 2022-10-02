# 14 Instalar Jupyter Netbook de forma segura en tu vps

Entramos y ejecutamos:

    sudo apt update -y && sudo apt install curl gnupg2 ca-certificates lsb-release -y

Instalamos la última versión hasta la fecha, dando click derecho en esta página web:

    [anaconda distribution](https://www.anaconda.com/products/distribution)

Exactamente click derecho copiar link aquí:

![anaconda distribution link for ubuntu and create curl command](https://user-images.githubusercontent.com/5947268/193467631-9d94ea0c-3828-4a12-a612-544578276f66.png)

Y ejecutamos (ahora estamos en Domingo 2 de Octubre del 2022, y este es el link: https://repo.anaconda.com/archive/Anaconda3-2022.05-Linux-x86_64.sh)

    cd /tmp && curl https://repo.anaconda.com/archive/Anaconda3-2022.05-Linux-x86_64.sh --output anaconda.sh

Ejecutamos para comprobar el Hash con la página web oficial en internet:

    sha256sum /tmp/anaconda.sh

Y comenzamos la instalación:

    bash anaconda.sh

Decimos

    yes

Le damos al enter todo el rato y le decimos:

    yes

Ejecutamos:

    source ~/.bashrc
