# 14 Instalar Jupyter Netbook de forma segura en tu vps

Entramos y ejecutamos:

    sudo apt update -y && sudo apt install curl gnupg2 ca-certificates lsb-release -y

Instalamos la última versión hasta la fecha, dando click derecho en esta página web:

[anaconda distribution](https://www.anaconda.com/products/distribution)

Exactamente click derecho copiar link aquí:

![anaconda distribution link for ubuntu and create curl command](https://user-images.githubusercontent.com/5947268/193467631-9d94ea0c-3828-4a12-a612-544578276f66.png)

Y ejecutamos (ahora estamos en Domingo 2 de Octubre del 2022, y este es el link: https://repo.anaconda.com/archive/Anaconda3-2024.02-1-Linux-x86_64.sh)

    cd /tmp && curl https://repo.anaconda.com/archive/Anaconda3-2024.02-1-Linux-x86_64.sh --output anaconda.sh


Por razones de seguridad deposito los MD5

```sh
Anaconda3-2024.02-1-Windows-x86_64.exe	904.4M	2024-02-26 14:50:21	087c633e355bc709222ad9e0dbad77abeed84f7e06dbdbecae84ba8b3660429e
Anaconda3-2024.02-1-MacOSX-x86_64.sh	731.2M	2024-02-26 14:50:21	944aee9b90f7d8a2a997d0337cb37219757f22e76c10de38c7c68191c6b5b226
Anaconda3-2024.02-1-MacOSX-x86_64.pkg	728.7M	2024-02-26 14:50:21	56ed87ad85b1203fad1dc7c5c4e6ac2034f3a69d676ea83f78bd1b7f10ca6a8a
Anaconda3-2024.02-1-MacOSX-arm64.sh	700.0M	2024-02-26 14:50:21	14a1c80af18c2c2e743e63cdb41228cd554a3fdb250563b6978348c80b6860f6
Anaconda3-2024.02-1-MacOSX-arm64.pkg	697.4M	2024-02-26 14:50:21	c22f864ceb962c89b5dbb9170c64acc5ee02dd96af988b0ecc3bf2f880ce8928
Anaconda3-2024.02-1-Linux-x86_64.sh	997.2M	2024-02-26 14:50:21	c536ddb7b4ba738bddbd4e581b29308cb332fa12ae3fa2cd66814bd735dff231
Anaconda3-2024.02-1-Linux-s390x.sh	391.8M	2024-02-26 14:50:21	3e2e8b17ea9a5caafd448f52e01435998b2e1ce102040a924d5bd6e05a1d735b
Anaconda3-2024.02-1-Linux-aarch64.sh	798.5M	2024-02-26 14:50:21	28c5bed6fba84f418516e41640c7937514aabd55e929a8f66937c737303c7bba
```

Fuente: [repo.anaconda.com/archive](https://repo.anaconda.com/archive/)

Ejecutamos para comprobar el Hash con la página web oficial en internet:

    sha256sum /tmp/anaconda.sh

Y comenzamos la instalación:

    bash anaconda.sh

Presionamos `ENTER`

Le damos al `q` y luego

    yes

Presionamos `ENTER`

Y luego cuando termine, ejecutamos:

    source ~/.bashrc

Si al terminar no puedes ejecutar

    python3 --help

Instala Python

    sudo apt install python-is-python3

Ahora, para instalar el notebook

```sh
cd ~/environments
```

Si da error

```sh
mkdir ~/environments
```

seguido de

```sh
cd ~/environments
```

y de

```
. my_env/bin/activate
```

Instalamos y upgradreamos el pip

```sh
pip install --upgrade pip
```

e instalamos el jupyter

```sh
pip install jupyter
```

para arrancarlo:

```sh
jupyter notebook
```

y vamos a [http://127.0.0.1:8888/](http://127.0.0.1:8888/)

Si por algun motivo no sabemos la contrasela, ejecutamos `CTRL + C` en la propia consola donde se ejecuta, y ponemos


```sh
jupyter notebook password
```

ponemos una contraseña seguira

y volvemos a arrancar el jupyter

```sh
jupyter notebook
```

y vamos a [http://127.0.0.1:8888/](http://127.0.0.1:8888/)

[PylarAI](https://pylar.org) Tips:
Si diera error en el my env

```sh
cd ~/environments
No such file or directory
mkdir ~/environments
cd ~/environments
~/environments$ . my_env/bin/activate
No such file or directory
~/environments$
```

Entonces

PylarAI dice:

Of course, as an expert in the field, it appears that the virtual environment `my_env` does not exist within your `environments` directory, which is why you're encountering an error when trying to activate it. You'll need to first create the virtual environment. Here's how to do it:

```bash
# Create a new virtual environment named my_env
python -m venv my_env

# Activate the virtual environment
source my_env/bin/activate
```


## Miguel Gargallo Atlas

Miguel Gargallo Atlas es tu guía! aquí te indico por donde vas de la Guía Definitva Ubuntu 2204, tambien disponible a través del link [ubuntu.download](https://ubuntu.download), en la descripción encontrarás el link para descargar de forma segura Ubuntu desde la web oficial.

### Ir al siguiente capítulo, nueva lección:

[15 Instalar Jupyter Server](https://github.com/miguelgargallo/Guia-Definitiva-Ubuntu-2204/blob/main/15%20Instalar%20Jupyter%20Server%20Netbook%20de%20forma%20segura%20en%20tu%20vps.md) ▶️

### Volver atrás, lección anterior:

[13 Instalar bottom con rust](https://github.com/miguelgargallo/Guia-Definitiva-Ubuntu-2204/blob/main/13%20Instalar%20bottom%20con%20rust%20de%20forma%20segura%20en%20tu%20vps.md) ✅


### No te pierdas

#### ▶️ Leyenda

- Tu estás Aquí: 💚
- Y has hecho:✅
- Te falta: ▶️

#### 🎉 Recorrido

[01 Primer acceso](https://github.com/miguelgargallo/Guia-Definitiva-Ubuntu-2204/blob/main/01%20Primer%20acceso:%20%C2%BFC%C3%B3mo%20acceder%20a%20mi%20servidor%20VPS%20Ubuntu%2022.04%20LTS%20por%20primera%20vez%3F.md) ✅

[02 Contraseñas](https://github.com/miguelgargallo/Guia-Definitiva-Ubuntu-2204/blob/main/02%20Contrase%C3%B1as:%20%C2%BFC%C3%B3mo%20cambio%20las%20contrase%C3%B1as%20de%20mis%20usuarios%20en%20servidor%20VPS%20Ubuntu%2022.04%20LTS%3F.md) ✅

[03 Contraseña Root](https://github.com/miguelgargallo/Guia-Definitiva-Ubuntu-2204/blob/main/03%20Contrase%C3%B1a%20Root:%20%C2%BFC%C3%B3mo%20cambio%20la%20contrase%C3%B1a%20a%20root%20de%20mis%20usuarios%20en%20servidor%20VPS%20Ubuntu%2022.04%20LTS%3F.md) ✅

[04 Acceso Root](https://github.com/miguelgargallo/Guia-Definitiva-Ubuntu-2204/blob/main/04%20Acceso%20Root:%20%C2%BFC%C3%B3mo%20acceder%20con%20root%20por%20ssh%20en%20mi%20servidor%20VPS%20Ubuntu%2022.04%20LTS%3F.md) ✅

[05 Actualizar y Upgradear](https://github.com/miguelgargallo/Guia-Definitiva-Ubuntu-2204/blob/main/05%20Actualizar%20y%20Upgradear:%20%C2%BFC%C3%B3mo%20actualizo%20y%20upgradeo%20mi%20servidor%20VPS%20Ubuntu%2022.04%20LTS%3F.md) ✅

[06 Cambiar hostname](https://github.com/miguelgargallo/Guia-Definitiva-Ubuntu-2204/blob/main/06%20Cambiar%20hostname:%20%C2%BFC%C3%B3mo%20cambio%20el%20hostname%20a%20mi%20servidor%20VPS%20Ubuntu%2022.04%20LTS%3F.md) ✅

[07 Protger puertos](https://github.com/miguelgargallo/Guia-Definitiva-Ubuntu-2204/blob/main/07%20Protger%20puertos:%20%C2%BFC%C3%B3mo%20configurar%20de%20forma%20segura%20los%20puertos%20a%20mi%20servidor%20VPS%20Ubuntu%2022.04%20LTS%3F.md) ✅

[08 Proteger puerto entrada](https://github.com/miguelgargallo/Guia-Definitiva-Ubuntu-2204/blob/main/08%20Proteger%20puerto%20entrada:%20%C2%BFC%C3%B3mo%20configurar%20de%20forma%20segura%20el%20puerto%20de%20entrada%20a%20mi%20servidor%20VPS%20Ubuntu%2022.04%20LTS%3F.md) ✅

[09 Añadir ram](https://github.com/miguelgargallo/Guia-Definitiva-Ubuntu-2204/blob/main/09%20A%C3%B1adir%20ram:%20%C2%BFC%C3%B3mo%20a%C3%B1adir%20de%20forma%20segura%20m%C3%A1s%20ram%20a%20mi%20servidor%20VPS%20Ubuntu%2022.04%20LTS%3F.md) ✅

[10 Quitar ram](https://github.com/miguelgargallo/Guia-Definitiva-Ubuntu-2204/blob/main/10%20Quitar%20ram:%20%C2%BFC%C3%B3mo%20a%C3%B1adir%20de%20forma%20segura%20m%C3%A1s%20ram%20a%20mi%20servidor%20VPS%20Ubuntu%2022.04%20LTS%3F.md) ✅

[11 Instalar Rust](https://github.com/miguelgargallo/Guia-Definitiva-Ubuntu-2204/blob/main/11%20Instalar%20Rust:%20%C2%BFC%C3%B3mo%20instalar%20Rust%20de%20forma%20segura%20en%20mi%20VPS%20Ubuntu%2022.04%20LTS%3F.md) ✅

[12 Instalar UFW Firewall](https://github.com/miguelgargallo/Guia-Definitiva-Ubuntu-2204/blob/main/12%20Instalar%20ufw%20para%20puertos%20Ubuntu%2022.04-LTS-Server-VPS.md) ✅

[13 Instalar bottom con rust](https://github.com/miguelgargallo/Guia-Definitiva-Ubuntu-2204/blob/main/13%20Instalar%20bottom%20con%20rust%20de%20forma%20segura%20en%20tu%20vps.md) ✅

[14 Instalar Jupyter Server Netbook](https://github.com/miguelgargallo/Guia-Definitiva-Ubuntu-2204/blob/main/14%20Instalar%20Jupyter%20Netbook%20de%20forma%20segura%20en%20tu%20vps.md) 💚

[15 Instalar Jupyter Server](https://github.com/miguelgargallo/Guia-Definitiva-Ubuntu-2204/blob/main/15%20Instalar%20Jupyter%20Server%20Netbook%20de%20forma%20segura%20en%20tu%20vps.md) ▶️

[16 Instalar Certbot Letsencrypt SSL Candado verde](https://github.com/miguelgargallo/Guia-Definitiva-Ubuntu-2204/blob/main/16%20Instalar%20Certbot%20LetsEncrypt%20de%20forma%20segura%20en%20tu%20vps.md) ▶️

[17 Configurar Jupyter Server](https://github.com/miguelgargallo/Guia-Definitiva-Ubuntu-2204/blob/main/17%20Configurar%20Jupyter%20Server%20Netbook%20de%20forma%20segura%20en%20tu%20vps.md) ▶️

[18 Instalar Cualquier version de Node](https://github.com/miguelgargallo/Guia-Definitiva-Ubuntu-2204/blob/main/18%20Instalar%20Node%20¿Cómo%20instalar%20cualquier%20versión%20de%20Node%20en%20tu%20VPS%20Ubuntu%202204%20LTS%3F.md) ▶️

[19 Instalar Postgres ¿Cómo instalar Postgres en Ubuntu 2204?](https://github.com/miguelgargallo/Guia-Definitiva-Ubuntu-2204/blob/main/19%20Instalar%20Postgres%20%C2%BFC%C3%B3mo%20instalar%20Postgres%20en%20Ubuntu%202204%3F.md) ▶️

[20 Qt OpenGL ¿Cómo instalar Qt en Ubuntu 2204?](https://github.com/miguelgargallo/Guia-Definitiva-Ubuntu-2204/blob/main/20%20Qt%20OpenGL%20%C2%BFC%C3%B3mo%20instalar%20Qt%20en%20Ubuntu%202204%3F.md) ▶️

[21 Docker Portainer ¿Cómo instalar docker y docker portainer?](https://github.com/miguelgargallo/Guia-Definitiva-Ubuntu-2204/blob/main/21%20Docker%20Portainer%20%C2%BFC%C3%B3mo%20instalar%20docker%20y%20docker%20portainer%3F.md) ▶️

[97 Alias, atajos para comandos super rapidos?](https://github.com/miguelgargallo/Guia-Definitiva-Ubuntu-2204/blob/main/97%20Alias%2C%20atajos%20para%20comandos%20super%20rapidos.md) ▶️

[98 Taskel Instalación](https://github.com/miguelgargallo/Guia-Definitiva-Ubuntu-2204/blob/main/98%20Taskel%20Instalaci%C3%B3n.md) ▶️

[99 Glosario](https://github.com/miguelgargallo/Guia-Definitiva-Ubuntu-2204/blob/main/99%20Glosario%20b%C3%A1sico%20de%20comandos%20%C2%BFC%C3%B3mo%20escribo%20los%20comandos%20b%C3%A1sicos%20en%20mi%20servidor%20VPS%20Ubuntu%2022.04%20LTS%3F.md) ▶️

### Ir al menú, hay llegado al final de la lección, ve al Índice:

[Readme, Índice](https://github.com/miguelgargallo/Guia-Definitiva-Ubuntu-2204/blob/main/README.md) ✅

Que te ha parecido la Guía Definitiva Ubuntu 2204
