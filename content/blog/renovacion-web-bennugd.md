---
title: Renovación de la Web de BennuGD
date: 2018-11-29
---

 Se está dando un resurgimiento de la comunidad BennuGD, originando un interesante debate en [el foro de BennuGD](http://forum.bennugd.org/index.php/topic,4735.0.html) que después se trasladó a un server de Discord, principalmente con intenciones de dar fuerza a la comunidad div-like en general, unificando los distintos nichos en un grande y nuevo **DivHub**!

Esto provocó que reaparecieran mis ganas de retomar el proyecto de dale una apariencia renovada al sitio de BennuGD, algo que habia comenzado [hace tiempo](http://forum.bennugd.org/index.php/topic,4605.msg72239.html#msg72239). Así que me puse manos a la obra con este proyecto, y hoy les cuento de que se trata.

Estoy armando una web en la que convivan el sitio web, la documentación y la seccion proyectos de BennuGD. Aunque si esto resulta, tal vez se pueda extender a unificar todas las comunidades.

Todo el contenido del sitio estaría alojado en un repositorio en github, facilitando enormemente las tareas de mantenimiento y edición, permitiendo un trabajo de **forma colaborativa**.

{{< figure src="/blog/screenshot_2018-11-30_bennugd.png" caption="Vista Previa de la nueva documentación de BennuGD. Se puede ver en [tehuel.github.io/bennugd-redesign](https://tehuel.github.io/bennugd-redesign)">}}

## El Lado Técnico de la Web

Inicié este nuevo proyecto usando [Hugo](https://gohugo.io), que es un generador de sitios web estáticos. Los sitios web estáticos, junto con el JAMStack son tecnologías que están creciendo mucho ultimamente, porque proveen de muchas ventajas.

A grandes razgos la idea es no necesitar más de un servidor web que esté procesando los pedidos de los visitantes de una web, teniendo que conectarse a bases de datos y armando las vistas en HTML. Sino que en cambio, esto se reemplaza por un repositorio git con el contenido del sitio web, y un proceso de "build" en el que se generan todos los HTMLs que componen al sitio final. Este procesamiento, o build del sitio se hace una unica vez, dando como resultado archivos estáticos, que se suben directamente al servidor y son los mismos que ven los visitantes.

{{< figure src="/blog/static-vs-dynamic.png" caption="Diagrama comparativo entre la simpleza de una web estática, contra la complejidad de una web dinámica">}}

Esto tiene varias ventajas, como pueden ser:

- Elimina la necesidad de **actualizaciones y mantenimiento** de los servidores: lo que se sube a internet es unicamente archivos estáticos, como HTML, CSS, y JS. No hay que entrar a actualizar wordpress ni nada a los servidores, porque no es necesario instalar nada de eso en los servidores. No hay problemas de seguridad ni hackeos relacionados.
- Permite incorporar técnicas modernas de desarrollo de software, como git e integración continua. Explico en detalle
- versionado con git: como todo el contenido del sitio web está dentro de un repositorio, es mucho más simple llevar un control de los cambios, y ante cualquier problema siempre se puede volver en la historia y deshacer cualquier cambio.
- desarrollo colaborativo, con github: que el repositio de la web sea visible de forma publica en internet permite que cualquiera pueda colaborar con sus cambios a la web, a través de Pull Requests


## Para cuando va a estar?

Bueno, esto recien comienza, así que imposible estimar una fecha. De todas maneras están invitados a seguir el desarrollo en el [repositorio del proyecto en github](https://github.com/tehuel/bennugd-redesign).

También se puede ver la vista previa en github-pages, yendo a [tehuel.github.io/bennugd-redesign](https://tehuel.github.io/bennugd-redesign).

Por ahora es todo, pero espero muy pronto traer más novedades.

Nos Vemos! 👍
