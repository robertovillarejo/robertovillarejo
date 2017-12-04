---
layout: post
title:  "Reportes Process Dashboard"
date:   2017-12-04 16:55:00 +0000
categories:
---


## Prerrequisitos:
- Tener instalado el [Process Dashboard 2.4 ](https://www.processdash.com/download)

A continuación se enlistan los pasos para poner a funcionar el **add-on de reportes** de David Tuman. Los pasos oficiales se encuentran en este [enlace](https://github.com/dtuma/processdash-reporting-demo/wiki). Sin embargo, **existe un *bug* en la versión 2.2 del cliente Process Dashboard** que impide ver correctamente los reportes del add-on. Por esta razón, se necesitan pasos adicionales para poner a funcionar este módulo.

## Pasos
1. Generar el war de reportes tal como lo indica David Tuman en su [wiki](https://github.com/dtuma/processdash-reporting-demo/wiki) o descargarlo de [aquí](https://mega.nz/#!OlJGAZDA!MUmWPU2vLk765Et_SlOdPbS9ft6wNPVP-f8c8Rou5A0)
2. Copiar el war a la carpeta de los add-ons del Process Dashboard.
  Para saber cuál es la carpeta de donde el Process Dashboard lee los add-ons, consulta el **Menú principal > Ayuda > Sobre Process Dashboard > Configuración**.  
  Verás una leyenda como ésta:
  `Dashboard add-ons también seran leidos del siguiente directorio:
  /home/roberto/.processdash/Templates`

3. Descargar el `.jnlp` del PDES y ejecutarlo
  Entra al sitio web del PDES y descarga el *Dataset* que desees. Luego, ejecútalo y escribe tus credenciales.  
  Según las instrucciones en la wiki, con estos pasos ya debería funcionar el add-on instalado. Sin embargo, el archivo `.jnlp` es la **versión 2.2 del Process Dashboard** y el add-on no funciona con esta versión.  
  Por tanto, haremos un respaldo de los datos para abrirlo con la **versión 2.4**

4. Guardar el grupo de datos del proyecto en una carpeta de tu preferencia  
  En el menú, selecciona **Archivo > Guardar respaldo de datos**

5. Cerrar el cliente PDES (el `.jnlp` descargado)

6. Iniciar el PDES 2.4

7. Abrir el grupo de datos respaldado  
  En el menú principal, **Herramientas > Abrir grupo de datos** y selecciona el archivo `.zip` guardado previamente

8. Abrir **Reporting Demonstrations**  
  Luego del paso anterior, se mostrará una ventana con una lista de opciones. Selecciona la última opción **Reporting Demonstrations** y se abrirá tu navegador web.

9. Elige un reporte para verlo  
  En la página que recién abrió, elige el reporte que prefieras sobre el proyecto.  
  En el reporte **Plan Summary** encontrarás la información sobre los defectos inyectados en y removidos en cada fase del proyecto.
