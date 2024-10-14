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
