---
layout: post
title:  "Herramienta para base de conocimientos"
date:   2017-06-06 18:42:40 +0000
categories: 
---

# Comparación de herramientas para construir una base de conocimientos para la DADS Infotec

## Criterios a evaluar:
  - Facilidad de edición (añadir nuevo contenido)
  - Faclidad de despliegue (Cloud pública, Cloud privada, Infraestructura propia)
  - Facilidad de versionar
  - Agradable a la vista
  - Precio

## Herramientas:

### GitBook

Gibook es una plataforma en línae para crear documentación.

- Facilidad de edición:
  - Gitbook cuenta con un [editor gráfico](https://www.gitbook.com/editor) en línea con botones para añadir diferentes estilos de texto como encabezados, citas, negritas, subrayado, etc. Este editor va generando un archivo markdown de fondo.
  - También se puede utilizar AsciiDoc para añadir contenido
  - Se pueden añadir [plugins](https://plugins.gitbook.com/) en la plataforma *online* y también en la instalación local.

- Facilidad de versionar:
  - Se integra perfectamente con Github, aunque por sí solo, Gitbook utiliza Git para administrar sus versiones.

- Faclidad de despliegue:
  - Tan fácil como usar el botón de guardar en el editor en línea para ver los cambios reflejados en el libro.
  - Si se tiene ligado Gitbook con Github, también se puede hacer un push a Github para que se publiquen los cambios en Gitbook.
  - Gitbook tiene una [aplicación de escritorio](https://www.gitbook.com/editor) para Windows, Mac OS y Linux que soporta la edición *offline* del libro.
  - Se puede [instalar](https://github.com/GitbookIO/gitbook/blob/master/docs/setup.md) `gitbook-cli` mediante `npm` para tener una instancia local de GitBook

- Agradable a la vista:
  - Gitbook cuenta con botones para cambiar el color de la página y el tamaño de la fuente.
  - Es posible personalizar los estilos (CSS) de un libro en Gitbook o utilizar algún tema creado por la comunidad.
  - Gitbook proporciona tres plantillas diferentes para crear contenido:
    - Libro y manual
    - Documentación de API
    - Base de conocimientos

- Precio: **Gratis** con [planes de pago](https://www.gitbook.com/pricing) si se desea hacer privados los libros y aumentar el número de colaboradores.

### Bookdown

[Demo](https://bookdown.org/yihui/bookdown-demo/)  

Es un paquete del lenguaje R que utiliza R Markdown para la redacción de libros y reportes/artículos. Está orientado a la presentación de datos en sus libros pero también se puede utilizar para escribir otro tipo de publicaciones.

- Facilidad de edición:
  - Se debe instalar el lenguaje R y el paquete rstudio

- Facilidad de versionar
  - Para editar o añadir contenido es necesario crear un repositorio git y luego escribir el contenido en MarkDown

- Faclidad de despliegue
  - Para publicar es necesario registrarse con una cuenta de Google en bookdown.org y subir los cambios desde consola.

- Agradable a la vista:
  - Diferentes estilos de lectura: sepia, blanco, noche
  - Configurable el tamaño de la lectura
  - Búsqueda de contenido dentro de la página actual (no busca de manera global ni en el índice)

- Precio: **Gratis**

### Jekyll

[Demo](https://github.com/jekyll/jekyll/wiki/sites)  

Jekyll es una gema de Ruby que ayuda a generar sitios estáticos a partir de archivos de texto (generalmente Markdown). Jekyll es el motor detrás de Github Pages.

- Facilidad de edición:
  - Para añadir o editar contenido se manipulan archivos de texto (por defecto funciona con Markdown). Estos archivos se colocan dentro de una carpeta según la estructura que se defina y se genera el sitio (archivos HTML) con Jekyll.

- Facilidad de versionar:
  - Debido a que se trata de archivos de texto, se integra fácilmente con Git.

- Faclidad de despliegue:
  - El despliegue se puede hacer en cualquier servidor web, puesto que se trata de archivos HTML y CSS.

- Agradable a la vista:
  - Por defecto Jekyll define algunos estilos que son agradables a la vista pero no muy acertados para la documentación de una base de conocimientos.
  - Si se desea lograr un aspecto específico para una base de conocimientos se debe invertir más tiempo en el diseño del sitio

- Precio: **Gratis**

### ReadTheDocs

[Demo](https://docs.readthedocs.io/en/latest/index.html)  

ReadTheDocs es una plataforma en la que se aloja la documentación para la comunidad de código abierto.

- Facilidad de edición:
  - El contenido se escribe en archivos Markdown o reStructuredText

- Facilidad de versionar:
  - Se integra perfectamente con Git/Github a través de [Webhooks](https://developer.github.com/webhooks/)

- Faclidad de despliegue:
  - Los cambios se reflejan de manera automática en la plataforma https://readthedocs.org/
  - Se puede ejecutar una instancia local de ReadTheDocs ([instalación](https://docs.readthedocs.io/en/latest/install.html))

- Agradable a la vista:
  - Tiene un aspecto totalmente orientado a la lectura de documentación

- Precio: **Gratis**

### Github Pages
[Demo React docs](https://facebook.github.io/react/)  
[Demo Boostrap docs](https://getbootstrap.com/docs/4.0)

Github Pages es el servicio de Github para alojar sitios estáticos de proyectos, organizaciones o usuarios (funciona con Jekyll)

- Facilidad de edición:
  - El contenido se escribe en archivos Markdown

- Facilidad de versionar:
  - Se integra directamente a un repositorio Github

- Faclidad de despliegue:
  - Utiliza webhooks para detectar cambios en un repositorio Github y publicar el contenido

- Agradable a la vista:
  - Tiene una lista corta de [temas soportados](https://pages.github.com/themes/)
  - Los temas soportados tienen más un aspecto de blog que de documentación

- Precio: **Gratis**

### DocGist
[demo](http://gist.asciidoctor.org/?github-mraible/jhipster4-demo//README.adoc)  

DocGist es una herramienta proxy URL que convierte documentos [AsciiDoc](http://asciidoctor.org/docs/asciidoc-syntax-quick-reference). La conversión a HTML se realiza en el navegados (del lado del cliente) usando [Asciidoctor.js](https://github.com/asciidoctor/asciidoctor.js).

- Facilidad de edición:
  - El contenido se escribe en archivos AsciiDoc

- Facilidad de versionar:
  - Se integra fácilmente a Gists de Github, repositorios de Github, carpetas de Dropbox y otros como *Google Documents*.

- Faclidad de despliegue:
  - La conversión se realiza del lado del cliente (en el navegador).
  - Originalmente es una gema de Ruby pero también se puede utilizar directamente el Asciidoctor.js

- Agradable a la vista:
  - Tiene una lista corta de [temas soportados](https://pages.github.com/themes/)
  - Los temas soportados tienen más un aspecto de blog que de documentación

- Precio: **Gratis**

### Docsify.js.org

[demo](https://dobromir-hristov.github.io/palettify/#/)  

Docsify es un generador de sitios de documentación. A diferencia de GitBook, no genera archivos html estáticos sino que *parsea* los archivos Markdown *al-vuelo* y los muestra como un sitio. Docsify funciona junto con Github Pages.

- Facilidad de edición:
  - El contenido se escribe en archivos Markdown

- Facilidad de versionar:
  - Se integra fácilmente a Git Pages

- Faclidad de despliegue:
  - Es necesario usar Git Pages

- Agradable a la vista:
  - Actualmente sólo tiene tres temas disponibles (CSS).

- Precio: **Gratis**

### Bookbinder

[demo](https://docs.cloudfoundry.org/deploying/index.html)

Es una gema de Ruby con una interfaz de línea de comandos para convertir archivos Markdown o DITA a un sitio estático HTML. Actualmente el proyecto se encuentra **inactivo** sin planes de dar mantenimiento al código.

- Facilidad de edición:
  - El contenido se escribe en archivos Markdown o DITA

- Facilidad de versionar:
  - Se integra fácilmente con repositorios Git

- Faclidad de despliegue:

- Agradable a la vista:

- Precio: **Gratis**

### Readme.io  
### Gelato.io  
### Zendesk Knowledge Base  
