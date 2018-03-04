---
title: Integración Continua en BennuGD
date: 2017-01-19
tags:
---

Aprovechando la [migración que hice de todos mis proyectos BennuGD a Github](http://torresbaldi.com/nuestros-juegos-en-github/), se me ocurrió intentar modernizar un poco las técnicas de desarrollo y agregar integración continua a la mezcla. También aprovechando que en proyectos open source esto se puede hacer de manera gratuita con [Travis CI](https://travis-ci.org).

Les cuento un poco lo que fue mi travesía para poder dejar todo funcionando:

<!-- more -->

## Primer paso: Instalar BennuGD

La idea es, para cada build descargar la ultima version de BennuGD desde la pagina oficial, y después instalarla.

Descarga, con wget:

```
wget http://www.bennugd.org/downloads/bgd-1.0.0-r335-linux.tar.gz
```

Instalación, que consiste en extraer los archivos, dar permisos de ejecución a los binarios, mover a las carpetas correspondientes, y hacer visibles las librerías. Todo esto sería:

```
tar -zxvf bgd-1.0.0-r335-linux.tar.gz
chmod +x bin/*
sudo mv bin/* /usr/local/bin/
sudo mv lib/* /usr/local/lib/
sudo ldconfig -v
```

Acá mismo quise probar correr **bgdc**, y no había caso, me decía que no encontraba el archivo, siendo que el archivo estaba ahí mismo donde yo lo había puesto. Después de varias horas de luchar con este problema, encontré que venia por el lado de [querer ejecutar un binario 32 bits es un sistema 64 bits](http://askubuntu.com/questions/133389/no-such-file-or-directory-but-the-file-exists). La solución? Instalar las librerías de compatibilidad con 32 bits, e instalar las dependencias de BennuGD en su versión especifica de 32 bits:

```
sudo apt-get update -qq
# 32bit compatibility
sudo apt-get install -qq libc6:i386 libncurses5:i386 libstdc++6:i386
# BennuGD dependencies
sudo apt-get install -qq zlib1g:i386 libssl1.0.0:i386 libsdl1.2debian:i386 libsdl-mixer1.2:i386
```

Después de todo esto, chan, tenemos BennuGD instalado!

## Segundo paso compilar el juego

Para esto lo que yo hacia era, a partir de varios archivos prg, concatenarlos y armar un único prg grande, que es el que finalmente se va a usar dentro del juego.

Y en este momento como no hay tests para correr, mi prueba es simplemente comprobar que el proyecto compila.

Estos dos procesos los separé en 2 scripts, a los que apropiadamente decidí llamar build.sh y test.sh. Corro todo con:

```
# primero doy permisos de ejecucion
sudo chmod +x build.sh test/test.sh
# armo el archivo final
./build.sh
# voy a la carpeta test a probar el juego que usa el archivo
cd test && ./test.sh && cd ..
```

Dentro del test un pequeño truquito que tuve que hacer es corregir el código de salida de BennuGD, ya que travis respeta la nomenclatura unix, en la que un código de salida 0 es correcto, y algo mayor a 0 es error. El código final de test.sh me quedo así:

```bash
#!/bin/sh

# build the test program
bgdc 'test.prg'

# invert output status of bgdc
if [ $? -eq 1 ]
then
  exit 0
else
  exit 1
fi
```
Con esto, cuando el juego compila, Travis informa un build correcto. Excelente!

![Automate all the things](/img/automate.png 'Automate All The Things')

Bueno, por ahora lo dejo aca. Ya se está haciendo bastante extenso el post, y la idea no era aburrir así. Todos estos pasos que detallé se pueden ver directamente en el archivo .travis.yml que está en la raíz del repositorio de algunos proyectos, por ejemplo [bgd-tilescroll/.travis.yml](https://github.com/TorresBaldi/bgd-tilescroll/blob/master/.travis.yml)

Dejo pendiente para la próxima el tema de armar builds para cada plataforma, y también el subir esos builds a Github Releases, todo desde Travis.

Espero sirva a alguien,
Saludos! 🙂

