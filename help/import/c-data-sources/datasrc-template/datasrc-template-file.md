---
description: Información sobre la plantilla de fuentes de datos, que ofrece un marco de datos adecuado para el envío de un conjunto específico de datos externos a las fuentes de datos.
subtopic: Data sources
title: Resumen de plantilla de fuentes de datos
topic: Developer and implementation
uuid: e768bcff-a996-44c7-a7f2-9a2c651ecad9
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Resumen de plantilla de fuentes de datos

Información sobre la plantilla de fuentes de datos, que ofrece un marco de datos adecuado para el envío de un conjunto específico de datos externos a las fuentes de datos.

El archivo de plantilla que genera este asistente está pensado para ayudar al usuario a comenzar la importación. No es obligatorio usar nada más las columnas definidas en la plantilla, sino que se pueden agregar otras columnas que se necesiten, siempre que la métrica o la definición sea compatible con el tipo de procesamiento de datos seleccionado.

Para saber cuáles son las métricas y dimensiones compatibles con cada tipo, consulte las siguientes secciones:

* [Registro web](/help/import/c-data-sources/c-datasrc-types/datasrc-web-log.md)
* [Tráfico](/help/import/c-data-sources/c-datasrc-types/datasrc-traffic.md) (obsoleto)
* [Conversión](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md)
* [ID de transacción](/help/import/c-data-sources/c-datasrc-types/datasrc-transactionid.md)
* [Visitor ID](/help/import/c-data-sources/c-datasrc-types/datasrc-visitorid.md)
* [Procesamiento completo](/help/import/c-data-sources/c-datasrc-types/datasrc-full-processing.md)

For example, for a Visitor ID data type, you can add a column for any metric or dimensions listed in [Visitor ID](/help/import/c-data-sources/c-datasrc-types/datasrc-visitorid.md).

Una vez creada la plantilla, puede descargarla, escribir los datos en ella y cargar el archivo al sitio FTP del sistema de fuentes de datos. En cuanto el servidor de fuentes de datos procese los datos importados, estos ya se podrán usar en informes de marketing.

The Data Source template is a [!DNL .txt] file that you can open with any text editor. Sin embargo, es más fácil trabajar con la plantilla en Microsoft Excel u otra aplicación de hoja de cálculo. El contenido de la plantilla depende de las opciones que se elijan en el [!UICONTROL Asistente para la activación de fuentes de datos].

Consulte [Referencia sobre el archivo de importación](/help/import/c-data-sources/datasrc-template/datasrc-import-file-reference.md) para obtener más detalles.
