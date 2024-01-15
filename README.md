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

--soft: no realiza el reset para el directorio de trabajo ni el índice. Es como deshacer la instrucción de `git commit`, pero no `git add`.
--mixed: es la opción por defecto. Cambia el índice al commit específico pero no modifica el directorio de trabajo. Es como desahacer `git commit` y `git add`.
--hard: en este caso se realiza el reset para el directorio de trabajo y para el índice, eliminando de los archivos los cambios que se hayan producido. No elimina archivos que se hayan creado entre HEAD y el commit seleccionado.
* `git revert`

Se utiliza para devolver HEAD a un punto específico pero como si fuese un cambio más del historial, creando un commit para ello.

Sus opciones principales son:

-n o --no-commit: realiza la operación sin crear un commit, lo que permite continuar haciendo cambios hasta que finalmente se realice el commit.
--mainline parent-number: se utiliza para deshacer cambios como consecuencia de un merge, especificando la rama principal a la que se llevan los cambios.
--edit: abre el editor de texto para editar el mensaje del commit de revert.
--abort: abandona la operación revert antes de su finalización, por ejemplo, después de un `git revert -n`.

* `git cherry-pick`

Se utiliza para aplicar los cambios producidos por un commit en concreto de una rama en la rama de trabajo.

Sus opciones principales son:

--edit: abre el editor de texto para editar el mensaje del commit de cherry-pick.
-x: Agrega un mensaje al final del commit para indicar que fue realizado mediante el comando cherry-pick.
--no-commit: al igual que en git revert, deja la ejecución del comando pendiente tras realizar los cambios para poder seguir ejecutando cambios hasta que se realice el `git commit` correspondiente

* `git rebase`

Tiene dos funcionalidades:

La primera, que se ejecuta sobre la misma rama, sirve para combinar varios commit seguidos. Todos aquellos commits sobre los que se elija la opción squash quedarán incluidos en el siguiente commit que se defina como pick. Para ello se abra un editor de texto que permite la selección.

Esta opción debe ejecutarse con la opción - i `git rebase -i HEAD~numero comentarios`.

La segunda, consiste en la fusión de una rama sobre otra, uniendo todos los commit de la rama secundaria en uno solo.

Sus opciones principales son:

--interactive: permite reorganizar, editar o eliminar commits durante la ejecución de rebase.
--continue: Después de resolver los conflictos, permite continuar.
--abort: al igual que en `git revert`, aborta el proceso de rebase antes de su confirmación.


* `git merge`

Se utiliza para combinar cambios de una rama con otra.

Sus opciones principales son:

--squash: Junta los distintos commit durante la fusión.
--no-commit: Al igual que en los otros comandos, esta opción sirve para no finalizar automáticamente el merge, dejándolo pendiente de un commit.
--abort: Sirve para cancelar el proceso al igual que para los otros commit.

* `git branch`

Se utiliza para trabajar con las distintas ramas del repositorio. Dependiendo de la opción, se gestionan las ramas de forma distinata.

Sus opciones principales son:

--all: muestra todas las ramas locales y remotas como si fuesen un listado.
--delete: borra la rama local que se le indique `git branch -d nombreRama`.
-m: renombra una rama `git branch -m nombreViejo nombreNuevo`.
-r: muestra las ramas remotas como listado.
--merged: del listado de ramas, muestra las ramas fusionadas con la principal.
--no-merged: del listado de ramas filtra las ramas no fusionadas con la principal.


* `git clean`

Se utiliza para limpiar el directorio de trabajo para eliminar archivos que no están bajo la supervisión del control de versiones. Se ejecuta recursivamente desde el directorio en el que se ejecute el comando.

Sus opciones principales son:

--force: Si la configuración de git `clean.requireForce` no está marcada como false, el comando rechazará eliminar los archivos o directorios si no se marca esta opción.
--interactive: Muestra de forma interactiva lo que se haría para poder seleccionarlo.
--dry-run: muestra lo que se ejecutaría pero no lo llega a realizar, para que el usuario pueda ver el resultado de la acción antes de ejecutarlo.
-X: borra solo los elementos ignorados por git.q
