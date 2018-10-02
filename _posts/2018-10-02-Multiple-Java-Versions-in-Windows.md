---
layout: post
title:  "Múltiples versiones de Java en Windows"
date:   2018-10-02 11:00:00 +0000
categories: java,windows
---

## Binarios de Java
Cuando se instala una versión de Java en Windows usando el instalador de Oracle (`.exe`), éste crea una carpeta en `C:\Program Files\Java\(JRE|JDK)_VERSION}`. Esta ruta es la que usamos para crear la variable `JAVA_HOME` y añadir `JAVA_HOME\bin` a la variable `PATH`.

Sin embargo, el instalador además añade a la carpeta `C:\Windows\System32` el binario `java.exe`. Es por esta razón que puedes ejecutar el comando `java` en el __cmd__ luego de instalar Java incluso sin haber creado la variable `JAVA_HOME` ni haber alterado la variable `PATH`. Este binario de java apunta siempre hacia la última versión instalada.

## Desarrolladores

Si utilizas Maven para desarrollar aplicaciones debes saber que esta herramienta utiliza la variable `JAVA_HOME` para trabajar.  
Por tanto, es posible conservar una versión de Java como la "principal" y usar otra versión de Java para desarrollar aplicaciones. 

Por ejemplo, es posible instalar Java 10 usando el instalador de Oracle y conservar esta versión como la principal. Al mismo tiempo, se pueden conservar otras versiones y modificar JAVA_HOME para "alternar" entre ellas.

## Instalar Java 10

Descarga y ejecuta el JRE 10 (`jre-10.0.2_windows-x64_bin.exe`) de la [página de descargas](https://www.oracle.com/technetwork/java/javase/downloads/jre10-downloads-4417026.html) pero no remuevas las versiones anteriores.

![Mantener versiones anteriores de Java]({{ "/assets/mantener-versiones-antiguas.png" | absolute_url }} "Mantener versiones anteriores de Java")

De esta manera, cuando necesites usar una versión distinta para desarrollo solo debes cambiar el valor de la variable `JAVA_HOME` y Maven utilizará esa versión de JDK.