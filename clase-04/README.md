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

# CREAR TAGS
Es un etiqueta para los commits

## Crear un tag
```sh
git tag v1.0
# ejemplo de un tag en un commit especifico
git tag -a v0.8 -m "version no final" <hash> 
git tag -a v0.8 -m "version no final" c616c7d
# Ejemplo d eun tag en el último commit
git tag -a v1.0 -m "version actual de la documentación"
```

## Listar tags ya creados
```sh
git tag --list
```

## Ver tags ya creados
```sh
git show <nombre del tag> # para ver un tag especifico
git show v0.08
```

## Eliminar tags
```sh
git tag --delete <nombre del tag>
git tag --delete v0.08
git tag -d <nombre del tag>
git tag -d v0.08
```

## Subir al remoto los tags
```sh
git push origin --tags # no se recomienda
git push origin v1.0

```
## Eliminar tags del remoto
```sh
git push --delete origin <nombre del tag>
git push <nombre del remoto> :<nombre del tag>
git push origin :v0.08
```