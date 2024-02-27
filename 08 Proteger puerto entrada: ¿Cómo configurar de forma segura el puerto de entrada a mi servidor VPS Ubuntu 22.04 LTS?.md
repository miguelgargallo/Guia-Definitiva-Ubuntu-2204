 # 08 Proteger puerto entrada: ¿Cómo configurar de forma segura el puerto de entrada a mi servidor VPS Ubuntu 22.04 LTS?

Esta lección debe ser leida hasta el final

IMPORTANTE: Si al terminar esta clase, sales del servidor y no reinicias, no te preocupes, ve al panel de AWS o del serivicio que tengas contratado, y reinicia de ahí, no te asustes, no has perdido nada.

Truco de oro: Cuando hayas terminado: con otra consola, intenta entrar, porque sino puedes hacerlo desde el usuario que quieres... y sales de las 2 terminales, deberás de resetear todo el p* setup y estaras f*cked. Este truco es de oro.

Paso 0: Haz una copia de seguridad

    sudo cp /etc/ssh/sshd_config /etc/ssh/sshd_config.bak

Paso 1: Entramos en el archivo siguiente y cambiamos lo siguiente:

    sudo nano /etc/ssh/sshd_config

Y cambiamos el puerto:

    #Port 22

por

    Port 25472

Reiniciamos el servicio

    sudo service ssh restart

A partir de este momento y sin cerrar la tarminal, abre otra terminal, sí leíste bien, no cierres nada, simplemente abre terminal nueva e intenta acceder con:

    ssh -p 25472 tuuusario@123.123.123.123

Si todo está bien, el puerto nuevo será de entrada.

Esta lección debe ser leida hasta el final

Si lo que queremos es solo admitir a 1 usaurio y no permitir el login desde root

    sudo nano /etc/ssh/sshd_config

Copia esto con `ctrl` + `c`, si estas en Mac, es `cmd` + `c`

    Authentication

Y debajo pegamos:

    AllowUsers tuusuario

*tuusuario recuerda cambiar esto por el usuario con el que quieras entrar, esto va muy bien para cuando quieres prohibir el acceso de ssh a usuarios como `admin` donde por defecto `root` ya está bloqueado, pero no `admin`.

Y vamos a: `ctrl` + `w` de este modo, click derecho a la palabra consola si estas en Mac, es `cmd` + `w`

Si quieres mas de uno, solo pon espacio, y ya estaría:

    AllowUsers tuusuario tumadre

Y reiniciamos el servicio

    sudo service ssh restart

Ahora haz el truco de oro, pilla otra consola e intenta entrar

Ahora, abrimos otra terminal, y ejecutamos el `ssh -p 25472 user@123.123.123.123` para ver si deja entrar por ahí, porque sino te deja, no te austes, revisa los pasos hasta ahora, si cierras esa ventana, podrías no volver a acceder, para ello, en la ventana donde te ha fallado el accoeso ejecuta: `ssh user@123.123.123.123` si te pregunta por la contraseña, significa que el puerto `22` aún está operativo y que posiblemente no has activado bien el `ufw`, revisa todo con calma.

¿Porqué te enseño esto del `numbered`? Básicamente podrás borrar super rapido o manejar los puertos de forma mas eficiente:

    sudo ufw deny 1

o

    sudo ufw allow 1/tcp

Por cierto, si abres un puerto para algo, haz esto primero: ve a esta web

[Ports Guide de Miguel](https://www.speedguide.net/ports.php), está web es god tier level max, mira el puerto que quieres abrir si tiene alguna vulnerabilidad, y luego, sino hay nada raro:

    sudo ufw allow XXX/tcp

añadirmos tcp.

```md
El protocolo TCP (Transmission Control Protocol) es el encargado de proporcionar un servicio de comunicación punto a punto entre dos host. Este protocolo de cuarto nivel está orientado a conexión en la capa de transporte y funciona a través de la conexión mutua entre cliente y servidor.
```

IMPORTANTE: Si sales y no reinicias, no te preocupes, ve al panel de AWS o del serivicio que tengas contratado, y reinicia de ahí, no te asustes, no has perdido nada.

Truco de oro: Cuando hayas terminado: con otra consola, intenta entrar, porque sino puedes hacerlo desde el usuario que quieres... y sales de las 2 terminales, deberás de resetear todo el p* setup y estaras f*cked. Este truco es de oro.

*Por cierto:

Quita el puerto 22 con el valor de X

```bash
sudo ufw delete X
```

Le das a `Y` y Ahora haces numbered

```
sudo ufw status numbered
```

y quitar el otro (v6) restante

```bash
sudo ufw delete X
```

Le das a `Y` y listo.

Sin salir, abres otra consola y si puedes entrar y todo bien, has terminado.


## Miguel Gargallo Atlas

Miguel Gargallo Atlas es tu guía! aquí te indico por donde vas de la Guía Definitva Ubuntu 2204, tambien disponible a través del link [ubuntu.download](https://ubuntu.download), en la descripción encontrarás el link para descargar de forma segura Ubuntu desde la web oficial.

### Ir al siguiente capítulo, nueva lección:

[09 Añadir ram](https://github.com/miguelgargallo/Guia-Definitiva-Ubuntu-2204/blob/main/09%20A%C3%B1adir%20ram:%20%C2%BFC%C3%B3mo%20a%C3%B1adir%20de%20forma%20segura%20m%C3%A1s%20ram%20a%20mi%20servidor%20VPS%20Ubuntu%2022.04%20LTS%3F.md) ▶️

### Volver atrás, lección anterior:

[07 Protger puertos](https://github.com/miguelgargallo/Guia-Definitiva-Ubuntu-2204/blob/main/07%20Protger%20puertos:%20%C2%BFC%C3%B3mo%20configurar%20de%20forma%20segura%20los%20puertos%20a%20mi%20servidor%20VPS%20Ubuntu%2022.04%20LTS%3F.md) ✅


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

[08 Proteger puerto entrada](https://github.com/miguelgargallo/Guia-Definitiva-Ubuntu-2204/blob/main/08%20Proteger%20puerto%20entrada:%20%C2%BFC%C3%B3mo%20configurar%20de%20forma%20segura%20el%20puerto%20de%20entrada%20a%20mi%20servidor%20VPS%20Ubuntu%2022.04%20LTS%3F.md) 💚

[09 Añadir ram](https://github.com/miguelgargallo/Guia-Definitiva-Ubuntu-2204/blob/main/09%20A%C3%B1adir%20ram:%20%C2%BFC%C3%B3mo%20a%C3%B1adir%20de%20forma%20segura%20m%C3%A1s%20ram%20a%20mi%20servidor%20VPS%20Ubuntu%2022.04%20LTS%3F.md) ▶️

[10 Quitar ram](https://github.com/miguelgargallo/Guia-Definitiva-Ubuntu-2204/blob/main/10%20Quitar%20ram:%20%C2%BFC%C3%B3mo%20a%C3%B1adir%20de%20forma%20segura%20m%C3%A1s%20ram%20a%20mi%20servidor%20VPS%20Ubuntu%2022.04%20LTS%3F.md) ▶️

[11 Instalar Rust](https://github.com/miguelgargallo/Guia-Definitiva-Ubuntu-2204/blob/main/11%20Instalar%20Rust:%20%C2%BFC%C3%B3mo%20instalar%20Rust%20de%20forma%20segura%20en%20mi%20VPS%20Ubuntu%2022.04%20LTS%3F.md) ▶️

[12 Instalar UFW Firewall](https://github.com/miguelgargallo/Guia-Definitiva-Ubuntu-2204/blob/main/12%20Instalar%20ufw%20para%20puertos%20Ubuntu%2022.04-LTS-Server-VPS.md) ▶️

[13 Instalar bottom con rust](https://github.com/miguelgargallo/Guia-Definitiva-Ubuntu-2204/blob/main/13%20Instalar%20bottom%20con%20rust%20de%20forma%20segura%20en%20tu%20vps.md) ▶️

[14 Instalar Jupyter Server Netbook](https://github.com/miguelgargallo/Guia-Definitiva-Ubuntu-2204/blob/main/14%20Instalar%20Jupyter%20Netbook%20de%20forma%20segura%20en%20tu%20vps.md) ▶️

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
