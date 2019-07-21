---
description: Información sobre la plantilla de fuentes de datos, que ofrece un marco de datos adecuado para el envío de un conjunto específico de datos externos a las fuentes de datos.
seo-description: Información sobre la plantilla de fuentes de datos, que ofrece un marco de datos adecuado para el envío de un conjunto específico de datos externos a las fuentes de datos.
seo-title: Descripción general de la plantilla de fuentes de datos
solution: Analytics
subtopic: Fuentes de datos
title: Descripción general de la plantilla de fuentes de datos
topic: Desarrollador e implementación
uuid: e 768 bcff-a 996-44 c 7-a 7 f 2-9 a 2 c 651 ecad 9
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Descripción general de la plantilla de fuentes de datos

Información sobre la plantilla de fuentes de datos, que ofrece un marco de datos adecuado para el envío de un conjunto específico de datos externos a las fuentes de datos.

El archivo de plantilla que genera este asistente está pensado para ayudar al usuario a comenzar la importación. No es obligatorio usar nada más las columnas definidas en la plantilla, sino que se pueden agregar otras columnas que se necesiten, siempre que la métrica o la definición sea compatible con el tipo de procesamiento de datos seleccionado.

Para saber cuáles son las métricas y dimensiones compatibles con cada tipo, consulte las siguientes secciones:

* [Registro web](../../../import/c-data-sources/c-datasrc-types/datasrc-web-log.md#concept_E25D89C8B90A41FEB7DF4E936CACEE2B)
* [Tráfico](../../../import/c-data-sources/c-datasrc-types/datasrc-traffic.md#concept_F50D3AC6A5544D06BB81EF1E279576BC) (obsoleto)
* [Conversión](../../../import/c-data-sources/c-datasrc-types/datasrc-conversion.md#concept_FA3B6557128649C0B662E95C6B617FA0)
* [ID de transacción](../../../import/c-data-sources/c-datasrc-types/datasrc-transactionid.md#concept_A97302E9EC45468A8F30285FACE8C776)
* [Visitor ID](../../../import/c-data-sources/c-datasrc-types/datasrc-visitorid.md#concept_1CFAA61D57A84B22A41F7A8E0DFCAAB5)
* [Procesamiento completo](../../../import/c-data-sources/c-datasrc-types/datasrc-full-processing.md#concept_975B1BB9981D49139B4EE09C78CDE6ED)

For example, for a Visitor ID data type, you can add a column for any metric or dimensions listed in [Visitor ID](../../../import/c-data-sources/c-datasrc-types/datasrc-visitorid.md#concept_1CFAA61D57A84B22A41F7A8E0DFCAAB5).

Una vez creada la plantilla, puede descargarla, escribir los datos en ella y cargar el archivo al sitio FTP del sistema de fuentes de datos. En cuanto el servidor de fuentes de datos procese los datos importados, estos ya se podrán usar en informes de marketing.

The Data Source template is a [!DNL .txt] file that you can open with any text editor. Sin embargo, es más fácil trabajar con la plantilla en Microsoft Excel u otra aplicación de hoja de cálculo. El contenido de la plantilla depende de las opciones que se elijan en el [!UICONTROL Asistente para la activación de fuentes de datos].

Consulte [Referencia sobre el archivo de importación](../../../import/c-data-sources/datasrc-template/datasrc-import-file-reference.md#concept_472095E1D011434D98A21C101A4618BD) para obtener más detalles.
