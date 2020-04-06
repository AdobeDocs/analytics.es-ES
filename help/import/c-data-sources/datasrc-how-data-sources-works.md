---
description: Información sobre los métodos de Adobe para proporcionar acceso a fuentes de datos.
subtopic: Data sources
title: Funcionamiento de las fuentes de datos
topic: Developer and implementation
uuid: ee9e6e74-9b00-4733-9a4b-d9f2b954cc7c
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Funcionamiento de las fuentes de datos

Información sobre los métodos de Adobe para proporcionar acceso a fuentes de datos.

>[!NOTE] Después de enviar los datos a través de fuentes de datos, no se pueden distinguir de otros datos de informes recopilados por otros métodos (señalizaciones JavaScript, ActionSource, API de inserción de datos, etc.). Una vez importados, no se pueden quitar los datos.

![](assets/data_sources_overview.png)

Hay dos métodos disponibles para enviar datos:

* [FTP](/help/import/c-data-sources/datasrc-how-data-sources-works.md#section_0E70022648F94061AF5B4AD6C7145243)
* [API](/help/import/c-data-sources/datasrc-how-data-sources-works.md#section_65DACC9CE00C437BBFDD02D19C25A4BD)

## FTP {#section_0E70022648F94061AF5B4AD6C7145243}

Puede crear y administrar fuentes de datos basadas en FTP a través de informes de marketing, que utilizan la transferencia de archivos FTP para importar archivos de datos a las fuentes de datos. Después de crear las fuentes de datos, Adobe le indica una dirección FTP que puede usar para cargar los archivos creados. Después de la carga de los archivos, el sistema de fuentes de datos los encontrará y procesará automáticamente. Una vez procesados, los datos están disponibles para los informes de marketing.

## API {#section_65DACC9CE00C437BBFDD02D19C25A4BD}

Adobe oferta una API de fuentes de datos que le permite vincular programáticamente sus aplicaciones a fuentes de datos. Esto elimina la necesidad de un servidor FTP intermediario y transfiere datos a través de HTTP, SOAP y REST.

Consulte la documentación [de la API de fuentes de datos](https://github.com/AdobeDocs/analytics-1.4-apis/tree/master/docs/data-sources-api).
