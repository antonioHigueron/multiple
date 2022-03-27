# multiple
Usar dos o más cuentas de git en un mismo pc:
FUENTES:
https://thescienceofcode.azurewebsites.net/Articles/Show/5e71a2076dc6a240f8dbe934

https://www.youtube.com/watch?v=vSeYsk4WYvg

1 Tener git instalado

2 Si no existe crear carpeta ssh en: C:\Users\yourUser\.ssh

3 Crear las keys ssh
(ssh-keygen viene con git o en system32 en windows)
(rsa,ed25519... es el tipo) 
ssh-keygen -t rsa -C "youremail@email.com"

4 Te pide el nombre del fichero, debe crearse dentro del directorio .ssh
por ejemplo:
id_rsa_github_antonioHigueron
(rsa es el tipo, github es el proveedor, antonioHigueron es el user)

5 Pedirá una pass, si el equipo es de confianza y no quieres introducir en cada cambio, solo pulsar ENTER

6 crear en .ssh un archivo: "config" e introducir la info:
# Github
Host acaeronte github.com-acaeronte
HostName github.com
PreferredAuthentications publickey
IdentityFile ~/.ssh/id_rsa_github_acaeronte 

(Host 1dato puede ser un alias, 2dato seria el valor a usar sino hay alias)
(HostName es el host del proveedor, github,gitlab,bitbucket,azure...)
(PreferredAuthentications se va a usar la public key, que es el fichero xxxx.pub local)
(IdentityFile fichero que contiene la key)

7 Copiar el contenido del archivo: 
id_rsa_github_antonioHigueron.pub    en github: settings/SSH and GPG keys/SSH keys

8 Cuando vayas a clonar(MODIFICAR link copiado) un repo en local por SSH, poner:
git clone git@antonioHigueron:antonioHigueron/multiple.git

(en este caso se ha usado el alias:antonioHigueron es el dato que viene tras el @)

9 Con esto ya debería reconocerse en local el usuario con el que vas a trabajar ese repo
