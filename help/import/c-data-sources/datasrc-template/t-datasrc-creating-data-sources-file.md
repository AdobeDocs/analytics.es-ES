---
description: El archivo de plantilla de importaciones está diseñado para proporcionarle los conceptos básicos de importación.
subtopic: Data sources
title: Generación de plantillas de archivo de importación
topic: Developer and implementation
uuid: bcd90e34-42e6-4cd1-b67e-87586dea25d8
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Generación de plantillas de archivo de importación

El archivo de plantilla de importaciones está diseñado para proporcionarle los conceptos básicos de importación.

No es obligatorio usar nada más las columnas definidas en la plantilla, sino que se pueden agregar otras columnas que se necesiten, siempre que la métrica o la definición sea compatible con el tipo de procesamiento de datos seleccionado. Para saber cuáles son las métricas y dimensiones compatibles con cada tipo, consulte las siguientes secciones: Registro [](/help/import/c-data-sources/c-datasrc-types/datasrc-web-log.md)Web, [Tráfico](/help/import/c-data-sources/c-datasrc-types/datasrc-traffic.md), [Conversión](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md), ID [](/help/import/c-data-sources/c-datasrc-types/datasrc-transactionid.md)de transacción, ID [de](/help/import/c-data-sources/c-datasrc-types/datasrc-visitorid.md)[](/help/import/c-data-sources/c-datasrc-types/datasrc-full-processing.md)visitante, Procesamiento completo). For example, for a traffic data type, you can add a column for any metric or dimensions listed in [Traffic](/help/import/c-data-sources/c-datasrc-types/datasrc-traffic.md).

Una vez creada la plantilla, puede descargarla, escribir los datos en ella y cargar el archivo al sitio FTP del sistema de fuentes de datos. Una vez procesados por el servidor de fuentes de datos, los datos importados están disponibles para su uso en los informes de Analytics.

La plantilla de la fuente de datos es un archivo .txt que se puede abrir con cualquier editor de texto. Sin embargo, es más fácil trabajar con la plantilla en Microsoft Excel u otra aplicación de hoja de cálculo. El contenido de la plantilla depende según las opciones que se elijan en el Asistente para la activación de fuentes de datos.

Consulte [Referencia sobre el archivo de importación](/help/import/c-data-sources/datasrc-template/datasrc-import-file-reference.md) para obtener más detalles.

1. Iniciar sesión en Analytics.
1. En la Suite, haga clic en **Administración**&gt; **[!UICONTROL Fuentes de datos]**.
1. On the **[!UICONTROL Data Sources Create]** tab, select a template category and type.
1. Revise las instrucciones o la información de activación y haga clic en **[!UICONTROL Activar]**.

   Resultado (1). Seleccione las opciones de generación de la plantilla de datos en el Asistente para la activación de fuentes de datos.

   | Página del Asistente | Campo | Descripción |
   |--- |--- |--- |
   | 1 | Nombre | El nombre de la plantilla que Analytics muestra en el Administrador de fuentes de datos. |
   | 1 | Correo electrónico  | El correo electrónico al que se envían todas las notificaciones relacionadas con el uso de esta plantilla de fuente de datos. |
   | 1 | Casilla de verificación Tarifas asociadas | Seleccione la casilla de verificación para indicar que acepta las tarifas asociadas con el uso de esta plantilla de fuente de datos. |
   | 2 | Elegir métricas | Seleccione las métricas que desea importar con esta fuente de datos. Analytics recomienda determinadas métricas en función de la categoría y el tipo de fuente de datos seleccionados en el paso 3.  Para indicar otra métrica, escriba su nombre en un campo vacío y marque la casilla de verificación para habilitar la métrica. |
   | 3 | Asignar métricas | Seleccione un evento de Analytics para recibir cada métrica importada seleccionada en la página 2 del Asistente.  Debe usar eventos nuevos todavía no asignados a los que antes les haya asignado nombres que se correspondan con los datos de métricas importadas que recibirán a través de la fuente de datos.  Si se usa como variable de destino una eVar o una variable de producto o de código de seguimiento, y los valores cargados coinciden con valores capturados ya existentes, los eventos cargados básicamente agregarán las métricas a los valores preexistentes. Por ejemplo, puede crear una métrica "Pedidos sin conexión" con una dimensión de datos Productos que ya tenga Vistas del producto, Cierres de compras y Pedidos como métricas existentes. |
   | 4 | Elegir las dimensiones de los datos | Seleccione las dimensiones de datos para el desglose de las métricas importadas mediante esta fuente de datos. Analytics recomienda determinadas dimensiones de datos en función del tipo de fuente de datos seleccionado en el paso 3.  Para indicar otra dimensión de datos, escriba su nombre en un campo vacío y marque la casilla de verificación para habilitar la dimensión. |
   | 5 | Asignar las dimensiones de los datos | Seleccione el informe estándar o la eVar que recibirá cada dimensión de datos seleccionada en la página 4 del Asistente. |

1. Cuando se haya creado la plantilla, copie los datos en las columnas que correspondan, teniendo presente respetar el formato de datos necesario para cada columna de datos.

   Resultado (1). Guarde el archivo de fuente de datos, según la convención de asignación de nombres que haya elegido. Adobe recomienda usar una convención de asignación de nombres uniforme para todos los archivos de fuente de datos. Utilice una extensión de archivo común como .txt o .tsv (o no utilice ninguna extensión).

