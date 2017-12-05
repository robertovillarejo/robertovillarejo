---
layout: post
title:  "Personalizando JIRA para Casos de Prueba"
date:   2017-10-16 11:39:30 +0000
categories:
---

## Pasos
Primero se crearán los esquemas que serán utilizados por los proyectos:
  1. Crear un nuevo Field Configuration Scheme llamado "Infotec Configuration Scheme"
  2. Crear un nuevo Issue Type Screen Scheme llamado "Infotec Issue Type Screen Scheme"
  3. Crear un nuevo Workflow Scheme llamado "Infotec Workflow Scheme"

Luego, se crearán las implementaciones de cada tipo de _issue_
  1. Crear el nuevo tipo de _issue_
  2. Crear los campos personalizados (sin asociarlo a pantallas)
  3. Crear las configuraciones de campos
  4. Crear el esquema de Configuración de Campos (asociar la configuración de campos con el _issue_ creado)
  5. Crear las pantallas (asociar los campos personalizados)
  6. Crear los esquemas de pantallas
  7. Crear el esquema de pantalla por tipo de issue (asociar el esquema de pantalla con el _issue_ creado)

## Use Case

1. Definir un nuevo tipo de _issue_ en `Configuración>Incidencias>Añadir tipo de incidencia`:
  - Nombre: Use Case
  - Descripción: A use case of the system
2. Definir los campos personalizados en `Configuración>Incidencias>Campos personalizados>Añadir campo personalizado`:
  - name: Línea de texto
3. Crear una nueva configuración de campo "Test Field Configuration" en `Configuración>Incidencias>Configuraciones de campos>Añadir configuración de campos`. Hacer obligatorios los siguientes campos:
4. Crear las pantallas para el caso de prueba. En `Configuración>Incidencias>Pantallas>Añadir Pantalla`:


## Test Case

1. Definir un nuevo tipo de _issue_ en `Configuración>Incidencias>Añadir tipo de incidencia`:
  - Nombre: **Test Case**
  - Descripción: A test case
2. Definir los campos personalizados en `Configuración>Incidencias>Campos personalizados>Añadir campo personalizado`:
  - Precondiciones: Campo de texto (varias líneas)
  - Pasos: Campo de texto (varias líneas)
  - Resultados esperados: Campo de texto (varias líneas)
  - Resultados obtenidos: Campo de texto (varias líneas)
3. Crear una nueva configuración de campo "Test Field Configuration" en `Configuración>Incidencias>Configuraciones de campos>Añadir configuración de campos`. Hacer obligatorios los siguientes campos:
  - Precondiciones
  - Pasos
  - Resultados esperados
4. Crear las pantallas para el caso de prueba. En `Configuración>Incidencias>Pantallas>Añadir Pantalla`:  

|Nombre                     |Descripción                                                          |
|:--------------------------|:--------------------------------------------------------------------|
| Create Test Case Screen   | Setup the general test for approval                                 |
| Schedule Test Case Screen | Setup approved test template for use in a specific test environment |
| Test Case Screen          | Edit an invalid issue and reopen for review                         |
| Test Results Screen       | Record test case results                                            |

5. Asociar los campos personalizados a las pantallas recién creadas. Para esto se debe ir a `Configuración>Incidencias>Campos personalizados` y seleccionar la opción Configurar.

| Nombre del campo     | Pantallas asociadas                       |
|:---------------------|:------------------------------------------|
| Precondiciones       |                                           |
| Resultados obtenidos | Test Case Screen, Test Results Screen     |
| Resultados esperados | Create Test Case Screen, Test Case Screen |
| Pasos                | Create Test Case Screen, Test Case Screen |

## Nonconformity

### Custom Fields
