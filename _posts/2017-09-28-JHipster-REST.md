---
layout: post
title:  "Capa REST con JHipster"
date:   2017-09-28 12:50:00 +0000
categories:
---

# Capa REST con JHipster

La API REST de una aplicación debe retornar diferentes headers y códigos HTTP dependiendo de la petición hecha, es decir, de los verbos HTTP (POST, GET, PUT, DELETE).

A continuación se muestran los cuatro verbos (POST, GET, PUT, DELETE) junto con las posibles respuestas (códigos HTTP) de cada uno.  

La librería de JHipster proporciona dos clases que ayudan a retornar fácilmente los headers y códigos HTTP:  
- `io.github.jhipster.web.util.ResponseUtil`
- `mipaquetebase.web.rest.util.HeaderUtil` (se genera dentro de tu aplicación JHipster)

En esta publicación, también se muestra cómo retornar apropiadamente las respuestas HTTP utilizando estas dos clases.

## POST
Este verbo se usa para crear una nueva entidad.

Posibles códigos:
- **201 CREATED**: La entidad se creó exitosamente  
- **400 BAD REQUEST**: La petición está mál formulada  

### CREADO (CREATED 201)
Se envía:
- el código 201
- dos headers propios de la aplicación:
  * la alerta de entidad creada
  * el id de la entidad creada
- la entidad creada se envía en el cuerpo

**Código:** 201  
**Headers:**  
```
X-miApp-alert: miApp.suscription.created
X-miApp-params: a4fdbc56
location: api/suscription/a4fdbc56
```
**Body:**  
```
{
    “id”: “a4fdbc56”,
    “nombre”:  “Mi suscripción”
}
```

#### Con JHipster
```
ResponseEntity

.created(
new URI("/api/subscriptions/" + suscription.getId()))

.headers(HeaderUtil.createEntityCreationAlert(“suscription”, suscription.getId().toString()))

.body(suscription);
```

### SOLICITUD INCORRECTA (BAD REQUEST 400)
Se envía:
- el código 400
- dos headers propios de la aplicación:
  * el código de error
  * el nombre de la entidad que falló crearse
- un cuerpo vacío

**Código:** 400  
**Headers:**  
```
X-miApp-error:error.idexists
X-miApp-params: suscription
```
**Body:** Nulo

#### Con JHipster
```
ResponseEntity

.badRequest()

.headers(HeaderUtil.createFailureAlert(“suscription”, "idexists", "Una suscripción nueva no puede tener un id"))

.body(null);
```

## GET
Este verbo se usa para obtener una entidad

### OK (200 OK)
Se envía:
- el código 200
- el cuerpo con la entidad

**Código:** 200  
**Headers:**  
**Body:**  
```
{
    “id”: “a4fdbc56”,
    “nombre”:  “Mi suscripción”
}
```

### NO ENCONTRADO (NOT FOUND 404)
Se envía:
- el código 404
- el cuerpo nulo

**Código:** 200  
**Headers:**  
**Body:** Nulo  

#### Con JHipster
Para ambos casos: **OK** y **NOT FOUND**
```
ResponseUtil.wrapOrNotFound(Optional.ofNullable(subscription));
```

## PUT
Este verbo se usa para actualizar una entidad

## OK (200 OK)
Se envía:
- el código 200
- dos headers propios de la aplicación:
  * la alerta de entidad actualizada
  * el id de la entidad actualizada
- el cuerpo con la entidad actualizada

**Código:** 200  
**Headers:**  
```
X-miApp-alert: miApp.suscription.updated
X-miApp-params: a4fdbc56
```
**Body:**  
```
{
   “id”: “a4fdbc56”,
   “nombre”:  “Mi suscripción actualizada”
}
```

#### Con JHipster
```
ResponseEntity

.ok()

.headers(HeaderUtil.createEntityUpdateAlert(“suscription”, subscription.getId().toString()))

.body(result);
```

## DELETE
Este verbo se usa para borrar una entidad

## OK (200 OK)
Se envía:
- el código 200
- dos headers propios de la aplicación:
  * la alerta de entidad eliminada
  * el id de la entidad eliminada

**Código:** 200  
**Headers:**  
```
X-miApp-alert: miApp.suscription.deleted
X-miApp-params:  a4fdbc56
```
**Body:** Nulo  

#### Con JHipster
```
ResponseEntity

.ok()

.headers(HeaderUtil.createEntityDeletionAlert(“suscription”, id.toString()))

.build();
```
