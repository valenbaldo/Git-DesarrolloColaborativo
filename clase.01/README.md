# Clase 01 - Desarrollo Colaborativo GIT


## Configuraciones iniciales de la herramienta


### Agregar un nombre usuario y un correo
Este usuario y el correo va a ser utilizado para firmar cada una de las instantáneas(commits).
Es obligatorio la configuración de este nombre de usuario/correo
En la consola de visual, por el global también se puede hacer en cualquier consola, ya que no es exclusivo para un proyecto sino para todos los proyectos futuros, se configura una única vez


```sh
$ git config --global user.name “Valentina Garcia Baldomar”
$ git config --global user.email valentinabaldomar04@gmail.com
$ git config --local ... #Tiene que existir un repositorio para poder
$ git config --system ...
```


Si usamos un correo vinculado a la cuenta de github, se van a ver reflejados(Mejor)


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
$ git config --global init.defaultBranch main
```




# Empezando a trabajar con GIT
Este comando crea un repositorio de git en la carpeta actual. Osea, crea un directorio oculto llamado .git(donde dentro tengo los archivos del repositorio)
```sh
$ git init
#---
Initialized empty Git repository in C:/Users/baldosita/Documents/baldosita/Pescar/Cursos/git/.git/
```
Se usa git bash ya que muestra la existencia de el repositorio/rama una vez creado (lo indica el MAIN).
Si la carpeta .git que se creó con el comando anterior se elimina/pierde se pierde el repositorio.
```sh
#---
baldosita@DESKTOP-OHU431F MINGW64 ~/Documents/baldosita/Pescar/Cursos/git (main)
```


## Controlar el status de los archivos dentro del repositorio
Los archivos pueden estar en diferentes estados y hay varios lugares/áreas abstractas(no se pueden ver claramente pero estan) de trabajo. Solo existe este comando cuando hay un repositorio


```sh
$ git status
```


### Áreas posibles en las que pueden estar los archivos
* Working Directory (Directorio de trabajo) donde van agregando, borrando al archivo el desarrollo


* Staging Area (Área de control de cambios) Se agregan los archivos para darle seguimiento y posteriormente sacarles una foto (commit)


* Local Repo (Área de validación de cambios, donde se registran las modificaciones realizadas) Donde van a estar todas las fotos (commit) que vaya sacando.


### Estados de los archivos
* Untracked (Sin seguimiento) => archivos que no se agregaron al index/stage y por consecuente no se les da seguimiento. Git sabe que existe pero no les está dando seguimiento/controlando, es decir que no sabe que pasa dentro de ese archivo.


* Staged => Archivos que fueron agregados al index/stage área y cuyos cambios van a ser incorporados al repositorio


* Unmodified => Archivos que se encuentran en en el repositorio y no fueron modificado (Con respecto al repositorio, última instantánea)


* Modified => Archivos que se encuentro en el repositorio pero difieren con lo que se encuentra actualmente en el directorio trabajo (Working directory, última instantánea)

#### Agregar al area de Staging
Hacer que pase de Untracked a Staged. Marca el archivo y los cambios para que formen en un futuro parte de la siguiente instantenea (foto/commit).
```sh
git add <nombre-archivo>
git add clase.01/README.md
git add . #Tabulo parq eu auto complete
```
Luego compruebo con gitStatus, faltaria hacer commit

##### Guarda en el repositorio una instantanea. Sacar una foto/commit
Se hace commit de MICROTAREAS,no muchas cosas, para en caso de necesitar volver algo para atras, sea mas facil.

```sh
git commit -m "Mensaje descriptivo de lo que se hizo (Corto)"
```

###### Para comparar el Working Directory y el Local Repo
Lo verde es lo que se agrego al archivo, lo rojo lo que se quito en base a lo que tenia en el repositorio, previo al ultimo commit. Se sale con la "q".


```sh
git diff
```

#### Quitar de la area de staging area
```sh
git restore --staged <nombre-del-archivo>
git restore --staged clase.01/README.md
```

#### Como ver lo que paso en un commit
```sh
git show <hash>
git show 60776
```

#### Mostrar el historico de commit
```sh
git log # Version larga.
git log --oneline # Version resumen
```

#### .gitignore: Para ignorar archivos que no deseo que esten en el repositorio
Creo normalmente en el directorio raíz del proyecto el archivo .gitignore. Se le escriben los nombres de las carpetas a ignorar. Puede ser un commit unico

#### .gitkeep: Para darle seguimiento a carpetas vacias
Git no versiona carpetas vacias, este archivo sirve para que la detecte. 