# Publicando nuestra web

## Contenidos

<!-- TOC depthFrom:4 depthTo:4 -->

- [EJERCICIO 1](#ejercicio-1)
- [EJERCICIO 2](#ejercicio-2)
- [EJERCICIO 3](#ejercicio-3)
- [EJERCICIO 4](#ejercicio-4)
- [EJERCICIO 5](#ejercicio-5)
- [EJERCICIO 6](#ejercicio-6)
- [EJERCICIO 7](#ejercicio-7)
- [EJERCICIO 8](#ejercicio-8)
- [EJERCICIO 9](#ejercicio-9)
- [EJERCICIO 10](#ejercicio-10)
- [EJERCICIO 11](#ejercicio-11)
- [EJERCICIO 12](#ejercicio-12)
- [EJERCICIO 13](#ejercicio-13)

<!-- /TOC -->

## Introducción

La terminal es una herramienta fundamental para el desarrollo front-end. Su finalidad es ejecutar comandos mediante instrucciones. Estos comandos serían similares a las interacciones que haríamos en una aplicación normal (clics, escribir en campos, cambiar de sección, etc.) pero en este caso se hacen escribiendo órdenes en una terminal de comandos. Muchas de las herramientas para programación están hechas sin interfaz por ser más sencillas, aprender a usar la terminal nos ayudará en el futuro a poder usar esas herramientas y mejorar nuestro flujo de trabajo gracias a ellas.

La terminal parece muy agresiva al principio pero poco a poco le iremos pillando cariño. Te permite hacer prácticamente todo lo que puedes hacer con la interfaz gráfica del sistema operativo y bastantes cosas más.

También vamos a aprender cómo funciona el control de versiones y cómo utilizarlo para ir, poco a poco, añadiéndolo a nuestro flujo de trabajo. En esta sesión vamos a ver las dos herramientas que utilizaremos para gestionar las versiones de nuestro proyecto, git y GitHub.

_Git_ será la herramienta que utilizaremos para realizar un control de versiones sobre nuestros archivos. Es una herramienta que se utiliza a través de la línea de comandos de nuestro ordenador, es decir, para trabajar con git escribiremos comandos en nuestra Terminal.

GitHub es la plataforma social más famosa a la hora de publicar y colaborar en desarrollo de código. Además, permite guardar en un servidor nuestro código y sincronizarlo con el código que tendremos en nuestro ordenador. Todo esto lo hace apoyándose en git.

Otra cosa que veremos durante la sesión es el servicio de GitHub Pages que ofrece GitHub. Este servicio nos permite publicar nuestro código como si se tratase de un sitio web y que la gente pueda verlo en Internet desde cualquier parte del mundo. Al final de esta sesión veremos cómo habilitarlo para poder mostrar al mundo nuestra primera página web.

## Resumen de la sesión

En esta sesión se intenta acercar el control de versiones para que lo acabemos incluyendo en nuestro flujo de trabajo.

Además presentamos la plataforma GitHub y su servicio de hosting: GitHub Pages.

## ¿Para qué sirve lo que vamos a ver en esta sesión?

En la terminal hoy solo vamos a aprender a movernos por las carpetas y crear algún archivo pero más adelante será una herramienta fundamental al trabajar en grupo y con control de versiones.

Por ahora solo hemos empezado a arañar el mundo front-end pero el uso de un control de versiones nos ofrece algo que antes no teníamos:

- Si me dejé el trabajo en casa, ¿cómo puedo continuar trabajando?
- ¿Cómo puedo deshacer un cambio que acabo de realizar?
- ¿Cómo puedo saber de forma clara en qué punto hice un cambio concreto?
- ¿Cómo trabajo con otros sin que sea un caos y nos estemos pisando todo el rato?

La solución a todas esas preguntas es simple: usando un control de versiones.

Por su parte, GitHub, como hemos comentado, es una plataforma web que nos ofrece una serie de funcionalidades y herramientas para facilitarnos nuestro trabajo a la hora de realizar y mantener código. Algunas de las posibilidades que ofrece GitHub son las siguientes:

- Usarlo como servidor donde sincronizar y hacer una copia de seguridad de nuestro proyecto
- Formar parte de una red social que gira en torno a la programación, con perfil de usuario, posibilidad de interactuar con otros usuarios y posibilidad de usarla como portafolio de nuestros trabajos de desarrollo web
- Acceder a herramientas para gestionar mejor los proyectos y facilitar el desarrollo del código
- Tener una plataforma donde alojar nuestro sitio web y poder mostrarla al resto del mundo de forma sencilla (GitHub Pages)

## ¿En qué casos se utilizan?

Git se utiliza tanto en los casos más simples, como un pequeño proyecto o un archivo de configuración; hasta una locura con varios compañeros y que luego os vaya a hacer ricos. Siempre y cuando queráis (y podáis) tenerlo subido y disponible para todos.

Nosotros lo utilizaremos siempre que queramos llevar un control de los cambios que hemos hecho en un proyecto para no perder información. Al principio será sólo en determinados proyectos de código, pero a medida que le vayáis cogiendo el gustillo, empezaréis a sentiros vacías sin él. En Adalab, por ejemplo, lo utilizamos para gestionar el contenido del curso. Sí, este contenido que estáis leyendo ahora mismo está creado utilizando git :)

Por poneros un ejemplo que hayáis vivido en vuestra piel, tendría sentido utilizar git para los pequeños ejercicios que hacemos para practicar los conocimientos. Pero sobre todo que tendría sentido usar este control de versiones para gestionar el proyecto grupal del primer módulo.

Respecto a GitHub, lo utilizaremos siempre que queramos compartir un código con el resto de la comunidad o si queremos tenerlo en lo que se llama "la nube" para no perderlo y que cualquier persona con acceso y permisos de escritura pueda editarlo desde cualquier parte del mundo.

Por último, GitHub Pages, al ser un servicio gratuito y sencillo para publicar páginas, es un recurso muy útil si queremos colgar en Internet algún proyecto de forma gratuita.

Es importante saber que todos los servicios de GitHub son gratuitos tanto repositorios públicos como privados. Por el momento como queremos darle visibilidad al código y que otras personas puedan verlo, no tendremos ningún problema en que nuestro código sea público.

## Terminal

### Introducción a la Terminal

La terminal o consola es una de nuestras herramientas principales en el desarrollo front. Nos permite comunicarnos con el sistema mediante pequeñas instrucciones de texto (las llamamos _comandos_) sin necesidad de una interfaz gráfica.

La terminal nos permite obtener información del sistema, realizar tareas y hasta automatizarlas, y ganar en productividad.

La terminal de nuestro ordenador tiene este aspecto:

![Terminal de ubuntu](assets/images/1-7/terminal-ubuntu.png)

En esta ventana iremos escribiendo nuestros comandos para interactuar con el ordenador o con aplicaciones que no tengan una interfaz gráfica.

Por defecto la terminal nos mostrará una línea (el _prompt_) a partir de la cual podremos escribir nuestros comandos.

Normalmente nuestro prompt tendra este aspecto:
**usuario@nombre-de-equipo: ruta por defecto \$**

```shell
ubuntu@ubuntu: ~$
```

Esto nos dice que el usuario de nuestro equipo es **ubuntu**, que nuestro equipo se llama **ubuntu** y que estamos en la carpeta home del usuario (que se representa con `~`).

### Comandos básicos de GNU/Linux

**PWD**

Principalmente usaremos la terminal para movernos por el sistema de archivos del ordenador. Así que es fundamental saber dónde estamos en cada momento. El comando `pwd` (_Print Working Directory_) se encargará de mostrarnos en qué carpeta nos encontramos.

```shell
pwd
```

> **NOTA**: Muchas veces nos encontraremos los comandos que tenemos que introducir precedidos por el símbolo `$`, pero no hay que escribirlo.

Devolverá la ruta absoluta de la carpeta en la que estemos, con este aspecto:

```shell
/user/nombre-de-usuario
```

Esto es una ruta absoluta, que se construye a partir de la carpeta raíz de nuestro equipo, representada por el carácter inicial `/`. Nos estaría indicando que nos encontramos en la carpeta `nombre-de-usuario`, que está dentro de `user`, que está en la carpeta raíz de nuestro equipo.

Las rutas pueden ser _absolutas_, como la que nos devuelve el comando `pwd`, y empiezan por `/`. También pueden ser _relativas_, que usaremos más adelante.
Las relativas usan los caracteres especiales `..` para referirse a la carpeta madre de nuestra carpeta actual, o `.` (o nada) para referirnos a una carpeta que está dentro de nuestra carpeta actual.

```shell
../carpeta-madre
```

```shell
./carpeta-hija
carpeta-hija
```

**LS**

El comando `ls` nos muestra un listado de los archivos y carpetas que hay en nuestra carpeta actual.

Podemos usar la opción especial `ls -a` para listar también los ficheros y carpetas ocultos, que su nombre comienza por `.` y por defecto no se ven.

**CD**

El comando `cd` (Change Directory) nos ofrece diferentes posibilidades a la hora de cambiar de carpeta:

```shell
cd nombre-de-carpeta
```

Nos permite entrar en la carpeta `nombre-de-carpeta` que estaría en nuestra carpeta actual.

Podemos encadenar varios nombres de subcarpetas separadas por `/` para llegar hasta una ruta más profunda:

```shell
cd nombre-de-carpeta/carpeta-hija/carpeta-nieta
```

> **NOTA**: la terminal de comandos nos permite autocompletar los comandos como `cd` usando la tecla tabulador (Tab); por ejemplo, si escribimos `cd a` y damos a tabulador, aparecerán las opciones de carpetas o ficheros en la carpeta actual que comienza por 'a'.

```shell
cd /ruta/absoluta/a/una/carpeta
```

También podemos escribir la ruta absoluta desde la raíz de nuestro equipo `/` a la carpeta a la que queremos entrar.

```shell
cd
```

`cd` solo nos devuelve a la carpeta de nuestro usuario (esta es la localización por defecto donde se abrirá nuestra terminal)

```shell
cd ..
```

`..` nos permite subir un nivel, esto es, ir a la carpeta que contiene nuestra carpeta actual

```shell
cd -
```

Este comando permite "deshacer" el último cd realizado: vuelve a la localización anterior al último cambio de carpeta.

**MKDIR**

Nos permite crear una carpeta. PERO NO ENTRA EN LA CARPETA NUEVA.

Si no especificamos una ruta se creará en la localización actual pero se puede indicar la ruta usando `/` y `..`. Por ejemplo, vamos a crear una carpeta "proyecto" en la carpeta madre de la carpeta actual:

```shell
mkdir ../proyecto
```

**TOUCH**

Nos permite crear un nuevo archivo.

Si no especificamos una ruta se creará en la localización actual pero se puede indicar la ruta usando `/` y `..`. Por ejemplo, vamos a crear un archivo "index.html" en la carpeta actual (estará vacío):

```shell
touch index.html
```

**CLEAR**

A veces va a pasar que hemos introducido muchos comandos y sería genial poder "limpiar" la ventana. Para eso existe el comando `clear`, que nos limpia la ventana de la terminal.

**CP y MV**

Si queremos copiar o mover archivos usaremos los comandos `cp` o `mv`. El formato será `cp`/`mv` archivo-de-origen archivo_de_destino.

Vamos a mover el archivo index.html de nuestra carpeta actual a la carpeta madre:

```shell
mv index.html ../index.html
```

> **NOTA**: `mv` también sirve para renombrar ficheros o carpetas

**Abrir nuestra carpeta actual en el explorador de archivos desde la terminal**

A veces nos interesará abrir nuestra carpeta actual en el explorador de archivos (que en Ubuntu se llama Nautilus) y esto se puede hacer fácilmente desde la terminal con el comando:

```shell
nautilus .
```

y sí, `$ nautilus ..` nos abrirá nuestra carpeta madre en el explorador de archivos ;)

> **NOTA**: en Mac podemos abrir el explorador de archivos (Finder) con `open`

> **NOTA**: igual que con `nautilus` podemos abrir el explorador de archivos en una ruta, también podemos abrir programas como VSCode en una ruta. Por ejemplo, con `code .` abrimos una ventana de Code en la carpeta actual. Para que funcione también en Mac debemos [instalar el comando con estas instrucciones](https://code.visualstudio.com/docs/setup/mac#_launching-from-the-command-line).

**Volver a los últimos comandos**

Para volver a los últimos comandos ejecutados podemos usar la tecla de flecha para arriba ⬆️.

Si queremos buscar un comando en el historial, podemos usar Ctrl + R y comenzar a escribir el comando para buscarlo.

**Ayuda y opciones**

Si no sabemos cómo funciona un comando pediremos ayuda al terminal. Por ejemplo para saber cómo funciona el comando LS escribimos:

```shell
ls --help
```

El terminal mostrará una explicación de cómo se utiliza el comando y las opciones que se pueden utilizar. Con esta información sabremos que para listar el contenido de un directorio en orden inverso podemos escribir:

```shell
ls --reverse
```

o

```shell
ls -r
```

#### EJERCICIO 1

Desde la terminal, id a vuestra carpeta de documentos y cread la siguiente estructura de carpetas y archivos (vacíos):

```txt
nombre
    datos
        mis-datos.txt
    proyecto
        ruta-del-proyecto.txt
```

- En el archivo **mis-datos.txt** vamos a escribir el Nombre y la comida favorita.
- En el archivo **ruta-del-proyecto.txt** pondremos la ruta del archivo desde nuestra carpeta de `Documentos`
- Mover los dos archivos a la carpeta principal, que sería **nombre**

\_\_\_\_\_\_\_\_\_\_

#### EJERCICIO 2

Desde la terminal, vamos a crear un nuevo proyecto en nuestra carpeta de proyectos que se llame `rutas-relativas`, con las carpetas `images` y `styles`. Y los archivos `index.html` (en la raíz del proyecto), `style.css` (en la carpeta `styles`) y `imagen-de-prueba.jpg` (en la carpeta `images`, la podéis descargar desde [este enlace](assets/images/1-7/imagen-de-prueba.jpg)).

Ahora, editando el archivo `index.html` en VSCode se tiene que ver la imagen de dos formas:

1. Con un `<img>`
2. Como fondo de un `div` del mismo tamaño que la imagen

¿Cómo es la ruta de ambas imágenes? ¿Absoluta? ¿Relativa?
¿Es diferente en los dos casos? ¿Por qué?

\_\_\_\_\_\_\_\_\_\_

## Git

### Introducción a git

Vamos a ver una pequeña introducción a git, para ello hemos seleccionado el siguiente video ya que pensamos que explica de forma breve y sencilla qué es git y algunos de sus conceptos básicos.

- [1.- Curso Git - Introducción a Git](https://www.youtube.com/watch?v=zH3I1DZNovk)

### Configurar git en nuestro ordenador

Vamos a ver cómo configurar git en nuestro ordenador. Para llevarlo a cabo, primero comprobaremos si tenemos instalada una versión reciente de git.

> NOTA:
> Para comprobar si tenemos instalado git en nuestro ordenador, debemos abrir la Terminal y ejecutar el comando `git --version`. Esto mostrará el texto `git version` seguido de la versión de Git que tenemos instalada. Para poder trabajar de forma correcta, lo indicado sería que tuviésemos una versión igual o posterior a la `2.11.0`.

**1. Creamos una cuenta en [GitHub](https://github.com). Poniendo nuestro usuario de GitHub en minúsculas**

> Esto es súper importante y lo agradeceréis más adelante.

**2. Añadimos nuestro nombre a la configuración de Git**

Abrimos la aplicación de la terminal e introducimos el siguiente comando, tal y como se muestra abajo, sustituyendo `"John Doe"` por vuestro nombre. Una vez lo hayamos introducido, pulsamos intro para que se ejecute.

**Importante:** Escribiremos nuestro nombre entre comillas para evitar problemas a la hora de ejecutar el comando.

```shell
git config --global user.name "John Doe"
```

**3. Configuramos nuestro email para trabajar con Git**

Ahora introducimos el siguiente comando para guardar la configuración de nuestro email:

```shell
git config --global user.email "johndoe@example.com"
```

Sustituiremos en este caso `"johndoe@example.com"` por el email que **hemos utilizado para crear nuestra cuenta de GitHub**.

**Nota:** Es importante que el email coincida con el que hemos utilizado en GitHub, ya que se utilizará para comprobar nuestros credenciales a la hora de subir información a un repositorio en esta plataforma.

**4. Añadimos la configuración para que se guarde nuestra contraseña para GitHub**

Por defecto, cada vez que intentamos conectarnos con GitHub, el servidor de GitHub nos pedirá la contraseña de nuestro usuario. Como vamos a subir y descargar cambios de GitHub de forma constante, puede ser un poco molesto tener que introducir la contraseña cada vez que queramos conectarnos con el servidor. Para evitar esto, vamos a almacenar la contraseña de forma segura en nuestro ordenador.

**En Ubuntu**

Para poder almacenar la contraseña de GitHub en Ubuntu, realizaremos los siguientes comandos uno por uno:

```shell
sudo apt-get install libsecret-1-0 libsecret-1-dev
```

Nos solicitará una contraseña, aquí debemos introducir la contraseña de nuestro ordenador, no la de GitHub.

```shell
cd /usr/share/doc/git/contrib/credential/libsecret
```

```shell
sudo make
```

```shell
cd -
```

```shell
git config --global credential.helper /usr/share/doc/git/contrib/credential/libsecret/git-credential-libsecret
```

Al hacer esto, la próxima vez que introduzcamos nuestra contraseña de GitHub, esta se almacenará de forma segura en nuestro ordenador y no será necesario volver a introducirla de nuevo.

Una vez hayamos realizado ese paso, no necesitaremos hacer ningún cambio más.

**En Windows 10**

Para poder almacenar la contraseña de GitHub en Windows, realizaremos los siguientes comandos uno por uno, en la terminal de Ubuntu que instalamos el primer día del curso en la instalación de ordenadores:

```shell
sudo apt-get install libsecret-1-0 libsecret-1-dev
```

Nos solicitará una contraseña, aquí debemos introducir la contraseña que pusimos cuando instalamos Ubuntu dentro de Windows, no la de GitHub.

```shell
cd /usr/share/doc/git/contrib/credential/libsecret
```

```shell
sudo make
```

```shell
cd -
```

```shell
git config --global credential.helper "/mnt/c/Program\ Files/Git/mingw64/libexec/git-core/git-credential-manager.exe"
```

Al hacer esto, la próxima vez que introduzcamos nuestra contraseña de GitHub, esta se almacenará de forma segura en nuestro ordenador y no será necesario volver a introducirla de nuevo.

Una vez hayamos realizado ese paso, no necesitaremos hacer ningún cambio más.

**En Mac**

Para poder almacenar la contraseña de GitHub en Mac, simplemente ejecutamos el siguiente comando:

```shell
git config --global credential.helper osxkeychain
```

Una vez hayamos realizado ese paso, no necesitaremos hacer ningún cambio más.

**5. Configuramos el editor de texto para trabajar con Git**

**Nano** es un editor de texto que suele venir por defecto en Ubuntu en la terminal. Queremos que sea nuestro editor por defecto para trabajar con Git. Para ello abrimos la terminal e introducimos el siguiente comando. Una vez lo hayamos introducido, pulsamos intro para que se ejecute.

```shell
git config --global core.editor nano
```

El editor por defecto en otros sistemas operativos es otro, pero en este curso vamos a utilizar siempre Nano para trabajar todas de la misma manera.

### Cómo trabajar con git

Para trabajar con git lo haremos usando comandos a través de la Terminal, como comentábamos en la introducción de esta sesión. Para ello tendremos que aprender unos comandos básicos.

Una vez configurado git en nuestro equipo tendremos que activar el control de versiones en nuestro proyecto, esto lo haremos con `git init`. Este comando lo usaremos solo una vez en la carpeta de nuestro proyecto y activa que se controle cada cambio que hacemos a nuestros archivos del proyecto.

A partir de este momento, cada vez que hagamos cambios, git sabrá qué archivos hemos modificado.

En cualquier momento podremos pedir que nos diga en qué estado está el proyecto con `git status`, lo que nos dirá si hemos cambiado archivos.

Normalmente trabajaremos con cambios cortos o tareas pequeñas, y cuando hayamos terminado, querremos indicarle a git que ya hemos terminado un paquete de cambios, para lo que tenemos dos comandos:

1. `git add -A` para añadir los archivos que hemos modificado. Una vez añadidos git sabrá qué cambios hemos hecho.
1. `git commit -m "Mensaje"` nos permite crear como un paquete de cambios y "guardarlo en nuestro sistema de versiones", nos dejará escribir un mensaje corto para asociarlo al paquete de cambios o _commit_.
1. Si queremos ver la lista de commits realizados en un proyecto usaremos `git log`. Para salir del listado usamos la tecla `q`.

En el video que añadimos a continuación se explican los comandos básicos para empezar a trabajar con git.

- [3.- Curso Git - Nuestro primer proyecto](https://www.youtube.com/watch?v=vH9pkFf1D7M)

> **Nota:** En el video pone los mensajes de los commits en español pero nosotros los escribiremos en inglés.

**Mensaje del commit**

Es importante acompañar el commit con un mensaje. Este mensaje debe ser suficientemente corto para que no sea una locura leerlo y, a la vez, explique qué cambio se ha hecho de forma clara.

Normalmente trabajaremos con otras compañeras en un mismo proyecto y será fundamental que todas entiendan qué se ha hecho en cada paso para poder trabajar de forma más rápida y no tener que estar preguntando qué es cada cosa.
Crear mensajes claros en los commits, nos servirá también para que si volvemos a ver un commit del pasado, podamos entender qué es lo que hicimos.

A la hora de escribir un mensaje para un commit hay múltiples maneras de plantearlo e infinidad de guías. Como estamos empezando tengamos en cuenta sólo la siguiente serie de normas para crear un mensaje lo suficientemente bueno:

- Debe estar escrito en inglés
- Tiene que ser corto. Máximo 72 caracteres
- Debe explicar brevemente y a nivel general los cambios que se han hecho (añade el footer, corrige los enlaces del artículo, etc.)
- No tiene que detallar los cambios hechos en el código, sino en general. Recordemos que ya tenemos un control de versiones que muestra, exactamente, qué se ha hecho. (Ejemplo: no pongáis "Add 2 paragraph tags", poned mejor "Add introduction text")
- Usaremos el imperativo (Ejemplo: `Change header styles` - Cambia los estilos del header) para decir qué hace el commit.

Un ejemplo de un buen commit:

```
$ git commit -m "Fix typo in article title"
```

#### EJERCICIO 3

Vamos a crear nuestro primer proyecto con git, al que llamaremos `testing-git`. Dentro de él, crearemos un archivo HTML con un título HEAD en el que ponga "Testing Git" y un `h1` con el mismo texto. Además, crearemos un archivo para los estilos (`main.css`) dónde añadiremos un estilo para que la familia de texto que se use en la web sea `sans-serif`. Organizaremos el proyecto siguiendo la estructura de siempre:

```txt
testing-git
    styles
        main.css
    images
    index.html
```

Una vez creado el proyecto con el HTML y el CSS indicado. Inicializa el repositorio Git en el proyecto (asegurate de que estás en la carpeta testing-git), añade los archivos y haz el primer commit con el mensaje `Initial commit`

```shell
git init
```

```shell
git add -A
```

```shell
git commit -m "Initial commit"
```

\_\_\_\_\_\_\_\_\_\_

#### EJERCICIO 4

Modificar el archivo `index.html` para que en el título de la página ponga "My first Git project" y en el texto de la cabecera aparezca una sonrisa `:)`. Añadir los cambios y hacer un commit para guardarlos.

**Nota:** El mensaje del commit deberá explicar de forma clara los cambios que hemos realizado

\_\_\_\_\_\_\_\_\_\_

#### EJERCICIO 5

Vamos a realizar un tercer cambio dónde añadiremos un archivo `README.md` en la raíz de nuestro proyecto. Este archivo se utiliza para poner información acerca de nuestro código y, por defecto, la web GitHub lo muestra en la página principal de nuestro proyecto. Dentro de ese archivo escribiremos el siguiente texto:

```markdown
## My first Git project

Dummy project to learn Git basics
```

**Nota:** El mensaje del commit deberá explicar de forma clara los cambios que hemos realizado

\_\_\_\_\_\_\_\_\_\_

## GitHub

Como hemos explicado anteriormente, GitHub es una plataforma de desarrollo colaborativo para alojar proyectos utilizando el sistema de control de versiones de git. Está muy enfocada a proyectos de código abierto y la verdadera fuerza de GitHub está en la comunidad tan grande que se ha montado sobre la idea de código abierto u _open source_ :)

#### EJERCICIO 6

Poneros, ambas compañeras, una imagen de perfil en vuestras cuentas de GitHub. No tiene por qué ser una fotografía.

\_\_\_\_\_\_\_\_\_\_

Hasta ahora sabemos crear un repositorio git local, ahora vamos a ver cómo creamos un repositorio remoto en GitHub, de esta forma podremos acceder al código desde cualquier equipo y podremos colaborar con nuestras compañeras.

Para ello, nos vamos a nuestro perfil y buscamos el botón `+` para crear un nuevo repositorio:

![Nuevo repositorio](assets/images/1-7/github-repo-1.png)

Rellenamos los datos que nos piden: nombre del repositorio, descripción y marcamos que queremos inicializarlo con un `Readme.md`:

![Nuevo repositorio](assets/images/1-7/github-repo-2.png)

Una vez creado, nos llevará a la página principal de nuestro repo donde podremos conseguir la url para descargarlo en nuestro equipo. Esta es una descarga especial que llamamos, clonar, que nos hace una copia local del proyecto conectada con la versión remota.

![Nuevo repositorio](assets/images/1-7/github-repo-3.png)

Ahora, con esta url podemos irnos a nuestra terminal y clonarlo con `git clone`:

![Nuevo repositorio](assets/images/1-7/github-repo-4.png)

Esto nos generará una carpeta con nuestro proyecto. **Recordad que crea la carpeta pero no nos mete dentro** por lo que tendremos que usar el comando `cd` de nuestra terminal para cambiar la ruta actual.

> **Nota**:
> Por defecto git nos creará una carpeta con un nombre automático, si queremos un nombre específico para la carpeta de nuestro proyecto podemos declararlo tras la url que nos da GitHub:

```shell
git clone url-del-repositorio-que-me-da-github nuevo-nombre-de-carpeta
```

Ahora tenemos un repositorio local en la carpeta en la que hemos clonado nuestro nuevo repositorio remoto.
Si accedemos a la carpeta, dentro debería estar el archivo README.md.

Podemos crear archivos y/o realizar cambios sobre los existentes, guardarlos en local (Ctrl+S o Cmd+S), añadirlos para que git sepa que cambios hemos hecho (`git add -A`), commitearlos con un mensaje (`git commit -m "Add main css file"`), y finalmente hacer un _push_ al repositorio remoto de GitHub (`git push origin master`) para guadar nuestros cambios allí.

### ¿Y si ya tengo un proyecto con Git en local?

A la hora de conectar el repo local y el remoto lo mas cómodo es empezar creando el repo en GitHub, clonándolo y seguir a partir de ahí con la conexión ya hecha. Pero puede pasar que ya tuviésemos un proyecto en local que hubiésemos inicializado con `git init`, en este caso seguiremos estos pasos:

1. Creamos un repo vacío en GitHub **SIN INICIALIZARLO CON README.md, GITIGNORE O LICENCIA**.
2. Esto nos llevará a una página diferente con las instrucciones para conectar un repo local con nuestro repo remoto:

![Nuevo repositorio](assets/images/1-7/github-repo-5.png)

3. Copiamos la línea con `git remote add origin url-del-repositorio-que-me-da-github`
4. Desde la terminal, nos vamos a la carpeta de nuestro proyecto que ya tiene inicializado un repo local y ejecutamos la línea que hemos copiado. Esto conectará los dos repos.

En el video que mostramos a continuación se hace un pequeño tour alrededor de la plataforma para ver cómo funciona y las funcionalidades que ofrece. En el video pone el nombre del repositorio con mayúsculas y minúsculas, nosotros lo pondremos en minúsculas y con el texto separado por guiones, como hacemos con las carpetas de nuestros proyectos. En el video también explica ramas, pero lo ignoraremos. De momento solo vamos a trabajar con una rama (`master`), más adelante veremos cómo es el flujo a la hora de trabajar con varias ramas, pero vayamos poco a poco.

> **Nota:**
> Sólo veremos hasta el min 21:34. Porque en el resto del video habla de cosas que no vamos a aprender por el momento.

- [Curso Git - Empezando con GitHub](https://www.youtube.com/watch?v=Qn186NyDqOk)

#### EJERCICIO 7

Vamos a:

1. Crear un proyecto vacío en GitHub. Le pondremos como nombre `testing-git`.
1. Añadimos el repositorio que acabamos de crear como repositorio remoto en nuestro proyecto usando `git remote` como se muestra en el video.
1. Hacer _push_ para mandar la info del proyecto al repositorio remoto y, de esta forma, almacenar los datos del proyecto en GitHub. Comprobar tras hacerlo que, al abrir la página del proyecto en GitHub, se muestran los cambios que hemos realizado en nuestro ordenador.
1. Realizar un cambio en el CSS del proyecto para que el texto de la cara sonriente se muestre centrado vertical y horizontalmente en la página.
1. Una vez que estemos conforme con nuestro tipo sonriente, haremos un commit para añadir el cambio a nuestro repositorio y otro push, para sincronizar los cambios de nuestro repositorio local con los del remoto y, de esta forma, subir los cambios a GitHub.

\_\_\_\_\_\_\_\_\_\_

#### EJERCICIO 8

Puesto que trabajamos en parejas o en grupos queremos trabajar con el mismo código que tienen nuestras compañeras. Por ello si una compañera sube un cambio de código a GitHub (con `git push`) queremos poder descargarlo a nuestro ordenador (con `git pull`). Para ello:

1. Crear un proyecto vacío en GitHub. Le pondremos como nombre `testing-git-pull`. En este proyecto vamos compartir código entre varias compañeras.
1. Clonar el proyecto en ambos ordenadores (el tuyo y el de tu compañera) con `$ git clone url-del-repositorio-que-me-da-github` (como se explica en ejercicio 6).
1. Una de las compañeras debe añadir el fichero `index.html` en la raíz del proyecto.
1. La compañera que haya hecho el cambio anterior debe hacer un commit y luego un push para subir el cambio a GitHub.
1. Después, el resto de compañeras debe hacer `git pull` (desde dentro de la carpeta del proyecto) para descargarse los cambios a su ordenador.
1. Abrir el proyecto con VSCode para comprobar que, efectivamente, los cambios se han descargado desde GitHub.
1. Ahora otra compañera puede hacer otro cambio en `index.html`, hacer otro commit y otro push.
1. Repetir los pasos del 4 al 7 tantas veces como se quiera.

> **NOTA:** Cada vez que ejecutamos un comando de Git en la terminal es muy interesante leer la información que aparece en la terminal para saber lo que está haciendo Git.

## GitHub Pages

Como hemos comentado previamente, GitHub ofrece un servicio llamado [GitHub Pages](https://pages.GitHub.com) que pueden utilizar los usuarios como hosting gratuito para los proyectos que estén alojados en GitHub.

Un hosting es un servicio de almacenamiento de datos para poder tener tu web en un servidor y que esté disponible en Internet y esto es lo que ofrece exactamente GitHub Pages.

#### EJERCICIO 9

Desde la página de nuestro proyecto `testing-git` en GitHub, activar GitHub Pages.

**Pista:** Hay que ir a la pestaña _settings_ del proyecto ;)

\_\_\_\_\_\_\_\_\_\_

## Github Classroom

GitHub Classroom es un "módulo" de GitHub que permite automatizar el control de acceso y la creación de repositorios. Durante este curso lo usaremos para asignar ejercicios.

Classroom permite asignar repositorios vacíos o con un código inicial.

#### EJERCICIO 10

Haz clic en el siguiente enlace [https://classroom.github.com/a/cdZUSdeT](https://classroom.github.com/a/cdZUSdeT) para crear tu primer repositorio a través de GitHub Classroom, y luego:

1. Clónalo en tu equipo
2. Crea un archivo `README.md`
3. Dentro, escribe tu nombre precedido de un `#`: `# PEPA HERRERA`
4. Haz `add` y `commit`
5. Haz un `push` al repo remoto :)

\_\_\_\_\_\_\_\_\_\_

## Más ejercicios de la terminal

#### EJERCICIO 11

A través de la terminal entra en la carpeta del ejercicio 1 y investiga el comando `ls` para conseguir:

- Listar el contenido de la carpeta para ver los nombres, propietarios y tamaño de los ficheros y carpetas.
- Listar el contenido de la carpeta para mostrar solo el nombre de los ficheros y carpetas en formato columna.
- Listar (con un solo comando) el contenido de la carpeta para ver los nombres, propietarios y tamaño de los ficheros y carpetas, incluyendo las subcarpetas y subarchivos.
- Repertir los ejercicios anteriores en la carpeta del ejercicio 7, mostrando también los archivos y carpetas ocultas.

En cada caso mira detenidamente toda la información que muestra la columna.

\_\_\_\_\_\_\_\_\_\_

#### EJERCICIO 12

A través de la terminal:

- Copia la carpeta `rutas-relativas` del ejercicio 2 en la carpeta `rutas-relativas-2`.
- Copia la carpeta `rutas-relativas` del ejercicio 2 en la carpeta `rutas-relativas-3` con la opción `verbose` y observa qué aparece en la terminal.

\_\_\_\_\_\_\_\_\_\_

#### EJERCICIO 13

A través de la terminal:

- Renombra (o mueve) la carpeta `rutas-relativas-2` del ejercicio 12, y ponle el nombre `nuevas-rutas-relativas`.

\_\_\_\_\_\_\_\_\_\_

## Recursos extra

### Personaliza la terminal

- [Prompt coloreado](https://www.howtogeek.com/307701/how-to-customize-and-colorize-your-bash-prompt/)
- [Prompt con información del repo GIT](https://sujipthapa.co/blog/git-pro-tip-show-your-branch-on-linux-ubuntu-terminal)

### Pro Git

Como recurso extra para aprender Git, el libro de "Pro Git" es uno de los mejores. Está escrito por dos desarrolladores que trabajaron en implementar libgit, el sistema que utiliza GitHub en el núcleo de su plataforma para lidiar con Git. Aparte, ambos han formado parte del desarrollo de Git y la comunidad que mantiene este software, por lo que saben muy bien de lo que hablan. El libro está explicado de forma sencilla y fácil de entender y es gratuito.

**Nota:** Es un libro bastante denso pero los capítulos 1 y 2 se centran en lo básico, por lo que puede ser interesante leer estos y en el futuro leer el resto.

- [Enlace a la página del libro Pro Git (versión inglesa y más actual)](https://git-scm.com/book/en/v2)
- [Enlace a la página del libro Pro Git (versión española, menos actual y no disponible para descargar)](https://git-scm.com/book/es/v2)
