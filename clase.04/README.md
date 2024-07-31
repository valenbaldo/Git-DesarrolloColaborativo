## Clase 04 - Git Desarrollo colaborativo

### Area de Stash

STAGES - Como almacenar cosas que aun no estan para hacer un commit (sin terminar/en proceso). Es una estructura de datos de tipo pila, se puede tener mas de un stash en la caja de stages. Solo se usa de manera individual, no se suben al remoto. Al momento de traer varios stages pueden surgir conlictos, se solucionan igual que los conflictos de fusciones (merge).

![estructura-pila](_ref/estructurapila.png)

#### Crear stashes 

```sh
$ git stash
$ git stash -m "nombre stash" #Se usa en caso de querer ponerle un nombre para identificarlo
```

#### Listar stages

```sh
$ git stash list
```

#### Aplicar un stash (el ultimo)
Si lo aplica borra el ultimo stash, si hay conflicto lo aplica y no lo borra.

```sh
$ git stash pop
```
#### Aplicar un stash especifico (rompiendo la estructura de pila)
Lo aplica pero NUNCA borra el stash, hay que hacerlo manualmente

```sh
$ git stash apply <numero de stash>
```

#### Borrar un stash (el ultimo)

```sh
$ git stash drop
```

#### Borrar un stash en especifico

```sh
$ git stash drop <numero de stash>
```

## Git alias
Me permite crear alias de comandos para en vez de estar escribiendo el comando y sus sub comandos hacerlo a traves de una letra o una palabra

### Creando un alias

```sh
$ git config --global alias.<alias-elegido> "<comando-de-git-sin-la-palabra-git>"
$ git config --global alias.s "status --short"
$ git config --global alias.c "commit -m"
$ git config --global alias.l "log --oneline"
$ git config --global alias.ll "log --oneline --all --graph --decorate"
```

### Quitar un alias

```sh
$ git config --global --unset alias.ll #Quita el alias ll
```

### Listar alias configurados

```sh
$ git config --global --get-regexp alias
```

# GIT RESET
Me permite deshacer cambios en el arbol de trabajo y en el area de preparacion(staging area) de git.

## 3 tipos de reset

Le digo uno menos(inmediato inferior) de los quiero eliminar.

1. Reset soft: borra el commmit o los commits selecionados y arrojar los cambios al staging area. 

```sh
git reset --soft <hash>
```

2. Reset Mixed: Va a borrar el commit o los commits seleccionados y arrojar los cambios al Working directory.

```sh
git reset <hash>
git reset --mixed <hash>
```

3. Reset hard: Va a borrar el commit o los commits seleccionados y descartar los cambios dentro de esos commit. Hay que tener cuidado al usarlo.

```sh
git reset <hash>
git reset --hard <hash>
```