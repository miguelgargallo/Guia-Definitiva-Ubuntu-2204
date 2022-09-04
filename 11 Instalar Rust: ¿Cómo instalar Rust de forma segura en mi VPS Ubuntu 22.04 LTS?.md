11 Instalar Rust: ¿Cómo instalar Rust de forma segura en mi VPS Ubuntu 22.04 LTS?


Paso 1: Actualizamos nuestro servidor

    sudo apt update && sudo apt upgrade

Paso 2: Ejecutaremos el siguiente comando para instalar los paquetes necesarios:

    sudo apt install curl build-essential gcc make -y

Paso 3: Ejecutamos la instalación de Rust

    curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh

Paso 4: Escojemos opción 1.

    1, Presionamos, Enter.

Paso 5: Verificamos:

    source ~/.profile

    source ~/.cargo/env

    rustc -V

Finalmente, para la fecha en la que estamos este es el resultado:

    rustc 1.63.0 (4b91a6ea7 2022-08-08)


< [Lección anterior: 10 Quitar ram](https://github.com/miguelgargallo/Configurar-Ubuntu-22.04-LTS-Server-VPS/blob/main/10%20Quitar%20ram:%20%C2%BFC%C3%B3mo%20a%C3%B1adir%20de%20forma%20segura%20m%C3%A1s%20ram%20a%20mi%20servidor%20VPS%20Ubuntu%2022.04%20LTS%3F)   |  [00 Vuelve al Índice](https://github.com/miguelgargallo/Configurar-Ubuntu-22.04-LTS-Server-VPS)      >
