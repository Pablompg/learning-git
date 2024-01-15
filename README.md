# learning-git
Repository for teaching the basics of git and github

Access [learning-git.pablompg.com](learning-git.pablompg.com)

PPT: https://docs.google.com/presentation/d/1R028KEPas62j005SnG7IdUdtM-o7C0xqAT_KnBQtI6E/edit?usp=sharing

## Exercise
For all the following questions, explain the git command, and its options. The first one is done as an example.

* `git add`

Adds a change in the working directory to the staging area. You can add all changes in the working directory by using `git add .`. You can also just add a file by specifying the name and path of the file `git add <file_path>`. This DOES NOT commit the change.
* `git fetch` importa ficheros remotos sin modificar los cambios locales
Sus opciones principales son:

--all: Recupera los cambios en todas las ramas.
--prune: elimina las referencias locales que no existan en el repositorio remoto.
--dry-run: muestra los cambios que se descargarían sin aplicarlos
--tags: recupera las etiqutas del repositorio remoto, que son las referencias que apuntan a puntos concretos del historial. Se utilizan mucho para la publicación de versiones.
--set-upstream: define un upstream al realizar el fetch si no está definido previamente.(La primera vez que se inicie un repositorio).

* `git fake` incluye cualquier meme que quieras


* `git commit` confirma un cambio después de añadir al stage. Podrá ir seguido de atributos como -m para añadir un mensaje, -a para confirmar los cambios de todos los ficheros, --amend para modificar el mensaje del commit
* `git branch -d | git branch -D` se ejecuta desde otra rama. Le sigue el nombre de la rama elegida y se elimina
* `git reset` elimina los cambios. Puede ir seguido de --hard para eliminar cambios en el directorio de trabajo y en el stage. También puede utilizarse el atributo --soft para reubicar la posición del HEAD sin eliminar cambios. Puede añadirse otro atributo HEAD~n donde n es la posicion del commit respecto al último commit que ocuparía la posición 0.
* `git revert` permite deshacer las confirmaciones aplicando en un nuevo commit. De esta manera no se pierde la trazabilidad de los cambios.
* `git cherry-pick`permite aplicar las confirmaciones realizadas con el commit de una rama en otra
* `git rebase` permite incorporar los commits de una rama a continuación de los commits sobre la rama donde se hace el rebase. Puede añadirse el atributo squash para incorporar un commit unico que agultine los cambios.
* `git merge` permite fusionar los commits de una rama a otra con un nuevo commit (merge commit) en la rama de destino
* `git branch` muestra por consola la rama actual y aquellas que pueden utilizarse. Seguida del atributo -a/-all muestra las ramas disponibles y las eliminadas
* `git clean` limpia del directorio de trabajo los cambios que no han sido añadidos al stage.
