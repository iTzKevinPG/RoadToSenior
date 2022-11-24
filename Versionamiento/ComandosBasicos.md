# Comandos básicos de Git🤞

Dentro de esta sección veremos los que forman parte de los comandos básicos o de uso casi diario de Git.

## Comandos

* Git clone
* Git branch
* Git checkout
* Git status
* Git add
* Git commit
* Git push
* Git pull 
* Git revert
* Git merge
* Git config
* Git init
* Git reset
* Git rebase
---

## Que, Como o Para Que!✨

Aquí se irán explicando cada comando con la información especifica y necesaria y un breve ejemplo.

### ✔ **Git clone**

Este comando básicamente lo que hace es generar en la ubicación de la ejecución del comando una copia idéntica de el ultimo estado del proyecto alojado en un repositorio ejemplo (GitHub).

```

git clone <URL-HTTPS Repository>

```
---

### ✔ **Git branch**

Dentro de Git la parte fundamental es el branching, creación de ramas para hacer un trabajo simultaneo entre varias personas a un mismo proyecto, existe la creación, la enumeración o listado y eliminación de ramas.


```
- Creación

git branch <branch-name>

- Listado

git branch
git branch --list

- Eliminación

git branch -d <branch-name>

```
---

### ✔ **Git checkout**

En un concepto básico este comando lo que nos permite hacer es movernos entre ramas, teniendo en cuenta excepciones de no tener cambios locales que generen conflictos.

```

git checkout <name-of-your-branch>

```

Excepciones:

* Todo cambio en tu rama actual preferiblemente deben confirmarse o guardarse antes del cambio.
* La rama a la que se va a cambiar debe existir local/remota.
---

### ✔ **Git status**

Este comando nos provee información sobre la rama actual.

```

git status

```

Información:

* Si la rama actual está actualizada.    
* Si hay algo que necesita un commit, un add, o borrarse.  
* Si hay archivos preparados, sin preparar o sin seguimiento    
* Si hay archivos creados, modificados o eliminados
---

### ✔ **Git add**

Dentro de nuestro trabajo diario, existen creaciones, modificaciones o eliminaciones de archivos, todos estos cambios quedaran registrados en nuestro local a la espera de una confirmación. Lo que hace este comando es agregar estos cambios para ser confirmados próximamente.

```
- Agregar un archivo

git add <file>

- Agregar todos los cambios

git add -A

```
---

### ✔ **Git commit**

Este comando es necesario en el momento de nuestro desarrollo cuando ya finalizamos las modificaciones y queremos guardarlo. Esto es como un punto de control, un guardado al cual si queremos podemos volver después. 

Para el uso de este comando es necesario dejar un mensaje corto y explicito sobre a que hace referencia (Una tarea o problema especifico).

```

git commit -m "commit message"

```

**Tener en cuenta que esto solo guarda localmente los cambios** 🚩

---

### ✔ **Git push**

Este comando es un paso siguiente a la confirmación de los cambios o el uso del comando **Git commit**, esto lo que hace es subir los cambios que se encuentran confirmados al servidor remoto.

```

git push <remote> <branch-name>

```

También hay que ser consientes que si una rama recién creada no existe remotamente, por esta razón debemos publicar la rama.

```

git push --set-upstream <remote> <name-of-your-branch>

- o

git push -u origin <branch_name>

```
---

### ✔ **Git pull**

Este comando es para obtener los cambios que estén alojados remotamente que no se encuentran en nuestro local, el funcionamiento de este comando es una combinación de dos comandos -**Git fetch** & -**Git merge**, lo que hace simplemente es traer cambios remotos y aplicarlos sobre la rama local y asi dejar actualizada la rama.

```

git pull <remote>

```

**Tener en cuenta que esto puede traer conflictos, si es asi el caso deben solucionarse manualmente** 🚩

---

### ✔ **Git revert**

En algunos casos de nuestro trabajo diario necesitamos deshacer cambios que hemos hecho en nuestra rama local o remota, pero este tipo de comandos deben ser usados con precaución para evitar **eliminaciones** no deseadas.

Para hacer uso de el comando Git revert lo primero es conocer nuestras confirmaciones, asi identificar a que punto queremos hacer la reversion de los cambios, para esto podemos usar un comando.

```

git log -- oneline

```

Luego de identificados los códigos **Hash** de cada confirmación, especificaremos que commit nos gustaría deshacer con su código.

```

git revert <Commit-Hash-Code>

```

Al realizar esta acción el comando, deshará la confirmación dada, pero creara una nueva confirmación sin eliminar lo anterior.

Ventaja de hacer **Git revert** es que no toca los historiales de los commits. Esto quiere decir que cualquier cambio realizado queda también registrado como una confirmación. Otro punto importante es que los cambios realizados con el comando quedan en local a menos de que se suban a remoto.

---

### ✔ **Git merge**

Consiguiente a el ajuste o desarrollo en tu rama y todo este correcto, el paso final es fusionar esos cambios a la rama consiguiente (dev, cert, master), para esto nos ayudara este comando.

Lo que hace este comando básicamente es integrar a la rama en la que estas posicionado características y sus confirmaciones de una rama de origen ejemplo ( Posicionados sobre dev o master, haces merge de tu feature), fusionando todo lo de tu rama feature con la que estas posicionado.

 Pasos:
* Para hacer esto lo primero que debemos hacer es actualizar nuestras ramas a fusionar (dev y feature).
* Posicionarnos en la rama de destino (dev).
* Hacer merge de la rama origen (feature)

```
- Rama destino

git checkout dev

- Merge origen

git merge <branch-name>

```






---
## Curiosidades 🤯

* Git Checkout para crear rama y acceder a la misma con tag **-b**.

```

git checkout -b <name-of-your-branch>

```