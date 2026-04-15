# Clase 04 - Git desarrollo colaborativo

## Stash

> Git tiene un área llamada "stash" donde puedes almacenar temporalmente una captura de tus cambios sin enviarlos al repositorio. Está separada del directorio de trabajo (working directory), del área de preparación (staging area), o del repositorio.

* Existe dentro de Git
* No se puede subir al remoto
* Trabaja con una estructura de pila

## Como crear stashes

```sh
git stash
git stash --m "mensaje descriptivo"
```

## Listar los stashes
```sh
git stash list
```

## Ver uel contenido de un stash en particular (solo muestra la cantidad de lineas agregadas)
```sh
git stash show <nro de stash> # me muestra ese numero de stash
git stash show 0 # me muestra el stash que se encuentra en la posicion 0
git stash show stash{0}
```

## Aplicar un stash en particular
```sh
git stash apply # aplica el stash de arriba de todo (el mas nuevo)
git stash apply 1 # stash{1}
git stash apply 2 # stash{2}
```

## Recuperar el stash
```sh
git stash pop # Recupera el último stash realizado y si no hay conflicto lo borra.
```
## Borrar stashes
```sh
git stash drop # borra el ultimo stash de la lista
git stash drop <nro stash> # elimina un stash especifico
```