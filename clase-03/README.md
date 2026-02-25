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

 ## Subir una arama específica al remoto