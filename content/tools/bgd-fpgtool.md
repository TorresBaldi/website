---
title: bgd-fpgtool
date: 2017-11-25
---

Una herramienta por consola para manejo de archivos FPG, programada en BennuGD.

<!-- more -->

La herramienta bgd-fpgtool permite convertir entre carpetas de imagenes y archivos FPG. Por un lado permite la creación de archivos a partir de una estructura de carpetas con imagenes, y por otro lado la extracción de imagenes a partir de archivos FPG.

Soporta varias profundidades de color (16 y 32 bits, por lo menos).

Todo esto se puede ejecutar desde la consola de comandos, lo que resulta muy util para "automatizar" el empaquetado de los recursos para el juego, reduciendo los pasos para que un artista vea los cambios en el juego, o permitiendo algunos _asset pipelines_ bastante interesantes, como por ejemplo exportar graficos a distintas resoluciones, y generar fpgs para distintas plataformas,

Ahora mismo la estoy usando efectivamente en la compilación de [Zombies 2012](/juegos/zombies-2012), pero la idea es de a poco integrarla con todos los juegos.

![Work In Progress](/img/wip.jpg)