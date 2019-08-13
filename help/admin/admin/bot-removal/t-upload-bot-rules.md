---
description: Para importar reglas de bots de forma masiva, puede cargarse un archivo CSV que defina las reglas.
seo-description: Para importar reglas de bots de forma masiva, puede cargarse un archivo CSV que defina las reglas.
seo-title: Cargar reglas de bots
solution: Analytics
subtopic: Reglas de bots
title: Cargar reglas de bots
topic: Herramientas de administración
uuid: bd 70 c 199-5817-437 e -980 d -6 d 8 f 95 d 82 f 2 c
translation-type: tm+mt
source-git-commit: 319eba8896e629214000c56ad6ef6b5774e89e1e

---


# Cargar reglas de bots

Para importar reglas de bots de forma masiva, puede cargarse un archivo CSV que defina las reglas.

Cree un archivo CSV con las columnas siguientes en el orden presentado:

| Columna 1 | Columna 2 | Columna 3 | Columna 4 | Columna 5 |
|---|---|---|---|---|
| Nombre de Bot | IP Start | IP End | Agent Match Rule<br>(`contains` or `starts with`) | Agent Exclude<br>(255 char limit) |

Puede definir tres tipos de reglas de bots:

* Agente de usuario contiene o comienza con
* Coincidencia de dirección IP única o comodín
* Coincidencia de rango de IP

Cada fila del archivo de importación puede contener una sola de las siguientes definiciones de bots:

* **Agente de usuario contiene o comienza con**: proporcione una cadena del agente de usuario único en la columna Agent Include. Especifique el tipo de coincidencia que desea estableciendo *contiene* o *comienza con* en el campo Agent Match Rule. An optional value can be included in the Agent Exclude column that defines one or more pipe-delimited ( `|` ) strings that the Agent does not contain. Las coincidencias de cadena distinguen entre mayúsculas y minúsculas. Las columnas IP Start e IP End deben estar vacías.

* **Coincidencia de dirección IP única o comodín**: Para hacer coincidir una dirección IP única ( `10.10.10.1`) o dirección IP comodín ( `10.10.*.*`), coloque el mismo valor en las columnas IP Start e IP End. Match Rule, Agent Include y Agent Exclude deben estar vacías.

* **Coincidencia de rango IP**: defina un intervalo de direcciones IP usando las columnas IP Start e IP End. Wildcards can be used to match IP ranges, for example `10.10.10.*` to `10.10.20.*`. Match Rule, Agent Include y Agent Exclude deben estar vacías.

## Varias reglas combinadas con OR

Para buscar coincidencias de un bot utilizando una combinación de reglas unidas con OR (por ejemplo, agente de usuario o dirección IP), proporcione un nombre idéntico para todas las reglas que desee combinar en el campo de nombre de bot. No se admiten coincidencias AND.

## Sobrescribir todas las reglas con un archivo de carga

Seleccione la casilla **[!UICONTROL Sobrescribir reglas existentes]para eliminar todas las reglas existentes y sustituirlas por las reglas definidas en el archivo de carga.**

## Reglas de exportación

El botón **[!UICONTROL Exportar archivo de bots cargado]exporta todas las reglas definidas en la IU en formato CSV.**
