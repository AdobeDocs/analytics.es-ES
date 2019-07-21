---
description: Información sobre los métodos de Adobe para proporcionar acceso a fuentes de datos.
seo-description: Información sobre los métodos de Adobe para proporcionar acceso a fuentes de datos.
seo-title: Cómo funcionan las fuentes de datos
solution: Analytics
subtopic: Fuentes de datos
title: Cómo funcionan las fuentes de datos
topic: Desarrollador e implementación
uuid: ee 9 e 6 e 74-9 b 00-4733-9 a 4 b-d 9 f 2 b 954 cc 7 c
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Cómo funcionan las fuentes de datos

Información sobre los métodos de Adobe para proporcionar acceso a fuentes de datos.

>[!NOTE]
>
>Una vez enviados mediante las fuentes de datos, los datos importados no se distinguen de los datos recopilados con otros métodos (señalización JavaScript, actionsource, API de inserción de datos, etc.). Los datos no se pueden eliminar después de importarlos.

![](assets/data_sources_overview.png)

Hay dos métodos disponibles para enviar datos:

* [FTP](../../import/c-data-sources/datasrc-how-data-sources-works.md#section_0E70022648F94061AF5B4AD6C7145243)
* [API](../../import/c-data-sources/datasrc-how-data-sources-works.md#section_65DACC9CE00C437BBFDD02D19C25A4BD)

## FTP {#section_0E70022648F94061AF5B4AD6C7145243}

Los informes de marketing permiten crear y administrar fuentes de datos para cargar mediante FTP; en este caso, para importar los archivos de datos en el sistema de fuentes de datos se utiliza el protocolo de transferencia de archivos FTP. Después de crear las fuentes de datos, Adobe le indicará una dirección FTP que puede usar para cargar los archivos creados. Después de la carga de los archivos, el sistema de fuentes de datos los encontrará y procesará automáticamente. Una vez procesados, los datos estarán disponibles para los informes de marketing.

## API {#section_65DACC9CE00C437BBFDD02D19C25A4BD}

Adobe ofrece una API específica que permite vincular mediante programación cualquier aplicación con el sistema de fuentes de datos. Esto elimina la necesidad de usar un servidor FTP intermedio, y las transferencias de datos pasan a realizarse por HTTP, SOAP y REST.

Consulte la [documentación de API de fuentes de datos](https://marketing.adobe.com/developer/documentation/data-sources/c-data-sources-api).
