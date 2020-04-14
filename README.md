# Apriendiendo Git y Github

Hola, soy Josema

git config -l -> Lista las configuraciones de GITHUB
git config --global user.email "email@email.com" 

git log filename.txt -> Te da el historial de cambios con su serial number, el nombre del commit, etc.

git log --stat filename.txt -> Cambios especificos que se hicieron en cuales archivos a partir del commit 

git checkout SERIAL_NUMBER_COMMIT filename.txt (also known as VIAJAR EN EL TIEMPO) -> Sobreescribe el arhivo por la versión de este commit. Es decir, tengo el archivo actual historia.txt con el serial number abc3 y quiero volver a la versión primera de historia.txt, miro en el log su serial number el cual es abc1 y hago el comando. También se podría ejecutar de la siguiente manera: git checkout master filename.txt que es la última versión que se había commiteado o estaba en master. 

git rm
Este comando nos ayuda a eliminar archivos de Git sin eliminar su historial del sistema de versiones. Esto quiere decir que si necesitamos recuperar el archivo solo debemos “viajar en el tiempo” y recuperar el último commit antes de borrar el archivo en cuestión.
    - git rm --cached: Elimina los archivos del área de Staging y del próximo commit pero los mantiene en nuestro disco duro.
    - git rm --force: Elimina los archivos de Git y del disco duro. Git siempre guarda todo, por lo que podemos acceder al registro de la existencia de los archivos, de modo que podremos recuperarlos si es necesario (pero debemos usar comandos más avanzados).

git reset
Este comando nos ayuda a volver en el tiempo. Pero no como git checkout que nos deja ir, mirar, pasear y volver. Con git reset volvemos al pasado sin la posibilidad de volver al futuro. Borramos la historia y la debemos sobreescribir. No hay vuelta atrás

git reset HEAD -> lo único que haremos será mover estos cambios de Staging a Unstaged. Seguiremos teniendo los últimos cambios del archivo, el repositorio mantendrá el archivo (no con sus últimos cambios pero sí con los últimos en los que hicimos commit) y no habremos perdido nada.

git fetch -> Trae del repositorio remoto al local, únicamente.
git merge -> Unifica el repositorio local con el directorio de trabajo.
Para hacer ambos, se usan -> git pull

En el entorno de VIM  puedo usar ESC+i para escribir ..... escribimos ..... ESC+SHIFT+ZZ para save.
Q para salir de pantallas de git log

------------------------

RAMAS

git branch -> Muestra las ramas.
git branch name -> Crea una rama con ese name
git checkout name -> Para moverme a esa rama

Importante antes de hacer el checkout de ramas hay que hacer git add y git commit para no perder los cambios.

git merge -> Fusiona dos ramas. El merge hay que hacerlo desde la rama master para no perder el historial.

git merge cabecera -> Junta la rama cabecera a la master. Lo que hace es un commit a la master

------------------------

GITHUB

Ya tengo mi espacio de trabajo en local, con mi directorio, mis archivos. Ahora he creado un repositorio en Github y quiero traermelo. ¿Cómo lo hago?

git remote add origin https://github.com/josema-Dis/nombre-repositorio -> Me trae el repositoripo remoto de Github a mi directorio local.

git remote -> Me dices que existe origin
git remote -v -> Nos muestra que hay urls de Github para hacer fecth o push.

git pull origin master -> Me traigo primero el readme.md de Github a mi directorio local y dara un error por primera vez.

git pull origin master --allow-unrelated-histories 

git push origin master -> Git envia a Origin la rama master
