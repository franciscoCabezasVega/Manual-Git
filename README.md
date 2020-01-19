# Manual-Git

Instrucciones y codigos para utilizar Git

## Contenido

1. Etapas del proyecto
2. GIT TAG
3. GIT LOG
4. COMPARACIONES
5. GIT RESET
6. GIT BRANCH
7. GIT CHECKOUT

## Etapas del proyecto

Recordar reemplazar los valores encerrados dentro de los [].

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

## GIT TAG

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

## GIT LOG

### Historia resumida

Para ver el historial de commits en forma resumida y en solo una linea utilizamos el comando `git log --oneline`.

### Historia resumida con grafico

Para ver el historial de commits en forma resumida y en solo una linea con grafica utilizamos el comando `git log --oneline --graph`.

### Historia resumida en un rango

Para ver el historial de commits en forma resumida y en solo una linea dentro de un rango simplemente le pasamos ese parametro luego del - tal como se muestra a continuacion `git log -[3]`.

## COMPARACIONES

### Cambio entre el estado actual con respecto a otro

Para ver las diferencias entre el estado en el que nos encontramos actualemnte y otro que necesitemos comparar, simplemente debemos ingresar el siguiente comando: `git diff ID_SHA_Commit`.

### Cambio entre 2 versiones

Para comparar los cambios sucedidos entre una version y otra se ingresa el siguiente comando: `git diff [SHA Version 1] VS [SHA Version 2]`.

## GIT RESET

### Reset Soft

El comando `git reset --soft [SHA]` va a quitar el ultimo commit realizado sobre la version seleccionada, sin eliminar los archivos del stage dejandolos listos para volver a subir los cambios.

### Reset Mixed

El comando `git reset --mixed [SHA]` va a quitar el ultimo commit realizado sobre la version seleccionada, sin eliminar los archivos del woking directory dejandolos listos para volver a subir los cambios con `git add` y `git commit`.

### Reset Head

Para borrar el archivo del stage se debe ingresas el comando `git reset HEAD [archivo]`.

### Reset Hard

Para borrar el archivo de todas las fases y dejar todo como si nunca hubiera existido, se debe ingresas el comando `git reset --hard [SHA]`.

## GIT BRANCH

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

## GIT CHECKOUT

###