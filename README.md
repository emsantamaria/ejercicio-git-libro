# Tarea 6
## Ejercicio 1: Etiquetar una versión
### Crea una nueva etiqueta en la rama principal que marque el estado actual del repositorio como la versión 1.0.

´´´
git tag 1.0.0
´´´

### Empuja la etiqueta al repositorio remoto.

´´´
Enumerando objetos: 35, listo.
Contando objetos: 100% (35/35), listo.
Compresión delta usando hasta 4 hilos
Comprimiendo objetos: 100% (30/30), listo.
Escribiendo objetos: 100% (35/35), 4.28 KiB | 398.00 KiB/s, listo.
Total 35 (delta 9), reusados 3 (delta 0), pack-reusados 0
remote: Resolving deltas: 100% (9/9), done.
To https://github.com/emsantamaria/ejercicio-git-libro
 * [new tag]         1.0.0 -> 1.0.0
 ´´´

 ### Muestra la lista de etiquetas presentes en el repositorio usando git tag.

 ´´´
VirtualBox:~/ejercicio-git-libro$ git tag
1.0.0
´´´

## Ejercicio 2: Revertir un commit
### Haz un cambio sencillo en uno de los archivos (puedes agregar una línea de texto en el archivo capitulo1.txt), y realiza un commit con un mensaje apropiado, como "Agregada una línea en capítulo 1".

´´´
En la rama main
Tu rama está actualizada con 'origin/main'.

nada para hacer commit, el árbol de trabajo está limpio
´´´

### imagina que te has equivocado y no querías hacer ese cambio. Reviértelo usando git revert.

´´´
uso: git revert [<opciones>] <commit-ish>...
   o: git revert <subcomando>

    --quit                finalizar secuencia revert o cherry-pick
    --continue            resumir secuencia revert o cherry-pick
    --abort               cancelar secuencia revert o cherry-pick
    --skip                saltar el commit actual y continuar
    --cleanup <modo>      cómo quitar espacios y #comentarios de mensajes
    -n, --no-commit       no realizar commit de forma automática
    -e, --edit            editar el mensaje de commit
    -s, --signoff         agregar una línea Signed-off-by al final
    -m, --mainline <número-de-padre>
                          seleccionar el padre principal
    --rerere-autoupdate   actualizar el índice con la resolución de conflictos reutilizada si es posible
    --strategy <estrategia>
                          estrategia de fusión
    -X, --strategy-option <opción>
                          opción para estrategia de fusión
    -S, --gpg-sign[=<key-id>]
                          Firmar commit con GPG
´´´

### Muestra el historial de commits para verificar que el commit de reversión se ha realizado correctamente.

´´´
uso: git revert [<opciones>] <commit-ish>...
   o: git revert <subcomando>

    --quit                finalizar secuencia revert o cherry-pick
    --continue            resumir secuencia revert o cherry-pick
    --abort               cancelar secuencia revert o cherry-pick
    --skip                saltar el commit actual y continuar
    --cleanup <modo>      cómo quitar espacios y #comentarios de mensajes
    -n, --no-commit       no realizar commit de forma automática
    -e, --edit            editar el mensaje de commit
    -s, --signoff         agregar una línea Signed-off-by al final
    -m, --mainline <número-de-padre>
                          seleccionar el padre principal
    --rerere-autoupdate   actualizar el índice con la resolución de conflictos reutilizada si es posible
    --strategy <estrategia>
                          estrategia de fusión
    -X, --strategy-option <opción>
                          opción para estrategia de fusión
    -S, --gpg-sign[=<key-id>]
                          Firmar commit con GPG

bae2@jpexposito-VirtualBox:~/ejercicio-git-libro$ git log commit
fatal: argumento ambiguo 'commit': revisión desconocida o ruta fuera del árbol de trabajo.
Usa '--' para separar las rutas de las revisiones, de esta manera:
'git <comando> [<revisión>...] -- [<archivo>...]'
bae2@jpexposito-VirtualBox:~/ejercicio-git-libro$ git log
commit c0abc34e898b345eadacab699d99472bf9bc4c3a (HEAD -> main, tag: 1.0.0, origin/main, origin/HEAD, bibliografia)
Author: emsantamaria <zeroenygma2@gmail.com>
Date:   Mon Oct 14 23:21:01 2024 +0100

    añadida nueva bibliografia

commit c0985592f7ba0a618bdf0e94f458c399e311d29e
Merge: 5d187aa 601e429
Author: emsantamaria <zeroenygma2@gmail.com>
Date:   Mon Oct 14 23:11:39 2024 +0100
´´´

## Ejercicio 3: Aplicar cambios de otra rama con Cherry-pick
### Crea una nueva rama llamada nueva-funcionalidad y haz un cambio en la rama, por ejemplo, crea un nuevo archivo capitulo5.txt con el siguiente contenido:   En este capítulo veremos cómo gestionar múltiples ramas en Git.

´´´
git branch nueva-funcionalidad
git checkout nueva-funcionalidad 
cat > capitulo5.txt
En este capítulo veremos cómo gestionar múltiples ramas en Git.
´´´

### Realiza un commit del cambio.

´´´
git add capitulo5.txt 
nueva-funcionalidad 8c2c798] creada nueva branch con capitulos5.txt
 1 file changed, 1 insertion(+)
 create mode 100644 capitulo5.txt
´´´

### Vuelve a la rama main y usa git cherry-pick para aplicar el commit de la rama nueva-funcionalidad en main.

´´´
git checkout main
--quit                finalizar secuencia revert o cherry-pick
    --continue            resumir secuencia revert o cherry-pick
    --abort               cancelar secuencia revert o cherry-pick
    --skip                saltar el commit actual y continuar
    --cleanup <modo>      cómo quitar espacios y #comentarios de mensajes
    -n, --no-commit       no realizar commit de forma automática
    -e, --edit            editar el mensaje de commit
    -s, --signoff         agregar una línea Signed-off-by al final
    -m, --mainline <número-de-padre>
                          seleccionar el padre principal
    --rerere-autoupdate   actualizar el índice con la resolución de conflictos reutilizada si es posible
    --strategy <estrategia>
                          estrategia de fusión
    -X, --strategy-option <opción>
                          opción para estrategia de fusión
    -S, --gpg-sign[=<key-id>]
                          Firmar commit con GPG
    -x                    adjuntar el nombre del commit
    --ff                  permitir fast-forward
    --allow-empty         preservar commits iniciales vacíos
    --allow-empty-message
                          permitir commits con mensajes vacíos
    --keep-redundant-commits
                          mantener commits redundantes, vacíos
´´´

## Ejercicio 4: Comparar ramas
### Haz un cambio en la rama main (puedes modificar el archivo README.md agregando una breve descripción).

´´´
creada breve descripcion
´´´

## Usa el comando git diff para comparar los cambios entre la rama main y la rama nueva-funcionalidad.

´´´
diff --git a/capitulo5.txt b/capitulo5.txt
new file mode 100644
index 0000000..be46439
--- /dev/null
+++ b/capitulo5.txt
@@ -0,0 +1 @@
´´´

## Ejercicio 5: Resolver conflictos de fusión
### Crea un conflicto de fusión modificando el mismo archivo en ambas ramas (main y nueva-funcionalidad).

´´´
Ya está actualizado.
´´´

### Intenta hacer un merge de la rama nueva-funcionalidad en main y resuelve el conflicto manualmente.

´´´
 Actualizando c0abc34..8c2c798
Fast-forward
 capitulo5.txt | 1 +
 1 file changed, 1 insertion(+)
 create mode 100644 capitulo5.txt
´´´

### Realiza un commit una vez resuelto el conflicto, y muestra la historia del repositorio.

´´´
main 08ae379] resuelto conflicto
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 capitulo2.txt
´´´

## Ejercicio 6: Revertir un merge
### Realiza un merge de la rama nueva-funcionalidad en la rama main.

´´´
Ya está actualizado.
´´´

### Ahora, imagina que no querías hacer esa fusión. Usa git revert para revertir el merge.

´´´
git revert -m"revertido merge"
uso: git revert [<opciones>] <commit-ish>...
   o: git revert <subcomando>

    --quit                finalizar secuencia revert o cherry-pick
    --continue            resumir secuencia revert o cherry-pick
    --abort               cancelar secuencia revert o cherry-pick
    --skip                saltar el commit actual y continuar
    --cleanup <modo>      cómo quitar espacios y #comentarios de mensajes
    -n, --no-commit       no realizar commit de forma automática
    -e, --edit            editar el mensaje de commit
    -s, --signoff         agregar una línea Signed-off-by al final
    -m, --mainline <número-de-padre>
                          seleccionar el padre principal
    --rerere-autoupdate   actualizar el índice con la resolución de conflictos reutilizada si es posible
    --strategy <estrategia>
                          estrategia de fusión
    -X, --strategy-option <opción>
                          opción para estrategia de fusión
    -S, --gpg-sign[=<key-id>]
                          Firmar commit con GPG
´´´

## Ejercicio 7: Eliminar una etiqueta
### Borra la etiqueta v1.0 localmente y en el repositorio remoto.

´´´
git tag -d
´´´

## Ejercicio 8: Restablecer un commit (Reset)
### Haz un commit en la rama main y luego restablece el estado del repositorio al commit anterior utilizando git reset --hard.

´´´
En la rama main
Tu rama está adelantada a 'origin/main' por 2 commits.
  (usa "git push" para publicar tus commits locales)

nada para hacer commit, el árbol de trabajo está limpio
´´´

### Verifica el estado del repositorio después del reset.

´´´
HEAD está ahora en 08ae379 resuelto conflicto
´´´
