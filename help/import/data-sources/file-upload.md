---
title: Cargar el archivo de fuentes de datos a Adobe
description: Proceso para cargar un archivo de fuente de datos en Adobe Analytics para su ingesta.
source-git-commit: bb3036380eeec9b7a868f60a4c9076f2b772532b
workflow-type: tm+mt
source-wordcount: '366'
ht-degree: 1%

---

# Cargar el archivo de fuentes de datos a Adobe

El envío de un archivo de fuentes de datos a Adobe implica un flujo de trabajo FTP típico autenticado. Puede usar el Explorador de Windows, el Buscador o un cliente FTP dedicado para cargar los archivos deseados en la ubicación FTP del Adobe.

Localice las credenciales de FTP en la [Administrador de fuentes de datos](manage.md). Cada fuente de datos tiene un vínculo a su **[!UICONTROL Información de FTP]**. Cada ubicación FTP está dedicada a esa fuente de datos específica; no puede usar la misma ubicación FTP para varias fuentes de datos.

Por motivos de seguridad, se deshabilitan las ubicaciones de FTP sin actividad durante más de 30 días.

## La variable `.fin` file

Una parte vital de la ingesta exitosa de un archivo de fuente de datos es la inclusión de un `.fin` archivo. Este archivo indica a los Adobes que el archivo de datos está listo para su procesamiento. Si carga un archivo de fuente de datos sin la correspondiente `.fin` Adobe nunca procesa esos datos.

La variable `.fin` tiene las siguientes propiedades:

* El archivo tiene un `.fin` extensión. Asegúrese de que el sistema operativo le permita ver y editar tipos de archivos.
* El archivo está vacío. No almacene datos dentro de la variable `.fin` archivo.
* El archivo tiene el mismo nombre que el archivo de fuente de datos. Por ejemplo, si carga un archivo de fuente de datos denominado `example.txt`, el `.fin` file **must** se llamará `example.fin`. Si no tienen un nombre idéntico, Adobe nunca procesa el archivo de fuente de datos.

Una vez que el archivo de origen de datos y `.fin` se cargan en el sitio FTP, Adobe procesa el archivo. No cargue el `.fin` hasta que el archivo de fuente de datos se cargue completamente. Si la variable `.fin` se carga antes de tiempo, Adobe recupera e incorpora el archivo parcialmente cargado, lo que provoca posibles errores.

## Orden de procesamiento

Si carga varios archivos al mismo tiempo en el sitio FTP, el Adobe los incorpora en orden alfanumérico. Si su organización requiere que los archivos se introduzcan en un orden específico, asegúrese de que los nombres de sus archivos tengan nombres alfanuméricos.

## Tiempo de procesamiento

Para garantizar el procesamiento más rápido de los archivos, Adobe recomienda agregar datos de métricas en una sola fila por fecha. Por ejemplo, este archivo de fuentes de datos, aunque válido, se procesaría más lentamente:

| `date` | `eVar1` | `event1` | `event2` | `event3` |
| --- | --- | --- | --- | --- |
| `07/24/YYYY` | `red` | `1` |  |  |
| `07/24/YYYY` | `red` | `1` |  |  |
| `07/24/YYYY` | `red` |  | `1` |  |
| `07/24/YYYY` | `red` |  |  | `1` |

Este archivo se procesaría más rápido, lo que contiene los mismos datos:

| `date` | `eVar1` | `event1` | `event2` | `event3` |
| --- | --- | --- | --- | --- |
| `07/24/YYYY` | `red` | `2` | `1` | `1` |
