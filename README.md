# ejercicio-git-libro
## clonando el repositorio

```
https://github.com/emsantamaria/ejercicio-git-libro
```

## ejercicio1
### mostrar historial de cambios

```
commit 36c8689cadd3411a525730547a7140183c935dca (HEAD -> main, origin/main, origin/HEAD)
Author: emsantamaria <zeroenygma2@gmail.com>
Date:   Mon Oct 14 21:04:32 2024 +0100

    Initial commit
```

### creando la carpeta capitulos y creando un archivo txt 

```
mkdir capitulos
 cat > capitulos/capitulo1.txt~Git es un sistema de control de versiones ideado por Linus Torvalds.
```

### añadiendo los cambios a la zona de intercambio temporal

```
git add capitulos/capitulo1.txt~
git add README.md
```

### hacer commit 

```
[main 0ab28c5] añadido capitulo1
 1 file changed, 3 insertions(+)
 create mode 100644 capitulos/capitulo1.txt~
```

### mostrar historial

```
commit 8a58657095394a2a041be7d9e6c31760cdf52498 (HEAD -> main)
Author: emsantamaria <zeroenygma2@gmail.com>
Date:   Mon Oct 14 22:17:38 2024 +0100

    añadido capitulo1

commit 0ab28c53e718b2c22542304ab2e0994fca8598f0
Author: emsantamaria <zeroenygma2@gmail.com>
Date:   Mon Oct 14 22:14:00 2024 +0100

    añadido capitulo1

commit 36c8689cadd3411a525730547a7140183c935dca (origin/main, origin/HEAD)
Author: emsantamaria <zeroenygma2@gmail.com>
```

## ejercicio2
### crear el fichero capitulo2.txt

```
cat > capitulos/capitulo2.txt
 El flujo de trabajo básico con Git consiste en:
 1- Hacer cambios en el repositorio.
 2- Añadir los cambios a la zona de intercambio temporal.
 3- Hacer un commit de los cambios.
```

### añadir los cambios

```
git add capitulos/capitulo2.txt
git add README.md
```

### hacer el commit

```
[main 3164437] añadido capitulo2
 2 files changed, 31 insertions(+), 1 deletion(-)
 create mode 100644 capitulos/capitulo2.txt
```

### mostrar diferencias

```
diff --git a/capitulos/capitulo2.txt b/capitulos/capitulo2.txt
new file mode 100644
index 0000000..4abf557
--- /dev/null
+++ b/capitulos/capitulo2.txt
```

## ejercicio3
### crear capitulo 3

```
cat > capitulos/capitulo3.txt
  
Git permite la creación de ramas lo que permite tener distintas versiones del mismo proyecto y trabajar de manera simultanea en ellas.
```

### añadiendo 

```
git add capitulo3.tx
```

### mostrar historial

```
commit 3164437a0d22db03816084dc7369d6fdef4ce465 (HEAD -> main)
Author: emsantamaria <zeroenygma2@gmail.com>
Date:   Mon Oct 14 22:35:46 2024 +0100

    añadido capitulo2

commit 8a58657095394a2a041be7d9e6c31760cdf52498
Author: emsantamaria <zeroenygma2@gmail.com>
Date:   Mon Oct 14 22:17:38 2024 +0100

    añadido capitulo1

commit 0ab28c53e718b2c22542304ab2e0994fca8598f0
Author: emsantamaria <zeroenygma2@gmail.com>
Date:   Mon Oct 14 22:14:00 2024 +0100

    añadido capitulo1

commit 36c8689cadd3411a525730547a7140183c935dca (origin/main, origin/HEAD)
Author: emsantamaria <zeroenygma2@gmail.com>
Date:   Mon Oct 14 21:04:32 2024 +0100
```

## ejercicio4
### creando indice

```
cat > indice.txt
```

### añadir 

```
git add indice.txt
```

### echo
```
echo "Indice de los cápitulos, con conceptos avanzados de git" >> indice.txt
```
### commit
```
[main ac5d875] se crea el indice
 2 files changed, 2 insertions(+)
 create mode 100644 capitulos/capitulo3.txt
 create mode 100644 indice.txt
```
### mostrar quien ha hechos cambios
```
ccbeab60        (emsantamaria   2024-10-14 22:54:20 +0100       1)Indice de los cápitulos, con conceptos avanzados de git
```
## ejercicio5
### crear una nueva rama
```
bibliografia        ccbeab6 se crea el indice
* main                ccbeab6 [adelante 5] se crea el indice
  remotes/origin/HEAD -> origin/main
  remotes/origin/main 36c8689 Initial commit
```
## ejercicio6
### añadir capitulo4
```
cat > capitulos/capitulo4.txt
En este capítulo veremos cómo usar GitHub para alojar repositorios en remoto.
```
### hacer commit 
```
git add capitulos/capitulo4.txt 
[main 5d187aa] añadido capitulo4
 1 file changed, 1 insertion(+)
 create mode 100644 capitulos/capitulo4.txt
```
### mostrar la historia del repositorio
```
5d187aa (HEAD -> main) añadido capitulo4
* ccbeab6 (bibliografia) se crea el indice
* ac5d875 se crea el indice
* 3164437 añadido capitulo2
* 8a58657 añadido capitulo1
* 0ab28c5 añadido capitulo1
* 36c8689 (origin/main, origin/HEAD) Initial commit
```
## capitulo7
### cambiar a la rama bibliografia
```
git checkout bibliografia 
Cambiado a rama 'bibliografia'
```
### crear el fichero bibliografia.txt
```
cat > bibliografia.txt
- Chacon, S. and Straub, B. Pro Git. Apress
```
### añadir los cambios y hacer commit
```
git add bibliografia.txt 
 git commit -m"añadido bibliografia.txt"
[bibliografia 601e429] añadido bibliografia.txt
 1 file changed, 1 insertion(+)
 create mode 100644 bibliografia.txt
```
### mostrar historial
```
601e429 (HEAD -> bibliografia) añadido bibliografia.txt
| * 5d187aa (main) añadido capitulo4
|/  
* ccbeab6 se crea el indice
* ac5d875 se crea el indice
* 3164437 añadido capitulo2
* 8a58657 añadido capitulo1
* 0ab28c5 añadido capitulo1
* 36c8689 (origin/main, origin/HEAD) Initial commit
```
## ejerrcicio 8
### fusionar rama bibliografia con main
```
Merge made by the 'ort' strategy.
 bibliografia.txt | 1 +
 1 file changed, 1 insertion(+)
 create mode 100644 bibliografia.txt
```
### historial
```
c098559 (HEAD -> main) Merge branch 'bibliografia'
|\  
| * 601e429 (bibliografia) añadido bibliografia.txt
* | 5d187aa añadido capitulo4
|/  
* ccbeab6 se crea el indice
* ac5d875 se crea el indice
* 3164437 añadido capitulo2
* 8a58657 añadido capitulo1
* 0ab28c5 añadido capitulo1
* 36c8689 (origin/main, origin/HEAD) Initial commit
```
### eliminar rama bibliografia
```
git branch -d bibliografia 
Eliminada la rama bibliografia (era 601e429).
```
### historial
```
 c098559 (HEAD -> main) Merge branch 'bibliografia'
|\  
| * 601e429 añadido bibliografia.txt
* | 5d187aa añadido capitulo4
|/  
* ccbeab6 se crea el indice
* ac5d875 se crea el indice
* 3164437 añadido capitulo2
* 8a58657 añadido capitulo1
* 0ab28c5 añadido capitulo1
* 36c8689 (origin/main, origin/HEAD) Initial commit
```
## ejercicio 9
### crear la rama bibliografia
```
git branch bibliografia
```
### ir a la rama bibliografia
```
git checkout bibliografia 
Cambiado a rama 'bibliografia'
```
### crear bibliografia.txt
```
cat > bibliografia.txt
- Scott Chacon and Ben Straub. Pro Git. Apress.
- Ryan Hodson. Ry's Git Tutorial. Smashwords (2014)
```
### cambiar a main
```
it checkout main 
Cambiado a rama 'main'
```
### Añadir los cambios a la zona de intercambio temporal y hacer un commit con el mensaje “Añadida nueva referencia bibliográfica.”
```
 git add bibliografia.txt 
git commit -m"añadida nueva bibliografia"
[bibliografia c0abc34] añadida nueva bibliografia
 1 file changed, 2 insertions(+), 1 deletion(-)

```
### Fusionar la rama bibliografía con la rama main.
```
git merge bibliografia 
Actualizando c098559..c0abc34
Fast-forward
 bibliografia.txt | 3 ++-
 1 file changed, 2 insertions(+), 1 deletion(-)
```
### mostrar historial
```
 c0abc34 (HEAD -> main, bibliografia) añadida nueva bibliografia
*   c098559 Merge branch 'bibliografia'
|\  
| * 601e429 añadido bibliografia.txt
* | 5d187aa añadido capitulo4
|/  
* ccbeab6 se crea el indice
* ac5d875 se crea el indice
* 3164437 añadido capitulo2
* 8a58657 añadido capitulo1
* 0ab28c5 añadido capitulo1
* 36c8689 (origin/main, origin/HEAD) Initial commit
```
