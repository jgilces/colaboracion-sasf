# NOTAS DE LA CAPACITACIÓN DEL CURSO DE GIT - Miércoles

## Fundamentos de Git - Comandos

- **(git status)** Permite obtener el estado actual del repositorio, a continuación se muestra el resultado de git status cuando se detectan cambios sobre archivos a los cuales git esta dando seguimiento:
    ```On branch nuevaRama
    Changes not staged for commit:
    (use "git add <file>..." to update what will be committed)
    (use "git restore <file>..." to discard changes in working directory)
            modified:   miercoles/notas.md

    no changes added to commit (use "git add" and/or "git commit -a")```

- En el siguiente ejemplo se muestra git status cuando existen archivos en el stage y se han detectado cambios en alguno de los archivos:
  ```On branch nuevaRama
    Changes to be committed:
    (use "git restore --staged <file>..." to unstage)
            modified:   miercoles/notas.md

    Untracked files:
    (use "git add <file>..." to include in what will be committed)
            miercoles/prueba.txt```

## Configuración inicial de GIT

Antes de realizar los commits de los cambios en el repositorio, sera necesario configurar el usuario y email del repositorio de git, caso contrario se presentará un error:

```$ git commit -m "Se añaden notas"
Author identity unknown

*** Please tell me who you are.

Run

  git config --global user.email "you@example.com"
  git config --global user.name "Your Name"

to set your account's default identity.
Omit --global to set the identity only in this repository.
```

Para resolver esto se pueden usar los siguientes comandos para establecer el usuario y correo del repositorio:

```
git config --global user.name "usuario"
git config --global user.email "correo"
```

## Configuración del Editor de texto por defecto

Siempre que se realice un commit, o se realice alguna acción que requiera la interacción del usuario para el ingreso de mensajes, git intentará abrir el editor de texto por defecto, por default en la instalación de git el editor es VIM, para cambiar a otro editor usamos el siguiente comando:

```
git config --global core.editor "emacs | vim | subl"
```

Tener presente que el editor de texto debe estar configurado en la variable PATH del sistema operativo.

## Cambiando el nombre de la rama por defecto master

En versiones antiguas de git, la rama por defecto al crear un repositorio era master (y se sigue manteniendo hoy en día), pero en versiones mas actuales de git ya no se crea la rama master, en vez de ello la rama se renombro a main, el usuario puede cambiar el nombre de la rama por defecto haciendo uso del siguiente comando:

```
git config --global init.defaultBranch "nombre de la rama"
```


# SNAPSHOT DE CAMBIOS

Luego de que se han realizado los cambios sobre el repositorio, el usuario puede realizar la confirmación de sus cambios para queden registrados en la base de cambios de git, para realizar un commit existen dos formas muy similares:

```
 (git commit).- Esta opcion es la mas basica, una vez presionado enter se abrira el editor configurado previamente, en el editor el usuario deberá especificar el mensaje del commit, un commit en este modo, permite el ingreso del titulo del commir y del cuerpo del commit.

 (git commit -m "mensaje").- Esta opcion es un atajo del commit tradicional, la unica diferecnia es que no es posible especificar el cuerpo del commit solo el titulo del mismo.
```