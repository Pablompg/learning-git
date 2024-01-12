# learning-git
Repository for teaching the basics of git and github

Access [learning-git.pablompg.com](learning-git.pablompg.com)

PPT: https://docs.google.com/presentation/d/1R028KEPas62j005SnG7IdUdtM-o7C0xqAT_KnBQtI6E/edit?usp=sharing

## Exercise
For all the following questions, explain the git command, and its options. The first one is done as an example.

* `git add`

Adds a change in the working directory to the staging area. You can add all changes in the working directory by using `git add .`. You can also just add a file by specifying the name and path of the file `git add <file_path>`. This DOES NOT commit the change.
* `git fetch`

Se utiliza para recuperar los cambios desde un repositorio remoto en el repositorio local. Se diferencia de git pull en que no realiza de forma automática un merge con la rama local. Con el comando `git fetch repo rama` recuperaremos los cambios en la rama del repositorio definidos.

Sus opciones principales son:

--all: Recupera los cambios en todas las ramas.
--prune: elimina las referencias locales que no existan en el repositorio remoto.
--dry-run: muestra los cambios que se descargarían sin aplicarlos
--tags: recupera las etiqutas del repositorio remoto, que son las referencias que apuntan a puntos concretos del historial. Se utilizan mucho para la publicación de versiones.
--set-upstream: define un upstream al realizar el fetch si no está definido previamente.(La primera vez que se inicie un repositorio).
* `git commit`

Se utiliza para registrar cambios en el repositorio local en el que se está trabajando. Es necesario haber añadido previamente esos cambios al área de preparación (Staging area) para poder realizar el comando commit.

Sus opciones principales son:

--all: añade al área de preparación automáticamente todos los cambios y luego los confirma por lo que no es necesario realizar el `git add` . El comando usado sería `git commit -a -m "Mensaje"` o `git commit -am "Mensaje"`. Esto solo será válido siempre y cuando los cambios estén siendo rastreados por git.
--m: añade un mensaje al commit. Este mensaje es siempre necesario.`git commit -m "Mensaje"`.
--amend: permite realizar cambios en el último commit que se haya realizado.
--C HEAD: sirve para utilizar el mensaje del commit más reciente de forma que el nuevo commit y el anterior compartan ese mensaje.
--patch: muestra una interfaz gŕafica para establecer el mensaje y seleccionar manualmente los cambios.

* `git branch -d | git branch -D`

Se utiliza para eliminar la rama local que se determine , con la fórmula `git branch -d rama`. Si el comando es `git branch -D rama` fuerza la eliminación de la rama incluso si hay cambios.

Sus opciones principales son:

--all: devuleve una lista de todas las ramas, locales y remotas
--remotes: devuleve un listado con las ramas que están en el repositorio remoto. Combinado con -d elimina ramas remotas con la sentencia `git branch -dr "Nombre Rama"`.
--move: mueve una rama especificada o le cambia el nombre a la rama utilizando `git branch -m "Nuevo nombre"`.
--copy: copia una rama

* `git reset`

Se utiliza para devolver el HEAD al punto especificado.

Sus opciones principales son:

--soft: no realiza el reset para el working tree ni el index file
--hard:
* `git revert`
* `git cherry-pick`
* `git rebase`
* `git merge`
* `git branch`
* `git clean`
