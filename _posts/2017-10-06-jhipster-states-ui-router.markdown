---
layout: post
title:  "JHipster: estados con ui-router"
date:   2017-10-06 14:01:00 +0000
categories:
---

# JHipster: estados con ui-router

Los estados en AngularJS definen la navigabilidad de la aplicación. JHipster utiliza [ui-router](https://ui-router.github.io/) como solución de administración de rutas de la aplicación.

El sub-generador de entidades de JHipster `jhipster entity` es capaz de crear las vistas, controladores, el servicio y los estados necesarios para las operaciones *CRUD* de la entidad.

En la siguiente imagen se muestran los estados necesarios para la administración de una entidad.

![Estados de la aplicación Web]({{ "/assets/jhipster-states-ui-router.png" | absolute_url }} "Estados de la aplicación Web JHipster")

Nótese que un par vista-controlador se puede utilizar para más de un estado en la aplicación tal como se aprecia en el caso de los estados `car.new`, `car.edit` y `car-detail.edit` los cuales usan el mismo par vista-controlador: `car-dialog.html` y `CarDialogController`.
