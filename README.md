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

## 🌳 Trabajando con ramas
Crear una rama
```bash
git branch <nombre_de_la_rama>
```
Ver todas las ramas
```bash
git branch
```
Cambiarse a una rama
```bash
git checkout <nombre_de_la_rama>
```
Diferecias entre ramas
```bash
git diff <nombre_de_la_rama> <nombre_de_la_rama>
```
Unir ramas
```bash
git merge <nombre_de_la_rama> # Desde la rama a la que se quieren mezclar los cambios
```
Eliminar una rama
```bash
git branch -d <nombre_de_la_rama>
```
Crear y cambiarse a una rama
```bash
git checkout -b <nombre_de_la_rama>
```

## 🏷 Trabajando con tags
Crear un tag
```bash
git tag <nombre_del_tag>
```
Mostrar todos los tags
```bash
git tag
```
Borrar un tag
```bash
git tag -d <nombre_del_tag>
```
Crear un tag con anotaciones
```bash
git tag -a <nombre_del_tag> -m "<mensaje>"
```
Crear un tag con anotaciones de un commit pasado
```bash
git tag -a <nombre_del_tag> <id_del_commit> -m "<mensaje>"
```
Ver información de un tag
```bash
git show <nombre_del_tag>
```

## 🛠 Comandos avanzados: Stash y rebase
Enviar los cambios actuales al stash
```bash
git stash
```
Mostrar todos los cambios en el stash
```bash
git stash list
```
Recuperar y eliminar el último cambio del stash
```bash
git stash pop
```
Eliminar el último cambio del stash
```bash
git stash drop
```
Enviar los cambios actuales al stash con un comentario
```bash
git stash save "<comentario>"
```
Recuperar la última entrada del stash sin eliminarla
```bash
git stash apply
```
Recuperar una entrada específica del stash
```bash
git stash apply <id_del_stash>
```
```bash
git stash apply stash@{1}
```
Enviar los cambios actuales al stash sin incluir los cambios del stage
```bash
git stash save --keep-index
```
Enviar los cambios actuales al stash incluyendo los archivos sin segumiento
```bash
git stash save --include-untracked
```
Borrar todas las entradas del stash
```bash
git stash clear
```
Reordenar commits
```bash
git rebase <nombre_de_la_rama> # Desde la rama de la cual quiero mover los commits
```
```bash
git rebase master # Desde development
```
Unir dos commits
```bash
git rebase -i HEAD~<no_de_commits>
```
```bash
git rebase -i HEAD~4 # Los últimos 4 commits
```
```bash
pick <id_del_commit> <mensaje_del_commit>
pick <id_del_commit> <mensaje_del_commit>
pick <id_del_commit> <mensaje_del_commit>
squash <id_del_commit> <mensaje_del_commit> # Fusiona este commit con el commit superior
```
Editar el mensaje del commit
```bash
git rebase -i HEAD~<no_de_commits>
```
```bash
git rebase -i HEAD~1 # El último commit
```
```bash
reword <id_del_commit> <mensaje_del_commit>
```
Separar archivos de un commit en varios commit
```bash
git rebase -i HEAD~<no_de_commits>
```
```bash
git rebase -i HEAD~1 # El último commit
```
```bash
edit <id_del_commit> <mensaje_del_commit>
```
```bash
git reset HEAD^ # Revertir los cambios del último commit
```
```bash
git add <ruta_del_archivo> # Agregamos los archivos para un nuevo commit
```
```bash
git commit "<mensaje_del_commit>" # Creamos el nuevo commit, los últimos dos pasos se repiten hasta tener todos los commits necesarios
```
```bash
git rebase --continue # Finalizamos la edición
```

## ☁ Repositorios remotos
Ligar el repositorio local con uno remoto
```bash
git remote add origin <url_del_repo>
```
Ver los reposotiorios remotos
```bash
git remote -v
```
Subir los cambios al repositorio
```bash
git push -u <remoto> <rama> # -u sirve para establecer la rama master como default
```
```bash
git push -u origin master
```
Subir los tags al repositorio
```bash
git push --tags
```
Bajar cambios del repositorio
```bash
git pull <remoto> <rama>
```
```bash
git pull origin master
```
Clonar un repositorio
```bash
git clone <url_del_repo>
```
Clonar un repositorio especificando el nombre de la carpeta
```bash
git clone <url_del_repo> <nombre_carpeta>
```
