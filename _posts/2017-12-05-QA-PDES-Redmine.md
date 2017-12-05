---
layout: post
title:  "Bases de datos de Redmine y PDES"
date:   2017-12-05 11:03:00 +0000
categories:
---

## Prerrequisitos

- Instalar MySQL Server y MySQL Workbench (opcional)
[MySQL Downloads](https://dev.mysql.com/downloads/mysql/)

- Descargar y descomprimir la base de datos  
Para descomprimir, puedes usar [7zip](http://www.7-zip.org/)

## BD PDES

1. Crear una nueva base de datos  
`CREATE DATABASE tpdw`

2. Crear el usuario `pdes` en la base de datos y darle permisos  
`CREATE USER 'pdes'@'localhost'`  
`GRANT ALL ON pdes.* TO 'pdes'@'localhost'`

3. Conectarse a la base de datos por consola o con MySQL Workbench
`mysql -u [USER] -p`

4. Ejecutar el script de respaldo de la BD

5. Hacer consultas a la BD. La documentación completa sobre esta base de datos se encuentra en [DataWarehouse PDES](https://www.processdash.com/pdes-tpdw)
Por ejemplo, para obtener las fases de cada proyecto y los defectos inyectados y removidos en cada una:  
`SELECT DISTINCT p.project_name AS "Nombre del proyecto", ph.phase_key AS "Fase Id",
ph.phase_short_name AS "Fase (nombre corto)",
ph.phase_name AS "Fase",
(SELECT SUM(defect_fix_count)
FROM defect_log_fact
WHERE defect_log_fact.defect_injected_phase_key = ph.phase_key ) AS "Num. Defectos Inyectados",
(SELECT SUM(defect_fix_count)
FROM defect_log_fact
WHERE defect_log_fact.defect_removed_phase_key = ph.phase_key ) AS "Num. Defectos Removidos"
FROM phase AS ph
INNER JOIN plan_item AS pi
ON pi.plan_item_key = d.plan_item_key
INNER JOIN project AS p
ON p.project_key = pi.project_key
JOIN defect_log_fact AS d
WHERE ph.phase_key = d.defect_injected_phase_key OR ph.phase_key = d.defect_removed_phase_key
ORDER BY ph.phase_key`

## BD Redmine

1. Crear una nueva base de datos  
`CREATE DATABASE redmine`

2. Conectarse a la base de datos por consola o con MySQL Workbench
`mysql -u [USER] -p`

3. Ejecutar el script de respaldo de la BD

4. Hacer consultas a la BD.
