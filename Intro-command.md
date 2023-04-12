## Comandos iniciales 

- `git init`   *para comenzar con el repositorio*
- `git add` *para agregar un archivo con cambios al repositorio*
- `git commit -m "texto que describe el cambio"` *confirmar los cambios ingresados al repo local*
- `git status` *checkear los cambios pendientes*
- `git show` *para ver historial de cambios efectuados*
- `git log` *para ver historial de cambios menos detalle*
- `git push` *para enviar cambios al repositorio remoto*
- `git pull` *para traer la ultima version del repositorio*
- `git rm`   *para quitar un archivo del repo*
- `git rm --cached`   *para quitar desde el cache*

## comandos para configurar una cuenta git 
- `git config --list`   *ver la configuracion actual*
- `git config --list --show -origin` *ver la ruta de origen de los archivos de configuracion* 
- `git config --global user.name` *cambiar el nombre de la configuracion global*
- `git config --global user.email` *cambiar el email de la configuracion global*
## analizar cambios en el archivo
- `git show`   *muestra el historial de cambios comenzando por mostrar el numero de tag*
- `git diff`   *para comparar dos versiones ingresando el tag, git diff ( tag antiguo  -  tag nuevo)*
 
## stagin ciclo basico
git add agrega los cambios al stagin area y esta a la espera de ser enviado al repo , pueden ser eliminados con rm 
git rm para remover 
commit se va al repositorio (master)

## estados del archivo 
1 sin rastrear
2 git add toma las modifricaciones y manda a stagging area .....esta siendo trackeado en stagging
3 commit -m los envia desde stagging al repo 

uso de checout traes los cambios de una rama a mi repo local 

## se crea la nueva rama dev
Qué regla produciría una advertencia "would be overwritten"?
Si ha modificado un archivo que también tiene modificaciones en el repositorio remoto pero no lo ha hecho un commit.
### Opciones
1. Desea forzar un pull para sobrescribir el archivo Obviamente, si realmente quieres esto, no te importan los cambios que acabas de hacer y no te importa eliminarlos. Si es así, simplemente haz lo siguiente:
```
git reset --hard
git pull
```
2. Si quieres ambos, tus cambios como los cambios desde el pull La forma más fácil de manejar esto en mi opinión es hacer un commit de tus cambios y luego hacer un pull. Entonces si hay un conflicto merge utiliza los mecanismos generalmente para resolver el merge (hint: configura difftool y mergetool así que usted puede resolver fácilmente conflictos usando GUI tools como el meld o el diffmerge etc.). Solo haz:
```
git add $archivo_afectado
git commit
git pull
```
3. Si quieres ambos cambios pero no tienes listo tu commit Pero sucede de vez en cuando usted tiene código parcialmente roto que usted está depurando y usted realmente no desea hacer un commit. En este caso puede almacenar los cambios temporalmente y luego desarmarlo, haz lo siguiente:
```
git stash
git pull
git stash pop 
```
