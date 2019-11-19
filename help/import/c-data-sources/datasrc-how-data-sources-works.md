---
description: Información sobre los métodos de Adobe para proporcionar acceso a fuentes de datos.
solution: Analytics
subtopic: Data sources
title: Funcionamiento de las fuentes de datos
topic: Developer and implementation
uuid: ee9e6e74-9b00-4733-9a4b-d9f2b954cc7c
translation-type: tm+mt
source-git-commit: cf910f98a1921b7558a6614a9d0d69f8e4f855b4

---


# Funcionamiento de las fuentes de datos

Información sobre los métodos de Adobe para proporcionar acceso a fuentes de datos.

> [!NOTE] Una vez enviados a través de las fuentes de datos, los datos importados no se distinguen de los datos de informes recopilados mediante otros métodos (señalización JavaScript, ActionSource, API de inserción de datos, etc.). Los datos no se pueden eliminar después de importarlos.

![](assets/data_sources_overview.png)

Hay dos métodos disponibles para enviar datos:

* [FTP](/help/import/c-data-sources/datasrc-how-data-sources-works.md#section_0E70022648F94061AF5B4AD6C7145243)
* [API](/help/import/c-data-sources/datasrc-how-data-sources-works.md#section_65DACC9CE00C437BBFDD02D19C25A4BD)

## FTP {#section_0E70022648F94061AF5B4AD6C7145243}

Los informes de marketing permiten crear y administrar fuentes de datos para cargar mediante FTP; en este caso, para importar los archivos de datos en el sistema de fuentes de datos se utiliza el protocolo de transferencia de archivos FTP. Después de crear las fuentes de datos, Adobe le indicará una dirección FTP que puede usar para cargar los archivos creados. Después de la carga de los archivos, el sistema de fuentes de datos los encontrará y procesará automáticamente. Una vez procesados, los datos estarán disponibles para los informes de marketing.

## API {#section_65DACC9CE00C437BBFDD02D19C25A4BD}

Adobe ofrece una API específica que permite vincular mediante programación cualquier aplicación con el sistema de fuentes de datos. Esto elimina la necesidad de usar un servidor FTP intermedio, y las transferencias de datos pasan a realizarse por HTTP, SOAP y REST.

Consulte la [documentación de API de fuentes de datos](https://github.com/AdobeDocs/analytics-1.4-apis/tree/master/docs/data-sources-api).
