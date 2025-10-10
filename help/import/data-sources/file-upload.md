---
title: Cargar archivo de fuentes de datos en Adobe
description: Proceso para cargar un archivo de fuentes de datos en Adobe Analytics para su ingesta.
exl-id: 64e3cd70-b511-4c4e-abd0-94eb36bc3519
feature: Data Sources
role: Admin
source-git-commit: 27bcbd638848650c842ad8d8aaa7ab59e27e900e
workflow-type: tm+mt
source-wordcount: '367'
ht-degree: 1%

---

# Cargar archivo de fuentes de datos en Adobe

El envío de un archivo de fuentes de datos a Adobe implica un flujo de trabajo de FTP autenticado tradicional. Puede usar el Explorador de Windows, Finder o un cliente FTP específico para cargar los archivos deseados en la ubicación FTP de Adobe.

Busque las credenciales de FTP en el [administrador de fuentes de datos](manage.md). Cada origen de datos tiene un vínculo a su **[!UICONTROL información de FTP]**. Cada ubicación FTP está dedicada a ese origen de datos específico; no puede utilizar la misma ubicación FTP para varios orígenes de datos.

Por motivos de seguridad, las ubicaciones de FTP sin actividad durante más de 30 días están desactivadas.

## El archivo `.fin`

Una parte vital de la ingesta correcta de un archivo de fuentes de datos es la inclusión de un archivo de `.fin`. Este archivo indica a Adobe que el archivo de datos está listo para procesarse. Si carga un archivo de fuentes de datos sin el archivo `.fin` correspondiente, Adobe nunca procesará esos datos.

El archivo `.fin` tiene las siguientes propiedades:

* El archivo tiene la extensión `.fin`. Asegúrese de que el sistema operativo le permite ver y editar tipos de archivos.
* El archivo está vacío. No almacene datos dentro del archivo `.fin`.
* El archivo tiene el mismo nombre que el archivo de fuente de datos. Por ejemplo, si carga un archivo de fuentes de datos denominado `example.txt`, el archivo `.fin` **debe** llamarse `example.fin`. Si no tienen un nombre idéntico, Adobe nunca procesa el archivo de fuente de datos.

Una vez que el archivo de origen de datos y el archivo `.fin` se hayan cargado al sitio FTP, Adobe procesará el archivo. No cargue el archivo de `.fin` hasta que el archivo de fuente de datos se haya cargado completamente. Si el archivo `.fin` se carga prematuramente, Adobe recupera e ingiere el archivo parcialmente cargado, generando posibles errores.

## Orden de procesamiento

Si carga varios archivos al mismo tiempo en el sitio FTP, Adobe los ingresa en orden alfanumérico. Si su organización requiere que los archivos se introduzcan en un orden específico, asegúrese de que sus nombres de archivo tengan un nombre alfanumérico.

## Tiempo de procesamiento

Para garantizar el procesamiento más rápido de los archivos, Adobe recomienda agregar datos de métricas en una sola fila por fecha. Por ejemplo, si bien este archivo de fuentes de datos es válido, se procesaría más lentamente:

| `date` | `eVar1` | `event1` | `event2` | `event3` |
| --- | --- | --- | --- | --- |
| `07/24/YYYY` | `red` | `1` | | |
| `07/24/YYYY` | `red` | `1` | | |
| `07/24/YYYY` | `red` | | `1` | |
| `07/24/YYYY` | `red` | | | `1` |

Este archivo se procesaría más rápido, y contiene los mismos datos:

| `date` | `eVar1` | `event1` | `event2` | `event3` |
| --- | --- | --- | --- | --- |
| `07/24/YYYY` | `red` | `2` | `1` | `1` |
