# Manual-Git

Instrucciones y codigos para utilizar Git.

## Contenido

01. [Etapas del proyecto](#etapas-del-proyecto)
02. [GIT TAG](#git-tag)
03. [GIT LOG](#git-log)
04. [COMPARACIONES](#comparaciones)
05. [GIT RESET](#git-reset)
06. [GIT BRANCH](#git-branch)
07. [GIT CHECKOUT](#git-checkout)
08. [GIT MERGE](#git-merge)
09. [GIT STASH](#git-stash)
10. [GIT CHERRY-PICK](#git-cherry-pick)

## [Etapas del proyecto](#manual-git)

Recordar reemplazar los valores encerrados dentro de los [ ].

### Inicializar Repositorio

Para inicializar nuestro repositorio utilizamos el comando `git init [Nombre_Repositorio]`.

### Borrar Repositorio

Para borrar un proyecto se debe utilizar el comando `rm -rf .git` dentro de la carpeta que contiene los archivos.

### Ver Estados

Dentro del proyecto ingresamos el comando `git status` para así ver el estado de nuestro repositorio.

### Agregar a Staged

1. Agregar un solo archivo: `git add [nombre_archivo]`.
2. Agregar todos los archivos: `git add .`

### Quitar del Staged

El archivo puede ser quitado con `git rm --cached [nombre_archivo]`.

### Quitado Forzado del Staged 

El archivo puede ser quitado con `git rm -f [nombre_archivo]`.

### Confirmar si el archivo existe

El archivo puede ser revisado con `git add -n [nombre_archivo]`.

### Subir cambios al repositorio local

`git commit -m "[Ej. Comentando respecto al codigo]"` Este comando permite aplicar los cambios de tu repositorio sin subir los cambios al repositorio remoto.

### Concatenar cambios al repositorio local

Nos permite anexar un cambio dentro de nuestro repositorio con la opcion de sobreescribir el commit anterior, para sobreescribir el commit y guardar los cambios basta con ingresar el comando `git commit -m "[Ej. Comentando respecto al codigo]" --amend` y si se desea mantener el commit anterior entonces seria de la siguiente forma: `git commit --amend`.

## [GIT TAG](#manual-git)

### Versionamiento del codigo (TAG)

Para crear el versionamiento de forma ligera en nuestro proyecto, se debe estar en la version que se desea taggear e ingresar la siguiente instruccion: `git tag -a [0.1] -m '[inicializando]'` donde -a es la etiqueta del tag y -m es la descripcion de la misma.

### Listar Versionamiento del codigo (TAG)

Para listar estos tags basta con simplemente escribir en la consola `git tag -l`.

### Editar Versionamiento del codigo (TAG)

La estructura del comando para editarun tag con respecto a un commit ya existente es: `git tag [1.0] [ID_SHA_Commit]`.

### Borrar Versionamiento del codigo (TAG)

Para borrar basta con escribir el siguiente comando seguido de la etiqueta a borrar `git tag -d [1.0]`.

### Renombrar Versionamiento del codigo (TAG)

El proceso para renombrar una version de alguno de nuestros commit es el siguiente en donde se reciben 3 parametros los cuales son: nombre de la nueva etiqueta > comentario > Id del commit afectado `git tag -f -a [0.1] -m '[iniciando]' [ID_SHA_Commit]`.

## [GIT LOG](#manual-git)

### Historia resumida

Para ver el historial de commits en forma resumida y en solo una linea utilizamos el comando `git log --oneline`.

### Historia resumida con grafico

Para ver el historial de commits en forma resumida y en solo una linea con grafica utilizamos el comando `git log --oneline --graph`.

### Historia resumida en un rango

Para ver el historial de commits en forma resumida y en solo una linea dentro de un rango simplemente le pasamos ese parametro luego del - tal como se muestra a continuacion `git log -[3]`.

## [COMPARACIONES](#manual-git)

### Cambio entre el estado actual con respecto a otro

Para ver las diferencias entre el estado en el que nos encontramos actualemnte y otro que necesitemos comparar, simplemente debemos ingresar el siguiente comando: `git diff ID_SHA_Commit`.

### Cambio entre 2 versiones

Para comparar los cambios sucedidos entre una version y otra se ingresa el siguiente comando: `git diff [SHA Version 1] VS [SHA Version 2]`.

## [GIT RESET](#manual-git)

### Reset Soft

El comando `git reset --soft [SHA]` va a quitar el ultimo commit realizado sobre la version seleccionada, sin eliminar los archivos del stage dejandolos listos para volver a subir los cambios.

### Reset Mixed

El comando `git reset --mixed [SHA]` va a quitar el ultimo commit realizado sobre la version seleccionada, sin eliminar los archivos del woking directory dejandolos listos para volver a subir los cambios con `git add` y `git commit`.

### Reset Head

Para borrar el archivo del stage se debe ingresar el comando `git reset HEAD [archivo]`.

### Reset Hard

Para borrar el archivo de todas las fases y dejar todo como si nunca hubiera existido, se debe ingresas el comando `git reset --hard [SHA]`.

## [GIT BRANCH](#manual-git)

### Crear Rama

Para crear una rama debemos ingresar el comando `git branch [RAMA]` para generar esa nueva rama.

### Listar Ramas

Para listar todas las ramas dentro de nuestro proyecto, basta con escribir dentro de la consola `git branch -l`.

### Eliminar Rama

Cuando una rama no ha sido mezclada ni tiene cambios adentro, basta con ingresar el siguiente comando: `git branch -d [RAMA]`.

### Eliminar Rama a la fuerza

En el caso de que no se cumpla lo mencionado en el punto anterior se debe escribir con D mayuscula tal como se muestra a continuacion: `git branch -D [RAMA]`.

### Renombrar Rama

Para renombrar nuestras ramas simplemente debemos ingresar el comando con la estructura mostrada a continuacion: `git branch -m [Nombre de la rama viejo] [Nombre de la rama nuevo]`.

## [GIT CHECKOUT](#manual-git)

### Moverse a otra rama

Para movernos entre una rama a otra basta con escribir el nombre de la rama a donde queremos estar `git checkout [RAMA]`.

### Moverse al estado actual de un commit

Si se desea revisar el estado de un proyecto cuando hicimos un determinado commit se puede revisar ingresando la siguiente instruccion seguida de su respectivo codigo: `git checkout [SHA]`.

### Crear una rama e ingresar de inmediato

Para crear una rama y quedarnos dentro en un solo paso, se debe escribir el siguiente comando: `git chekout -b [RAMA]`.

## [GIT MERGE](#manual-git)

### Mezclar los cambios

Para mezclar los cambios de una rama a la rama master, primero debemos ubicarnos en la rama que deseamos agregar los cambios, despues, ejecutar el siguiente comando con el nombre de la rama de donde se piensa mezclar todo `git merge [RAMA a mezclar]`.

## [GIT STASH](#manual-git)

### Guardar cambios temporalmente

Para guardar los cambios de forma temporal sin afectar nuestro proyecto se utiliza el comando `git stash` siempre y cuando existan cambios en la fase de stage.

### Listar Stash

Para listar los estados se debe ingresar la instruccion `git stash list`.

### Eliminar Stash

Al momento de eliminar un stash en necesario copiar el nombre del mismo junto con en indice que corresponde a su espacio en memoria de esta manera: `git stash drop  stash@{1}`.

### Aplicar los cambios del ultimo stash

Ingresando el siguiente comando `git stash apply` se pueden aplicar todos los cambios sucedidos a partir del ultimo stash.

## [GIT CHERRY-PICK](#manual-git)

### Seleccionando un commit

Cuando se presenta una situacion en donde solo queremos subir un cambio de una rama a otra, es necesario usar el comando `git cherry-pick [SHA]` junto al codigo del commit que deseamos subir.
