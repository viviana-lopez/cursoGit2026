# Clase 04 - Git desarrollo colaborativo

## STASH

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

# RESET
Me permite hacer uno o varios comits y los cambios los arroja a xxx lugar
Hay de tres tipos:
* SOFT
* MIXED
* HARD

## Git reset soft
Me permite deshacer uno o varios commits y los cambios los arroja al staging area (SA) (solo se pirerde el titulo del commit)
```sh
git reset --soft <nro de hash>
```

## Git reset mixed (default)
Me permite deshacer uno o varios commits y los cambios los arroja en el working directory (WD) (se pierde el titulo del commit y el guardado del contenido)

```sh
git reset <hash>
git reset --mixed <hash>
```
## Git reset hard
Me permite deshacer uno o varios commits y los cambios los descarta (CUIDADO PIERDO LOS CAMBIOS SOBRE LOS ARCHIVOS)
```sh
git reset --hard <hash>
```
