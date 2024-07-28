# Clase 01 - Desarrollo Colaborativo GIT

## Configuraciones iniciales de la herramienta

### Agrego un nombre usuario y un correo
Este usuario y el correo va a ser utilizado para firmar cada una de las instantaneas(commits). 
Es obligatorio la configuracion de este nombre de usuario/correo
En la consola de visual, por el global tambien se puede hacer en cualquier consola, ya que no es exclusivo para un proyecto sino para todos los proyectos futuros, se configura una unica vez

```sh
$ git config --global user.name “Valentina Garcia Baldomar”
$ git config --global user.email valentinabaldomar04@gmail.com 
$ git config --local ... #Tiene que existir un repositorio para poder 
$ git config --system ...
```

Si usamos un correo vinculado a la cuenta de github, se van a ver refeljados(Mejor)

#### Verificar comando usuario/correo
Si en la consola no dice nada, se aplico correctamente el comando, igualmente se puede verificar con el siguiente comando: 
```sh
$ git config --get-regexp user
# ----
user.name Valentina Garcia Baldomar
user.email valen.facultad04@gmail.com
```

### Borrar alguna de las configuraciones
```sh
git config --global --unset user.email
```

### Cambiar a nano
Cambiar a nano, si lo hicimos al instalarlo no hace falta

```sh
$ git config --global core.editor “nano" 
```

#### Verificar nano
```sh
$ git config --get-regexp editor
# ----
core.editor nano.exe
```

### Quieren cambiar la rama por defecto. Es master... (main)
```sh
git config --global init.defaultBranch main
```


# Empezando a trabajar con GIT
Este comando crea un repositorio de git en la carpeta actual. Osea, crea un directorio oculto llamado .git(donde dentro tengo los archivos del repositorio)
```sh
git init 
#---
Initialized empty Git repository in C:/Users/baldosita/Documents/baldosita/Pescar/Cursos/git/.git/
```
Se usa gitbash ya que muestra la existencia de el repositorio/rama una vez creado (lo indica el MAIN). 
Si la carpeta .git que se creo con el comando anterior se elimina/pierde se pierde el repositorio.
```sh
#---
baldosita@DESKTOP-OHU431F MINGW64 ~/Documents/baldosita/Pescar/Cursos/git (main)
```
