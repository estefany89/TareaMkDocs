# Git y Github

1. Git: instalación
2. GitHub
   * 2.1. Creación de un repositorio
3. Acceso Github desde local
   * 3.1. Acceso con usuario y PAT ( *personal access to ken* )
   * 3.2. Acceso con ssh
4. Proceso básico

## 1. Git: instalación

Es posible que ya instalado en máquina virtual. Si no apt install git

## 2. GitHub

Debe tener cuenta creada en GitHub. Se supone ya creada en otros módulos.

### 2.1. Creación de un repositorio

Creamos repositorio test-md-clases :

```
privado
con fichero README
```

## 3. Acceso Github desde local

GitHub ya **no** permite usar desde línea de comandos usuario y clave. En su lugar deberá usar un *token*
 personal o activar el uso de claves SSH. Observe el resultado al intentar clonar un repositorio privado
 usando clone HTTPS:

```
alu@xdebian11:~$ git clone https://github.com/angoies/test-md-clase.git
Clonando en 'test-md-clase'...
Username for 'https://github.com': angoies
Password for 'https://angoies@github.com':
remote: Support for password authentication was removed on August 13, 2021.
remote: Please see https://docs.github.com/en/get-started/getting-started-
with-git/about-remote-repositories#cloning-with-https-urls for information
on currently recommended modes of authentication.
fatal: Autenticación falló para 'https://github.com/angoies/test-md-
clase.git/'
alu@xdebian11:~$
```

### 3.1. Acceso con usuario y PAT ( personal access token )

En este enlace https://github.blog/2020-12-15-token-authentication-requirements-for-git-operations/ nos
 indica que ocurre y por qué. Lo más destacable:

```
Use of tokens offer a number of security benefits over password-based authentication:
1. Unique – tokens are specific to GitHub and can be generated per use or per device
2. Revocable – tokens can can be individually revoked at any time without needing to update
unaffected credentials
3. Limited – tokens can be narrowly scoped to allow only the access necessary for the use case
4. Random – tokens are not subject to the types of dictionary or brute force attempts that
simpler passwords that you need to remember or enter regularly might be
```

Lo que nos interesa: **tenemos que crear un token y utilizarlo en lugar de la clave**.

```
Enlace directo a creación de tokens: https://github.com/settings/tokens
Instrucciones de cómo crear el token
```

Para esta práctica basta generar un token "clásico" y darle todos los permisos al *scope* repo. Almacene el
 token en un lugar seguro, lo necesitará a continuación.

Para comprobar que todo es correcto volvemos a intentar el clone HTTPS usando como *password* el token
 obtenido:

```
alu@xdebian11:~$ git clone https://github.com/angoies/test-md-clase.git
Clonando en 'test-md-clase'...
Username for 'https://github.com': angoies
Password for 'https://angoies@github.com':
remote: Enumerating objects: 15, done.
remote: Counting objects: 100% (15/15), done.
remote: Compressing objects: 100% (12/12), done.
remote: Total 15 (delta 2), reused 9 (delta 1), pack-reused 0
Recibiendo objetos: 100% (15/15), listo.
Resolviendo deltas: 100% (2/2), listo.
alu@xdebian11:~$
```

Cada vez que intente acceder a un repositorio le pedirá usuario y token. Para trabajar con más comodidad
 es posible almacenar usuario y token en cache usando el comando git config --global
 credential.helper 'cache --timeout 3600' ( *timeout* especificado en segundos). Tras ejecutarlo le
 pedirá autenticarse una vez y eso datos se quedan en cache con ese tiempo de refresco.

```
alu@xdebian11:~$ cd test-md-clase/
alu@xdebian11:~/test-md-clase$ git config --global credential.helper 'cache
--timeout 3600'
alu@xdebian11:~/test-md-clase$ git push
Username for 'https://github.com': angoies
Password for 'https://angoies@github.com':
Everything up-to-date
alu@xdebian11:~/test-md-clase$ git push
Everything up-to-date
alu@xdebian11:~/test-md-clase$
```

Es posible almacenar el token de forma permanente, pero tenga en cuenta que lo hará en texto plano en el
 fichero ~/.git-credentials.

```
$ git config --local credential.helper store
$ git push http://example.com/repo.git
Username: <type your username>
Password: <type your password>
[several days later]
$ git push http://example.com/repo.git
[your credentials are used automatically]
```

Si quiere personalizar el fichero donde se almacena puede usar la opción git config --global
 credential.helper "store --file ~/.my-credentials"

### 3.2. Acceso con ssh

Podemos usar otro modo de autenticación: una clave SSH. Para ellos debe seguir los pasos indicados en
 Connecting to GitHub with SSH.

**Aviso** : Tenga en cuenta que si ya hemos clonado el repositorio con HTTPS será necesario modificar la
 configuración de los remotos. Para ello puede seguir estas indicaciones https://docs.github.com/es/get-
 started/getting-started-with-git/managing-remote-repositories#switching-remote-urls-from-https-to-ssh

En nuestro caso borraremos el directorio creado con el clone HTTPS y volvemos a hacer un clone SSH.

```
alu@xdebian11:~/test-md-clase$ cd ..
alu@xdebian11:~$ rm -rf test-md-clase/
alu@xdebian11:~$
```

Si intentamos clonar:

```
alu@xdebian11:~$ git clone git@github.com:angoies/test-md-clase.git
Clonando en 'test-md-clase'...
The authenticity of host 'github.com (140.82.121.3)' can't be established.
ECDSA key fingerprint is
SHA256:p2QAMXNIC1TJYWeIOttrVc98/R1BUFWu3/LiyKgUfQM.
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added 'github.com,140.82.121.3' (ECDSA) to the list of
known hosts.
git@github.com: Permission denied (publickey).
fatal: No se pudo leer del repositorio remoto.
Por favor asegúrate que tienes los permisos de acceso correctos
y que el repositorio existe.
alu@xdebian11:~$
```

Es necesario crear las claves SSH. Para ello tiene estos dos enlaces, crear en local y añadir en GitHub:

```
1. Generación de una nueva clave SSH
2. Agregar una clave SSH nueva a tu cuenta de GitHub
```

Vea un ejemplo de creación de las claves

```
alu@xdebian11:~$ ssh-keygen -t ed25519 -C "jgomez@iesromerovargas.com"
Generating public/private ed25519 key pair.
Enter file in which to save the key (/home/alu/.ssh/id_ed25519):
Enter passphrase (empty for no passphrase):
Enter same passphrase again:
Your identification has been saved in /home/alu/.ssh/id_ed
Your public key has been saved in /home/alu/.ssh/id_ed25519.pub
The key fingerprint is:
SHA256:10h/UuiiNSGtpnb7brUoPdyu79mQSyBtsPiQGHLgicc
jgomez@iesromerovargas.com
The key's randomart image is:
+--[ED25519 256]--+
|. |
| + o.. |
|. E o o +.. |
|. o o o B *. |
|. + S X =. |
| = * +.+ |
| o +o ++. |
|. ...*.o= |
| .=+**. |
+----[SHA256]-----+
alu@xdebian11:~$ ls -al .ssh/*.pub
-rw-r--r-- 1 alu alu 108 feb 23 09:12 .ssh/id_ed25519.pub
alu@xdebian11:~$ cat .ssh/id_ed25519.pub
ssh-ed
AAAAC3NzaC1lZDI1NTE5AAAAIIbaMp/uhRclwPz0AbQhooXxQN7IsUMfhqE9KtAOtoXa
jgomez@iesromerovargas.com
alu@xdebian11:~$
```

Luego seguimos los pasos para añadir la clave SSH a GitHub y finalmente probamos:

```
alu@xdebian11:~$ git clone git@github.com:angoies/test-md-clase.git
Clonando en 'test-md-clase'...
Enter passphrase for key '/home/alu/.ssh/id_ed25519':
remote: Enumerating objects: 15, done.
remote: Counting objects: 100% (15/15), done.
remote: Compressing objects: 100% (12/12), done.
Recibiendo objetos: 100% (15/15), listo.
Resolviendo deltas: 100% (2/2), listo.
remote: Total 15 (delta 2), reused 9 (delta 1), pack-reused 0
alu@xdebian11:~$
```

Puede "cachear la autenticación usando ssh-agent como se indica en este enlace.

## 4. Proceso básico

```
clone del repositorio creado previamente
alu@xdebian11:~$ git clone git@github.com:angoies/test-md-github.git
Clonando en 'test-md-github'...
remote: Enumerating objects: 3, done.
remote: Counting objects: 100% (3/3), done.
remote: Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
Recibiendo objetos: 100% (3/3), listo.
alu@xdebian11:~$ cd test-md-github/
alu@xdebian11:~/test-md-github$ ls
README.md
alu@xdebian11:~/test-md-github$
Trabajo en local: Modificar el fichero README.md
alu@xdebian11:~/test-md-github$ code README.md
alu@xdebian11:~/test-md-github$
status
alu@xdebian11:~/test-md-github$ git status
En la rama main
Tu rama está actualizada con 'origin/main'.
Cambios no rastreados para el commit:
(usa "git add <archivo>..." para actualizar lo que será confirmado)
(usa "git restore <archivo>..." para descartar los cambios en el
directorio de trabajo)
modificado: README.md
sin cambios agregados al commit (usa "git add" y/o "git commit -a")
alu@xdebian11:~/test-md-github$
add
alu@xdebian11:~/test-md-github$ git add README.md
alu@xdebian11:~/test-md-github$ git status
En la rama main
Tu rama está actualizada con 'origin/main'.
Cambios a ser confirmados:
(usa "git restore --staged <archivo>..." para sacar del área de stage)
modificado: README.md
alu@xdebian11:~/test-md-github$
```

commit

```
alu@xdebian11:~/test-md-github$ git commit -m "cambios en README para
demo"
Author identity unknown
*** Por favor cuéntame quien eres.
Corre
git config --global user.email "you@example.com"
git config --global user.name "Tu Nombre"
para configurar la identidad por defecto de tu cuenta.
Omite --global para configurar tu identidad solo en este repositorio.
fatal: no es posible auto-detectar la dirección de correo (se obtuvo
'alu@xdebian11.(none)')
alu@xdebian11:~/test-md-github$ git config user.email
"jgomez@iesromerovargas.com"
alu@xdebian11:~/test-md-github$ git config user.name "Jose Gomez"
alu@xdebian11:~/test-md-github$ git commit -m "cambios en README para
demo"
[main 64f7ed1] cambios en README para demo
1 file changed, 20 insertions(+)
alu@xdebian11:~/test-md-github$
```

push

```
alu@xdebian11:~/test-md-github$ git push
Enumerando objetos: 5, listo.
Contando objetos: 100% (5/5), listo.
Comprimiendo objetos: 100% (2/2), listo.
Escribiendo objetos: 100% (3/3), 431 bytes | 431.00 KiB/s, listo.
Total 3 (delta 0), reusado 0 (delta 0), pack-reusado 0
To github.com:angoies/test-md-github.git
c9a4725..64f7ed1 main -> main
alu@xdebian11:~/test-md-github$
```

