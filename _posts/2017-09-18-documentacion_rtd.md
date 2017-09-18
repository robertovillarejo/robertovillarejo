---
layout: post
title:  "Documentación con ReadTheDocs"
date:   2017-09-15 13:40:40 +0000
categories:
---
# Documentación con ReadTheDocs

Si las personas no saben por qué existe tu proyecto,
no lo usarán,
Si las personas no descifran cómo instalar tu código,
no lo usarán.
Si las personas no descifran cómo usar tu código,
no lo usarán.
[WriteTheDocs](http://www.writethedocs.org/guide/writing/beginners-guide-to-docs/#you-want-people-to-use-your-code)

## Getting Started

Debes tener instalado:

- [Python](https://www.python.org/)
- Sphinx
- El tema *ReadTheDocs*

### Instalación de Sphinx
`pip install sphinx sphinx-autobuild`

### Instalación del tema *ReadTheDocs*

#### Mediante git o descarga
Crea un *symlink* o copia dentro de tu carpeta `docs/_themes` el directorio `sphinx_rtd_theme/sphinx_rtd_theme` del repositorio [sphinx_rtd_theme](https://github.com/rtfd/sphinx_rtd_theme) para tener en tu proyecto: `docs/_themes/sphinx_rtd_theme`.
Luego añade las siguientes configuraciones en tu archivo `conf.py`:

`html_theme = "sphinx_rtd_theme"
html_theme_path = ["_themes", ]`

## Generando el sitio
Dentro de tu proyecto crea una carpeta para tu documentación:  
`mkdir docs`

Para crear los archivos base, ejecuta:
`cd docs  
sphinx-quickstart`

## Markdown
Si deseas escribir tu documentación en Markdown:  
`pip install recommonmark`

Luego, en tu `conf.py`:  
`from recommonmark.parser import CommonMarkParser
source_parsers = {
    '.md': CommonMarkParser,
}
source_suffix = ['.rst', '.md']`

## Documentando
Crea los archivos necesarios para tu documentación ya sea en formato `.rst` (reStructuredText) o en `.md` (markdown)

## Generando el sitio
Entra a tu carpeta de documentación `cd docs`
Y ejecuta `make html` para generar el sitio  

Abre el archivo `build/index.html` para ver el resultado
