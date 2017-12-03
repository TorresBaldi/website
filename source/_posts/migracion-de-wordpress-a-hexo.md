---
title: Migración de Wordpress a Hexo
date: 2017-11-25 21:10:12
tags:
---

Sin querer __borré el sitio web anterior__, hecho en wordpress. Y para no tener que pasar por el doloroso proceso de restaurar una copia de seguridad, y aprovechando la situación...

_Llego el momento de armar un website nuevo! Yay!_

<!-- more -->

Esta vez, quise usar una herramienta de generación de sitios web estáticos.

La ventaja creo que en mi caso es la simpleza en el mantenimiento del sitio, ya que no hay ningún framework o librería corriendo en un servidor, con quien sabe que agujeros de seguridad. Era bastante tedioso que cada vez que entraba al sitio en wordpress tenia varias actualizaciones esperándome.

Un requisito que tambien me gustó incluir en la busqueda de la herramienta indicada fue que tenga la menor cantidad de dependencias que instalar, dentro de lo posible (eso tambien suma a la idea de simpleza). Y así fue que llegue a [HEXO](https://hexo.io/), un generador de sitios estáticos en NodeJS.

## Instalación y Desarrollo

Hacer andar hexo fue bastante sencillo, teniendo instalado NodeJS. Fue cosa de un par de comandos y listo, tal cual lo dice la documentación:

	npm install hexo-cli -g
	hexo init blog
	cd blog
	npm install
	hexo server

Una vez que tenia la base funcionando me fui directo a crear un template nuevo, desde 0. Creo que una excelente forma de entender como funciona una herramienta, es directamente usarla en un proyecto real.

Para los templates se pueden usar varios lenguajes (EJS, en este caso), así como tambien varias otras tecnologias (integración con SCSS, en este caso) y todo bastante transparente, ya que hexo se encarga de todo.

Después de algunas horas de trabajo es que llegué a lo que se ve ahora mismo.

## Uso

Hexo viene con una herramienta de linea de comandos que facilita su uso. Por ejemplo, para escirbir un nuevo post es ```hexo new post "Titulo del Post"```, esto crea un archivo en base a un _scaffold_ configurable. Es cuestion de editar ese archivo, y ya va a ser parte del blog. Esto mismo funciona para borradores (_drafts_) y para páginas (_pages_).

Después para poder ver el blog con los cambios, hay que correr ```hexo serve```, y desde el navegador visitar ```http://localhost:4000```. Listo, vemos cualquier cambio que hagamos en el sitio cada vez que refresquemos la pagina.

~~Por ultimo (y creo que esto es lo mejor), para hacer un deploy al servidor, sólo hay que hacer ```hexo deploy```, y el mismísimo hexo se encarga de todo de acuerdo a lo que hayamos configurado previamente. Excelente.~~

__Actualización__: Tuve problemas para configurar el sistema de deploy exactamente de la forma en que yo lo necesitaba (rsync, ignorando algunas carpetas en particual, todo por ssh, y usando una clave privada para autenticación) así que decidí optar por hacer los deploys de forma "personalizada" dentro de la ejecución de de Travis.

Como toque final subí el código a Github, [de manera pública en Github](https://github.com/TorresBaldi/website), y agregué Travis a todo ese proceso, asi los deploys se hacen de forma automática en cada commit.

## Tecnologías Utilizadas

- Backend
  - [__Hexo__](https://hexo.io): el framework que hace el trabajo
  - [__NodeJS__](https://nodejs.org/): el lenguaje y la plataforma donde ejecuta
  - [__Markdown__](https://es.wikipedia.org/wiki/Markdown): lenguaje en el que se escriben los posts
- Frontend
  - [__Bulma CSS__](https://bulma.io/)
  - [__SASS__](http://sass-lang.com/)
  - [__EJS templates__](http://ejs.co/)

## Lo que falta

Hubo bastantes cosas que no pude terminar todavía, pero con el correr de los dias espero incluir, por ejemplo:

- Comentarios con Disqus
- Favicon
- información de OpenGraph
- Mejorar la vista de Juegos y Herramientas
- Mejorar el menu en Mobile
- Terminar de editar los colores de Bulma
- Galería de Imágenes?

Si ven algún error o algo fuera de lugar, avisen: [hola@torresbaldi.com](mailto:hola@torresbaldi.com)!
