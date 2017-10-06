---
layout: post
title:  "Curso JHipster"
date:   2017-09-28 20:00:40 +0000
categories:
---

# Preparación del ambiente de trabajo
Las herramientas necesarias para trabajar con JHipster:
- Git
- Maven
- MongoDB
- JHipster

## Git
Para instalar Git en Ubuntu:
`apt-get install git`

Para instalar Git en Windows:  
[Descarga](https://git-scm.com/download/win) el instalador.

## Maven
Para instalar Maven en Ubuntu:
`apt-get install maven`

Para instalar Maven en Windows:  
Puedes hacerlo mediante el administrador de paquetes `scoop`.  
Primero instala [scoop](http://scoop.sh/)  
luego ejecuta `scoop install maven`

## MongoDB Community Edition
Para instalar MongoDB CE en Ubuntu 16.04 ([guía oficial](https://docs.mongodb.com/manual/tutorial/install-mongodb-on-ubuntu/)):
Ejecuta:
```
sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv 0C49F3730359A14518585931BC711F9BA15703C6
echo "deb [ arch=amd64,arm64 ] http://repo.mongodb.org/apt/ubuntu xenial/mongodb-org/3.4 multiverse" | sudo tee /etc/apt/sources.list.d/mongodb-org-3.4.list
sudo apt-get update
sudo apt-get install -y mongodb-org
```
Inicia MongoDB:
`sudo service mongod start`

Para instalar MongoDB CE en Windows 64-bit:
Descarga [aquí](https://www.mongodb.com/download-center#community) el instalador.

## JHipster
Sigue la [guía oficial de instalación](http://www.jhipster.tech/installation/)

# Arquetipo JHipster
- Generación de la aplicación JHipster

  ```
  mkdir miApp
  cd miApp
  jhipster
  ```
  [Guía en español](https://robertovillarejo.gitbooks.io/jhipster/content/chapter1.html)
  [Guía en inglés](http://www.jhipster.tech/creating-an-app/)

- Recorrido por el arquetipo
  ```
  |--io.github.robertovillarejo
    |--domain                        - Los objetos de dominio (POJO) mapeados a la BD
    |--repository                    - Las interfaces de repositorio que extienden de JpaRepository o MongoRepository
    |--service                       - Las interfaces de los servicios    (opcional)
    |--service.impl                  - La implementación de los servicios (opcional)
    |--web.rest                      - Los `RestController` que usan al repositorio o al servicio
  ```

# Tecnología REST
[Capa REST con JHipster](https://robertovillarejo.github.io/2017/09/28/JHipster-REST.html)

# Swagger

# CRUD con JHipster
Los pasos para lograr un CRUD REST con JHipster son los siguientes:
- creación de la entidad de dominio y mapeo a la base de datos
- creación del repositorio con Spring Data
- creación de la interfaz del servicio y su implementación
- creación del servicio REST

# Spring Data
## Métodos de repositorio

# AngularJS
## CRUD con AngularJS
- Vista
- Controlador
- Servicio

## Rutas

## Internacionalización
