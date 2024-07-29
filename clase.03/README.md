# Clase 03 - Git Desarrollo colaborativo

## Repaso

Recomendacion: En el proyecto deberiamos tener una rama pincipal (main) y una rama de cada uno de los integrantes. Hay que tener cuidado si se asignan mismas funcionalidades ya que puede haber colisiones al momento de fusionar las ramas. 

### Ramas

![estructura-ramas](_ref/basica.png)
![estructura-ramas](_ref/avanzada.png)

### Creando una rama

```sh
git branch <nombre-rama>
```

### Listar ramas dentro de un repositorio

```sh
git branch
```

### Cambiar de ramas

```sh
git switch <nombre-rama>
git switch feature/ramas
git switch - #Toggle entre las ultimas 2 ramas
```

### Borrar una rama

```sh
git branch -d <nombre-rama>
git branch -d feature/footer 
```

Si los cambios exiten en otra rama de nuestro repo, voy a poder borrar la rama sin problemas pero si no exite tengo que forzar el borrado de la rama

```sh
git branch -D feature/footer
```
## Crear rama y moverse a ella

```sh
$ git switch -c <nombreDeRama>
$ git switch -c feature/ramas
