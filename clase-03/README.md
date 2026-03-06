# Clase 03 - Git deesarrollo colaborativo

## Ramas (Brances)

### Crear ramas

```sh
git branch <nueva-rama>
git branch feature/branches
```

### Listar ramas

```sh
git branch
```

> !!! IMPORTANTE: antes de movernos a otra rama debemos guardar los cambios realizados para no perder las modificaciones. 

### Crear rama y moverme a la rama creada

 ```sh
 git switch -c <nombre-rama>
 git switch -c feature/navbar
 ```

 ### Movernos entre la rama nueva y la anterior (movernos entre las 2 ultimas ramas cíclicamente)

 ```sh
 git switch -
 ``` 

 ### Eliminar ramas que no hayan tenido cambios
 > Para poder hacerlo se debe de estar posicionado en una rama distinta a la que vamos a eliminar/borrar

 ```sh
 git branch -d <nombre-rama>
 git branch -d feature/navbar
 ```

 ### Eliminar una rama que tenga cambios que no estén en el resto del proyecto
Borra una rama de manera forzada
 ```sh
 git branch -D <nombre-rama>
 git branch -D feature/branches
 ```

 ### Subir una arama específica al remoto
 ```sh
 git push <remoto> <nombre-rama>
 git push origin feature/branches
 ```

 ### Descargar toda la metadata del remoto (actualizar la carpeta .git local)
```sh
git fetch
```

### Listar ramas locales y remotas

```sh
git branch -a
```

### Listar ramas locales y remotas con detalle

```sh
git branch -av
```

## Alias en GIT(para evitar escribir comandos largos)
> Crear comandos
```sh
git config --global alias.<nombre-alias> "<comando completo sin el git>"
git config --global alias.ll "log --oneline --all --decorate --graph" # entre "" se escribe el comando completo sin el git del principio del comando
git config --global alias.l "log --oneline"
git config --global alias.s "status"
```

>Utilizar comandos ya creados (se usa con el bash en consola o con lynux)
```sh
!<nro-comando>
!! # usa el último comando utilizado
git <nombre-alias>
git ll # ejemplo con el alias creado como ll
```

### Listar configuraciones y alias
```sh
git config --global list
```

>Ver listado de comandos (se usa con el bash en consola o con lynux)
```sh 
history
```

### Borrar alias
```sh
git config --global --unset alias.sc
git config --global --unset user.<alias> # este se puede usar para borrar el mail y luego poder reconfigurarlo
```

### Empezando con fusiones (juntar 2 ramas)
Voy a poder fusionar 2 o más ramas entre sí para llevar los cambios de una rama origen a la de destino.
Los cambios se pueden realizar granularmente (sólo las lineas de codigo o archivos enteros específicos según sea necesario).

## Trabajando con fusiones
IMPORTANTE: Es que para hacer una fusión. Tengo que estar en la rama de destino. P sea que si me quiero traer los cambios de la rama feature/branches a la rama main, tengo que estar parado en la rama main y traerme los cambios de la otra rama.

```sh
git switch main
git merge feature/branches
```
> A partir de ese momento pueden pasar 3 cosas:
* Fast-forward-> Fusión automática -> Git se encarga de resolver la fusión.
* Tercer vía -> Diferentes algoritmos para resolver la fusión -> Automático
* Conflicto -> El proceso de fusión es manual. Voy a tener que solventar el conflicto y avisarle a git que lo hice para terminar el proceso de fusión.

```sh
git add --patch
```


### Distintos ámbitos en GIT (scopes)
* --system (alto) -> A todo el sistema operativo. Usuarios y repositorios
* --global -> Aplica a todos los repositorios del usuario actual. (Estandar)
* --local (bajo) -> Al repositorio específico en el qe estoy trabajando.

```sh
git config --<scope>
git config --system
git config --global
git config --local 
```
## Git Tags

* Marcar versiones de lanzamiento
* Facilitar despliegues y rollbacks
* Automatizar versiones en CI/CD
* Compartir versiones con otrosgit status