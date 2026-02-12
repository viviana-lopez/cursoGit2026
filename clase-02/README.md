# Clase 02 - Git desarrollo colaborativo

## Repaso comandos vistos.

> Muestro el estado y área en la que están los archivos

```sh
git status
```

> Marcamos archivos que están en el working directory para posteriormente hacer un commit

```sh
git add class-01/_ref/* # Marco todos los archivos que están dentro de la carpeta _ref
git add class-01/* # marca todos los archivos que estan dentro de la carpeta class-01
git add . # Este comando me sirve para marcar todos los archivos para luego hacer un commit
```

> Hacemos un commit (Snapshot, instantanea)

```sh
git commit -m "mensaje descriptivo"  # 80 caracteres maximo
```

> Listo timeline de commits (listado de commits)

```sh
git log --oneline
```
# .gitignore
Es un archivo que me permite indicarle a GIT que no quiero que la carpeta o el archivo sea controlado por GIT
Dentro del archivo hay que inficar que carpetas o archivs queremos que GIT ignore

# .gitkeep
Es un archivo que me permite darle seguimiento a una carpeta que quiero sea parate del repo pero que esté vacía. (para que sea utilizada luego).
Se hace esto porque GIT no versiona carpetas vacías. Sólo versiona carpetas que tengan archivos dentro.
Este archivo no lleva ningún tipo de contenido ni código y debe ser generado dentro de la carpeta vacía.