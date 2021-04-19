# Git Cheat Sheet 🎆🎇

Esta es una hoja de trucos con los comandos más útiles para trabajar con Git.

## ⚙ Ayuda y configuración
Configuración inicial de Git
```bash
git config --global user.name <nombre>
git config --global user.email <email>
```
Listar las configuraciones globales de Git
```bash
git config --global -l
```
Editar el archivo de configuraciones globales de Git
```bash
git config --global -e
```
Conover la versión de Git
```bash
git --version
```
Obtener ayuda
```bash
git --help
git --help <comando>
```

## ✏ Comandos básicos
Inicializar un repositorio
```bash
git init
```
Ver estatus del repositorio
```bash
git status
```
Agregar un archivo al stage
```bash
git add <ruta_del_archivo>
```
Agregar todos los archivos al stage
```bash
git add .
```
```bash
git add -A
```
Crear un commit
```bash
git commit -m "<mensaje_del_commit>"
```
Crear un commit y agregar archivos al mismo tiempo
```bash
git commit -am "<mensaje_del_commit>"
```
Deshacer todos los cambios hasta el último commit
```bash
git checkout -- .
```
Mostrar el log de commits
```bash
git log
```
Quitar archivos del stage
```bash
git reset <ruta_del_archivo>
```
Agregar varios elementos comunes en todo el proyecto
```bash
git add ".jpg" # Agrega todas las imágenes jpg del proyecto
```
Agregar varios elementos comúnes en el directorio actual
```bash
git add .jpg # Agrega todas las imágenes jpg del directorio actual
```

## ✏ Utilidades básicas
Mostrar el log de forma compacta
```bash
git log --oneline
```
Mostrar el log de forma alternativa (compacta, todas las ramas y visualmente mas llamativo)
```bash
git log --oneline --decorate --all --graph
```
Mostrar el estatus de forma compacta
```bash
git status -s 
```
Mostrar el estatus de forma compacta mostrando la rama actual
```bash
git status -s -b
```
Crear alias para comandos
```bash
git config alias.<alias> "<comando>"

git config alias.lg "git log --oneline --decorate --all --graph" # Ejemplo para crear un alias

git lg # Llamamos al alias que creamos
```

## 📃 Trabajando con archivos modificados y commits
Ver cambios entre archivos
```bash
git diff
```
Ver cambios entre archivos que estan en el stage
```bash
git diff --staged
```
Editar el mensaje del último commit
```bash
git commit --amend -m "<nuevo_mensaje>"
```
Revertir al último commit
```bash
git reset --soft HEAD
```
Revertir al padre del último commit
```bash
git reset --soft HEAD^
```
Revertir cambios conservando el stage
```bash
git reset --soft <id_del_commit>
```
Revertir cambios conservando eliminando el stage pero conservando los cambios
```bash
git reset --mixed <id_del_commit>
```
Revertir cambios eliminando todo
```bash
git reset --hard <id_del_commit>
```
Mostrar log de todas las acciones realizadas
```bash
git reflog
```
Renombrar un archivo
```bash
git mv <nombre_archivo_actual> <nombre_archivo_nuevo>
```
Eliminar un archivo
```bash
git rm <nombre_del_archivo>
```
