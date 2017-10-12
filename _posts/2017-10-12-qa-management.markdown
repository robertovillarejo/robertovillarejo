---
layout: post
title:  "Administración de Casos de Uso, Casos de Prueba e Incidencias"
date:   2017-10-12 12:03:40 +0000
categories:
---

Para asegurar que un producto de software cumple efectivamente con los requerimientos y calidad deseados es necesario realizarle algunas pruebas. El área encargada de realizar dichas pruebas se llama QA (Quality Assurance o Aseguramiento de la Calidad). En el proceso de prueba, cuando se encuentra que no se cumple con algún requerimiento entonces se levanta una No Conformidad; cuando se encuentra algún problema durante la ejecución de un caso de prueba entonces se registra un defecto. Ambos, tanto la no conformidad como el defecto, deben seguir un proceso para su resolución además de notificar a las personas competentes.
Para gestionar estos procesos, el área de QA de Infotec ha probado antes algunas herramientas tales como RedMine. Sin embargo, se ha percatado de que éstas no han cubierto por completo las necesidades del área o se ha invertido demasiado tiempo en ajustarlas a las mismas.

## Herramientas

Debido a la neceidad que tiene QA, se realizó una comparación de distintas herramientas a fin de valorar cuál es la que mejor se adapta a sus necesidades e implantarla en el área.

### [Jira](https://es.atlassian.com/software/jira)
Jira es una aplicación de seguimiento de *issues*.

A pesar de que JIRA Software no se diseñó para [Administrar Casos de Prueba](https://confluence.atlassian.com/jirakb/using-jira-software-for-test-case-management-136872198.html), se puede configurar para soportar dicha función. Para lograrlo, existen dos formas:
  - Personalizando Jira
    * Pruebas manuales
    * Enlaza *bugs* con requerimientos
    * Tipos de *issues* personalizados tales como **Caso de prueba** y **User Story**
    * Múltiples afecta/arregla de versiones
    * Asignación automática y manual de *issues*
    * Controles de flujo de trabajo de QA, desarrollo y acciones de *tester*
    * Subtareas para pruebas manuales
    * Integración con repositorio de código fuente
    * Reportes
    * Comentarios y adjuntos en los *issues*
    * Personalización
    * Importación de otros sistemas
    * Usa una herramienta existente y conocida

  - Integrando algún Add-on del Marketplace de Jira. [Ver Add-Ons](https://marketplace.atlassian.com/categories/test-management)

      El Add-On más popular en el Marketplace de Jira es [Zephyr](https://marketplace.atlassian.com/plugins/com.thed.zephyr.je/cloud/overview) con un precio de $10 mensuales para 10 usuarios máximo.  

[x] Integración con Confluence

### [Confluence](https://support.atlassian.com/confluence-cloud/)
Confluence es una sistema colaborativo de documentación

[x] [Administración de casos de uso](https://confluence.atlassian.com/doc/blog/2015/08/how-to-document-product-requirements-in-confluence)  
[x] Integración con Jira  

### SpiraTest
[x] Administración de casos de Uso
[x] Administración de casos de Prueba

- Precio mensual:
  - Starter: $15.99/usuario
  - 3-Usuarios: $26.66/usuario
  - 5-Usuarios:  $23.99/usuario
  - [10, 20, 30, 50]-Usuarios: $19.99/usuario
  - 100-Usuarios: $11.99/usuario
  - 150-Usuarios: $9.99/usuario

### Easy Redmine

### HP - Application Lifecycle Management

### IBM Rational

### TestTrack

## Conclusión
SpiraTest ofrece una solución *end-to-end* de administración de proyectos. Sin embargo, sus precios son bastante elevados sobre todo en comparación con las herramientas de Atlassian.

Jira Software+Confluence son las mejores herramientas según los criterios de precio, facilidad de despliegue y facilidad de uso. Con ellas, luego de hacer algunas adaptaciones, es posible administrar distintos elementos de un sistema tales como:
  - Requerimientos
  - Casos de uso
  - *User stories*
  - Casos de prueba
  - Ciclos de ejecución de un plan de pruebas

Debido a que los casos de uso y los casos de prueba se encuentran ligados en estas herramientas, se logra trazabilidad entre ellos además de que se pueden generar reportes de algunas métricas.

### Implantación de Jira Software+Confluence
Algunos enlaces útiles para utilizar las herramientas de Atlassian:
  - Obtener una instancia de JIRA y una instancia de Confluence
  - [Documentar requerimientos con Confluence](https://confluence.atlassian.com/doc/blog/2015/08/how-to-document-product-requirements-in-confluence)
  - [Administración de usuarios](https://confluence.atlassian.com/adminjiraserver073/user-management-861253163.html)
  - [Usando JIRA Software para Administración de Casos de Prueba](https://confluence.atlassian.com/jirakb/using-jira-software-for-test-case-management-136872198.html)
  - [Personalizar JIRA para Administración de Caos de Prueba](https://confluence.atlassian.com/jirakb/customise-jira-for-test-case-management-191004869.html)
  - [Pantallas de proyecto, esquemas y campos](https://confluence.atlassian.com/adminjiraserver071/project-screens-schemes-and-fields-802592517.html)
