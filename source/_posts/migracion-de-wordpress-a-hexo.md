---
title: Migración de Wordpress a Hexo
date: 2017-11-25 21:10:12
tags:
---

Sin querer __borré el sitio web anterior__, hecho en wordpress. Y para no tener que pasar por el doloroso proceso de restaurar una copia de seguridad, y aprovechando la situación...

_Llego el momento de armar un website nuevo! Yay!_

<!-- more -->

Esta vez, quise usar una herramienta de generación de sitios web estáticos

La ventaja creo que en mi caso es la simpleza en el mantenimiento del sitio, ya que no hay ningún framework o librería corriendo en un servidor, con quien sabe que agujeros de seguridad. Era bastante tedioso que cada vez que entraba al sitio en wordpress tenia varias actualizaciones esperándome.

Un requisito que tambien me gustó incluir en la busqueda de la herramienta indicada fue que tenga la menor cantidad de dependencias que instalar, dentro de lo posible (eso tambien suma a la idea de simpleza). Y así fue que llegue a [HEXO](https://hexo.io/), un generador de sitios estáticos en NodeJS.

## Instalación y Desarrollo

Hacerlo funcionar fue muy sencillo, teniendo ya instalado Node fue cosa de un par de comando y listo. Y una vez que tenia la base funcionando me fui directo a crear un template nuevo, desde 0. Creo que una excelente forma de entender como funciona una herramienta, es directamente usarla en un proyecto real.

Después de algunas horas de trabajo es que llegué a lo que se ve ahora mismo.

## Tecnologías Utilizadas

- Backend
  - __Hexo__: el framework que hace el trabajo
  - __NodeJS__: el lenguaje y la plataforma donde corre
  - __Markdown__: lenguaje en el que se escriben los posts
- Frontend
  - __Bulma CSS__
  - __EJS templates__
  - __SASS__

## Lo que falta

Si ven algún error o algo fuera de lugar, avisen! Hubo bastantes cosas que no pude terminar todavía, pero con el correr de los dias espero incluir:

- Comentarios con Disqus
- Favicon
- información de OpenGraph
- Mejorar la vista de Juegos y Herramientas
- Mejorar el menu en Mobile
- Terminar de editar los colores de Bulma
- Galería de Imágenes?
