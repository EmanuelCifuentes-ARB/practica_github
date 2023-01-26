# practica_github

## Commit inicial y readme

Creado el repositorio con el nombre practica_github desde la página de github.
El archivo README.md fue también creado desde la página de github.
La forma equivalente desde el terminal sería:
 $ touch README.md
 $ git add README.md
 $ git commit -m 'commit inicial'
 $ git push

## .gitignore

Creado archivo privado.txt y el directorio privada con touch y mkdir respectivamente.
Creado archivo .gitignore con touch y agregadas las rutas para que ignore el archivo y el directorio mencionados anteriormente (hecho con echo desde el terminal):

 $ echo "privada/" >> .gitignore
 $ echo "privado.txt" >> .gitignore

Luego, los cambios fueron commiteados y pusheados:
 $ git status
 $ git add .
 $ git commit -m *"mensaje"*
 $ git push
Este mismo código se referenciara más tarde con esta linea:
_Los cambios fueron commiteados y pusheados_

Readme abierto en Visual Studio para formatearlo correctamente.

## Ramas
Creado 1.txt
 $ touch 1.txt
Creada rama y cambiado el directorio de trabajo a esta rama
 $ git checkout -b v0.2
Creado archivo 2.txt
 $ touch 2.txt

_Los cambios fueron commiteados y pusheados_
La única diferencia es que, cuando se pusheo, fue pusheado de la siguiente manera:
 $ git push --set-upstream origin v0.2 para crear la rama remota

El espacio de trabajo fue cambiado hacia la rama _main_
 $ git checkout main

Mergeadas ramas con:
 $ git merge v0.2

### Merge con conflicto

Agregado "hola" en el archivo 1.txt, cambios commiteados:
 $ echo "hola" > 1.txt
 $ git add 1.txt
 $ git commit -m "añadido hola en 1.txt"

El espacio de trabajo fue cambiado hacia la rama _v0.2_
 $ git checkout v0.2

Agregado "adios" en el archivo 2.txt, cambios commiteados:
 $ echo "adios" > 2.txt
 $ git add 2.txt
 $ git commit -m "añadido adios en 2.txt"

El espacio de trabajo fue de vuelta cambiado hacia la rama _main_
 $ git checkout main

Se intenta hacer el merge con:
 $ git merge v0.2
retornando:
 *Auto-merging 1.txt*
 *CONFLICT (content): Merge conflict in 1.txt*
 *Automatic merge failed; fix conflicts and then commit the result.*

Listando con _merged_ y _no-merged_ retorna:
 $ git branch --merged
    _* main_
 $ git branch --no-merged
    _v0.2_
Entonces, la rama _v0.2_ todavía no está mergeada.

