---
title: Cargar archivo de fuentes de datos en el Adobe
description: Proceso para cargar un archivo de fuentes de datos en Adobe Analytics para su ingesta.
exl-id: 64e3cd70-b511-4c4e-abd0-94eb36bc3519
feature: Data Sources
role: Admin
source-git-commit: 27bcbd638848650c842ad8d8aaa7ab59e27e900e
workflow-type: tm+mt
source-wordcount: '367'
ht-degree: 1%

---

# Cargar archivo de fuentes de datos en el Adobe

El envío de un archivo de fuentes de datos al Adobe implica un flujo de trabajo de FTP autenticado tradicional. Puede usar el Explorador de Windows, Finder o un cliente FTP específico para cargar los archivos deseados en la ubicación FTP de Adobe.

Busque las credenciales de FTP en la [Administrador de fuentes de datos](manage.md). Cada fuente de datos tiene un vínculo a su **[!UICONTROL Información de FTP]**. Cada ubicación FTP está dedicada a ese origen de datos específico; no puede utilizar la misma ubicación FTP para varios orígenes de datos.

Por motivos de seguridad, las ubicaciones de FTP sin actividad durante más de 30 días están desactivadas.

## El `.fin` archivo

Una parte vital de la ingesta correcta de un archivo de fuentes de datos es la inclusión de un `.fin` archivo. Este archivo indica al Adobe que el archivo de datos está listo para procesarse. Si carga un archivo de fuente de datos sin el correspondiente `.fin` , el Adobe nunca procesa esos datos.

El `.fin` tiene las siguientes propiedades:

* El archivo tiene un `.fin` extensión. Asegúrese de que el sistema operativo le permite ver y editar tipos de archivos.
* El archivo está vacío. No almacene datos dentro de `.fin` archivo.
* El archivo tiene el mismo nombre que el archivo de fuente de datos. Por ejemplo, si carga un archivo de fuente de datos denominado `example.txt`, el `.fin` archivo **debe** ser nombrado `example.fin`. Si no tienen un nombre idéntico, Adobe nunca procesa el archivo de fuente de datos.

Una vez que el archivo de fuente de datos y `.fin` se cargan en el sitio FTP, el Adobe procesa el archivo. No cargue el `.fin` hasta que el archivo de fuente de datos se haya cargado completamente. Si la variable `.fin` El archivo se ha cargado antes de tiempo, el Adobe recupera e ingiere el archivo cargado parcialmente, lo que provoca posibles errores.

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
