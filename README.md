# Aprendiendo GitFlow

- Gitflow es un modelo de ramificación para Git que propone una estructura para gestionar proyectos, dividiendo el trabajo en diferentes ramas con propósitos especificos.

- Tenemos las dos ramas principales que serian main y develop.

- main: rama principal almacena el historial de publicación oficiales, contiene el código en producción.
- develop: es una rama de integración para el desarrollo. esto  al confirmar conviene etiquetar la rama con la versión.

- En git tenemos el comando `git flow init` que crear la estructura básica de todo el flujo que sigue git flow. la rama develop, feature, release, hotfix, support, prefix.

- !Nunca se trabaja directamente en la rama main/master¡

- Desarrollo basado en troncos es otro forma de trabajar con git recomendada para DevOps. Este trata de desarrollar pequeñas actualizaciones de forma frecuente en un "tronco" o rama principal. esto es mejor para los equipos de DevOps para simplificar las fases de fusión e integración. Funciona creando una rama a partir de la rama main, se desarrolla la actualización en un corto periodo de tiempo y es fucionada con la rama main. Esto es recomendado con CI para asegurar que lo que se fusiona pasa los tests.

- Rama Feature: se utilizan para desarrollar nuevas funciones. se crean a partir de develop y, una vez listas, se fusionan de nuevo en develop. comando para crear un feature: `git flow feature start feature_rama` y al terminar: `git flow feature finish feature_rama`
- Rama Release: estas se crean a partir de develop cuando estás listo para preparar una nueva versión de producción. sirve para realizar ajustes finales, correcciones de errores y preparar el código para el lanzamiento. comando para crear un release: `git flow release start 0.1.0(versión)` y al terminar: `git flow release finish '0.1.0'(versión)`. Esta se fusiona con el main y develop.
- Hotfix: Estos son para corregir errores críticos que afectan la versión de producción. se crean a partir de main/master. comando para crear un hotfix: `git flow hotfix start hotfix_branch` y al terminar: `git flow hotfix finish hotfix_branch`. Esta se debe fusionar el main y develop.

- Ya entendiendo para que sirve cada rama, veamos el flujo de trabajo.

- se clona el repo principal, `git flow init` para crear la estructura, nos dirigimos a la rama develop, creamos un feature, traajamos, lo fusionamos con la rama develop, una ves listo creamos una rama release para verificar que todo esta bien y la fusionamos al main y develop con `git flow release finish 'versión'`, listo.
- para los hotfix creamos la rama hotfix desde la rama main.

![gitflow-diagrama](https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTKD2bDmVYzWDpJb2lOyVa_2onAbF9XPWStZg&s)

- Contenido sacado de documentos de atlassian y canal de youtube la tecnología avanza.