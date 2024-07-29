# Clase 02 - Git Desarrollo colaborativo

## Repasando dinamica de trabajo base de git

## Listar una cantidad especifica de commits en el log 

```sh
$ git log --oneline -<cantidad-commits>
$ git log --oneline -3
```
### Haciendo un commit, Pasos:

 1. Hacer un status para ver en que estado estan los archivos que quiero sean parte del commit.

```sh
$ git status
```

 2. Agregar lo que quiero dentro del commit al area de confirmacion (staging area).

```sh
$ git add <nombre-archivo>
$ git add clase.o2/README.md
$ git add . #Agregar todo lo que sea parte de la funcionalidad en la que trabajo
```

 3. Hago el commit. Todo lo que estuviera en el area de staging se guarda en el repositorio local.

```sh
$ git commit -m "Nuevo commit, mensaje descriptivo"
```

## Git diff comparo entre diferentes commit en el tiempo

```sh
$ git diff <hash> <hash>
```

## Para agregar algo que olvide o quiero incorporar en el ultimo commit, uso el siguiente comando

```sh
$ git add . 
$ git commit --amend
$ git commit --amend "nuevo mensaje" #si quiero modificar el nombre del commit uso esto
```
# Ramas (branches)

## Nos permiten trabajar en el proyecto de manera auxiliar

## Listar ramas

```sh
$ git branch
```

## Crear una rama

```sh
$ git branch <nombre-rama>

$ git branch feature/ramas
$ git branch feature/navbar  #feature es una nomenclatura comun para marcar ramas
```
## Moverme entre ramas

```sh
$ git switch <nombreDeRama> #el más recomendado actualmente 
$ git switch - #para moverse a la última rama a la que estuve

$ git switch feature/ramas
```

## Crear y moverme

```sh
$ git switch -c <nombreDeRama>

```