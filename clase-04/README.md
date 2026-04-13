# Clase 04 - Git desarrollo colaborativo

## Stash

> Git tiene un área llamada "stash" donde puedes almacenar temporalmente una captura de tus cambios sin enviarlos al repositorio. Está separada del directorio de trabajo (working directory), del área de preparación (staging area), o del repositorio.

* Existe dentro de Git
* No se puede subir al remoto
* Trabaja con una estructura de pila

## Como crear stashes

```sh
git stash
```

## Listar los stashes
```sh
git stash list
```

## Recuperar el stash
```sh
git stash pop # Recupera el último stash realizado y si no hay conflicto lo borra.
```