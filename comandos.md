 # DETALLES DEL GITBASH

[GIT DOCUMENTACIÓN](https://git-scm.com/docs/git-push)

## COMANDOS GENERALES

[tutorial git](https://bluuweb.github.io/tutorial-github/guia/fundamentos.html)

git init
=> para iniciar seguimiento del proyecto

git status
=> ver el estado de todos los archivos

git status -s
=> ver listado de archivos directorios modificados y estado actual

git add index.html
=> lleva un archivo de seguimiento al area de ensayo "staging area"

git add .
=> le ordena hacer seguimiento a todos los archivos

git commit -m "descripción del archivo"
=> traslada el archivo al repositorio

git commit -am
=> agrega al area y hace el commit al mismo tiempo
con el git commit -am "description", este comando solo servirá si los archivos han sido previamente añadidos con el comando git add, si son archivos nuevos, no funcionará con ellos y deberás hacer un "git add ." más git commit -m "x".

git push
=> luego del commit para subir los cambios a la nube en github

git push origin --force
=> fuerza subir cambios al remoto luego de retroceder commits en tu repo local

git pull
=> para traer los cambios echos en remoto (desde la pagina de github)

git pull origin main
=> trae cambios echos en el remoto indicando la rama destino "main"

git commit --amend
=> para modificar un commit echo (comentario) o introducir nuevo texto'solo funciona con el ultimo commit'

## Restauracion

git restore --staged nameFile 
=> restorna un archivo del estage a su estado inicial

git reset .
=> para quitar todos los archivos del add

git reset "nameFile"
=> para quitar un archivo del add

git reset --hard "código"
=> hace una restauración a un estado anterior o posterior dando el código del commit

git checkout -- .
=> Restaura los archivos a un estado anterior incluido los borrados

git reset "código" --hard
=> restaura a un commit especifico

git reset --hard HEAD
=> volviendo a HEAD

git reset --hard HEAD^
=> volviendo a la confirmación antes de HEAD

git reset --hard HEAD~1
=> equivalente a ^

git reset --hard HEAD~2
=> retrocediendo dos confirmaciones antes de HEAD

get restore nameFile
=> recupera un archivo eliminado(que no halla sido comiteado)

## Ignorar archivos a fuerza

git rm --cached notas-md
=> si git ignore no evita archivos usa esto

## Variados

git stash
=> Guardado temporal que puede ser copiado o traladarlo a otra rama 

git stash pop
=> Trae cambios guardados con stash a la rama actual

git cherry-pick codeCommit
=> copia un commit desde una rama a otra(debes ubicarte en la rama donde quieres tener el commit)

git grep -n "texto"
=> muestra todos los lugares en tu proyecto donde este el texto que buscas, para buscar etiquetas html usa ""

git log -S "texto"
=> buscar una palabra dentro de un commit

alias (alias)=(comando)
=> para crear alias "atajos" de comandos enteros

git config --global alias.estado <aqui el comando completo>
=> crea un shorthands de algún comando demasiado largo(ojo que este cambio es permanente)

## Mostrar

git log --oneline
=> Muestra un listado de todos los commit echos, la descripción y quien hizo el cambio

git log --since=<hora> --oneline
=> para mostrar lista de commit con una hora especifica

git remote
=> muestra si tiene un repo en linea

git remote -v
=> muestra la URL del repo remoto para hacer fetch y push(deberian ser iguales)

git remote add apstream http://linkRepoOrigin (direccion del repositorio original del fork)
=> Agregar un repositorio remoto para recuperar cambios

git shortlog
=> muestra todos los cambios hechos por un equipo de trabajo con un git pull request

git shortlog -sn
=> para ver en números la cantidad de commit echos por el grupo de trabajo

git shortlog -sn --all
=> muestra si alguien del equipo borro commit a comparación del -sn solo muestra todo

git shortlog -sn --all --no--merges
=> muestra todos los commit en números menos los merge

git blame "nombreArchivo.extencion"
=> muestra quien hizo que en que linea con una lista completa(muy util en equipo)

git blame css/estilos.css -l<desdeLinea,hastaLinea>
=> muestra quien hizo q en cada linea de código (solo linea que especificamos)

git reflog
=> muestra una lista de todos los commit

## Limpieza de archivos

git clean --dry-run
=> debes hacer esto para mostrar todo lo que este comando te va a eliminar(archivos no trakeados)

git clean -f
=> elimina todo lo mostrado en la ejecución en seco (no elimina capetas)

## Copia in commit en otra rama

git cherry-pick código
=> copia commit especifico de otras ramas(mala practica porque no dice de donde se obtuvo)

## RAMAS O BRANCH

git branch nombre
=> para crear una nueva rama(git --oneline) para verificar

git checkout -b rama-nueva
=> para crear una rama nueva y ubicarse en esa al mismo tiempo

git branch
=> para ver en que rama estamos trabajando(el \* indica donde)

git checkout nombre
=> moverme a otra rama

git merge nombre(rama secundaria)
=> para UNIR ramas,el merge se debe hacer desde la rama master

git branch -d nombre(rama a eliminar)
=> para eliminar una rama luego de unirla al master

git push origin :nombreRama
=> para guardar cambios de eliminar rama en el repositorio remoto

git branch -r
=> para ver todas las ramas en remoto (osea en linea) que existeron y existen

git branch -a
=> para ver todas las ramas en local y remoto

nota: luego de conflictos con ramas usa git 'status' 'add .' 'commit' para guardar cambio

## CREANDO EL TAG (versiones para descargar)

git tag -a v1.0.0 -m "descripción del tag o release"
=> para crear la 1° tag

git push --tags
=> para subir el tag creado al repositorio

## CLONANDO REPO REMOTO

git clone "url que te da el githug"
=> con esto crear un clon del repositorio seleccionando donde lo quieres crear (carpeta)

## COMANDOS VIM

vim - git commit --amend
=> para abrir el editor Vim
comandos:
i => para empezar a editar
escp => para salir de editar
:wq => para guardar cambios y salir

Depués de introducir el comando con la dirección de vuestro repositorio desde la pagina de git y no os salga el recuadro de iniciar sesión:
colocad, despues de ejecutar el comando que muestra Juan lo siguiente : \$ git push origin master
(esto solo es en caso de tener ese detalle pero en general funciona bien)

## CREDENCIALES CONFIGURACIÓN minuto25

[tutorial](https://www.youtube.com/watch?v=sH9g77J92ns&ab_channel=CodeWar)

git credential -manager delete (url de github https://github.com)
=> para borrar credenciales de una cuenta

git config --global user.name

## HEROKU - VARIABLES DE ENTORNO

heroku config
=> muestra las variables de entorno existentes

heroku config:set nombre=richard
=> crea una variable de entorno

heroku config:get nameVariable
=> obtiene el contenido de la variable

heroku config:unset nameVariable
=> elimina una variable de entorno
