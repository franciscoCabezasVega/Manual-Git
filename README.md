# Manual-Git
Instrucciones y codigos para utilizar Git

## Comandos y funcionalidades

### Inicializar Repositorio

Para inicializar nuestro repositorio utilizamos el comando `git init Nombre_Repositorio`.

### Borrar Repositorio

Para borrar un proyecto se debe utilizar el comando `rm -rf .git` dentro de la carpeta que contiene los archivos.

### Ver Estados

Dentro del proyecto ingresamos el comando `git status` para así ver el estado de nuestro repositorio.

### Agregar a Staged

1. Agregar un solo archivo: `git add nombre_archivo`.
2. Agregar todos los archivos: `git add .`

### Quitar del Staged

El archivo puede ser quitado con `git rm --cached nombre_archivo`.

### Quitado Forzado del Staged 

El archivo puede ser quitado con `git rm -f nombre_archivo`.

### Confirmar si el archivo existe

El archivo puede ser revisado con `git add -n nombre_archivo`.