# Análisis de incidentes delictivos de Boston con PostgreSQL

Proyecto académico desarrollado para el curso **Bases de Datos — CC3201** de la Universidad de Chile.

El proyecto aborda el diseño, implementación, carga, consulta y optimización de una base de datos relacional construida a partir del dataset **Crimes in Boston**.

## Objetivo

Transformar un conjunto de datos crudo de incidentes delictivos en una base de datos relacional normalizada que permita realizar análisis temporales, geográficos y por tipo de delito.

## Dataset

El conjunto original contiene aproximadamente **319.073 registros** y variables relacionadas con:

- número de incidente;
- código y descripción de la ofensa;
- distrito;
- calle;
- fecha y hora;
- día de la semana;
- mes y año;
- clasificación UCR.

## Diseño de la base de datos

El dataset original fue normalizado y dividido en las siguientes tablas:

- `Distrito`
- `Ofensa`
- `Incidente`
- `Ocurre_en`
- `Comete`

El modelo fue diseñado para cumplir con:

- Primera Forma Normal;
- Segunda Forma Normal;
- Tercera Forma Normal;
- Forma Normal de Boyce-Codd.

## Implementación

La base de datos fue implementada en PostgreSQL utilizando dos esquemas:

- `Tamal_1`: tablas relacionales normalizadas;
- `Tamal_2`: zona de staging para cargar los datos crudos.

## Procesamiento de datos

Durante la carga se realizaron tareas como:

- conversión del archivo original a CSV;
- eliminación de valores duplicados;
- exclusión de registros nulos;
- carga mediante `COPY`;
- inserción de datos normalizados con `SELECT DISTINCT`.

## Consultas analíticas

Se desarrollaron consultas para responder preguntas como:

1. Evolución anual de crímenes por distrito.
2. Tipos de delito más frecuentes por día de la semana.
3. Horas con mayor frecuencia de delitos según su tipo.
4. Variación mensual de incidentes.
5. Calles con mayor concentración de delitos.
6. Relación entre tipos de crimen y distritos.

Las consultas utilizan técnicas como:

- `JOIN`;
- subconsultas;
- CTE;
- funciones de ventana;
- `RANK`;
- `ROW_NUMBER`;
- `LAG`;
- agregaciones y filtros.

## Optimización

Se crearon índices sobre campos utilizados frecuentemente en:

- joins;
- filtros temporales;
- búsquedas por distrito;
- búsquedas por calle;
- búsquedas por tipo de delito.

Entre ellos:

- índices por `OFFENSE_CODE`;
- índices por `INCIDENT_NUMBER`;
- índices por `YEAR`, `MONTH`, `HOUR` y `DAY_OF_WEEK`;
- índices por `STREET` y `Codigo`.

## Resultados

El análisis permitió identificar:

- distritos con mayor cantidad de delitos;
- evolución temporal de incidentes;
- delitos más frecuentes por día;
- calles con mayor concentración de crímenes;
- patrones horarios y mensuales.

## Archivos

- `Hito_N4_corregido(1).pdf`: informe final completo del proyecto.

## Tecnologías

- PostgreSQL
- SQL
- Modelamiento entidad-relación
- Normalización
- Optimización de consultas
- Análisis de datos
- Git
- GitHub

## Integrantes

- Esperanza Cares
- Fernando Palma
- Pablo Duarte

## Contexto académico

Proyecto desarrollado para el curso **CC3201 — Bases de Datos** de la Universidad de Chile.
