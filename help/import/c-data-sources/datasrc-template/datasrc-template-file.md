---
description: Información sobre la plantilla de fuentes de datos, que ofrece un marco de datos adecuado para el envío de un conjunto específico de datos externos a las fuentes de datos.
subtopic: Data sources
title: Resumen de plantilla de fuentes de datos
topic-fix: Developer and implementation
uuid: e768bcff-a996-44c7-a7f2-9a2c651ecad9
exl-id: d3122582-d392-4bd9-af2a-fb3d1292ba66
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '247'
ht-degree: 100%

---

# Resumen de plantilla de fuentes de datos

Información sobre la plantilla de fuentes de datos, que ofrece un marco de datos adecuado para el envío de un conjunto específico de datos externos a las fuentes de datos.

El archivo de plantilla que genera este asistente está pensado para ayudar al usuario a comenzar la importación. No es obligatorio usar nada más las columnas definidas en la plantilla, sino que se pueden agregar otras columnas que se necesiten, siempre que la métrica o la definición sea compatible con el tipo de procesamiento de datos seleccionado.

Para saber cuáles son las métricas y dimensiones compatibles con cada tipo, consulte las siguientes secciones:

* [Registro web](/help/import/c-data-sources/c-datasrc-types/datasrc-web-log.md)
* [Tráfico](/help/import/c-data-sources/c-datasrc-types/datasrc-traffic.md) (obsoleto)
* [Conversión](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md)
* [ID de transacción](/help/import/c-data-sources/c-datasrc-types/datasrc-transactionid.md)
* [ID de visitante](/help/import/c-data-sources/c-datasrc-types/datasrc-visitorid.md)
* [Procesamiento completo](/help/import/c-data-sources/c-datasrc-types/datasrc-full-processing.md)

Por ejemplo, para un tipo de datos de ID de visitante, se puede añadir una columna para cualquiera de las métricas o dimensiones que se enumeran en [ID de visitante](/help/import/c-data-sources/c-datasrc-types/datasrc-visitorid.md).

Una vez creada la plantilla, puede descargarla, escribir los datos en ella y cargar el archivo al sitio FTP del sistema de fuentes de datos. En cuanto el servidor de fuentes de datos procese los datos importados, estos ya se podrán usar en informes de marketing.

La plantilla de la fuente de datos es un archivo [!DNL .txt] que se puede abrir con cualquier editor de texto. Sin embargo, es más fácil trabajar con la plantilla en Microsoft Excel u otra aplicación de hoja de cálculo. El contenido de la plantilla depende de las opciones que se elijan en el [!UICONTROL asistente para la activación de fuentes de datos].

Consulte [Referencia sobre el archivo de importación](/help/import/c-data-sources/datasrc-template/datasrc-import-file-reference.md) para obtener más detalles.
