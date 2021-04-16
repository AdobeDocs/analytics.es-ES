---
description: El archivo de plantilla de importaciones está diseñado para proporcionarle los conceptos básicos de importación.
subtopic: Data sources
title: Generación de plantillas de archivo de importación
topic-fix: Developer and implementation
uuid: bcd90e34-42e6-4cd1-b67e-87586dea25d8
exl-id: c2717936-a011-4224-8a9e-94753abbcb33
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '596'
ht-degree: 100%

---

# Generación de plantillas de archivo de importación

El archivo de plantilla de importaciones está diseñado para proporcionarle los conceptos básicos de importación.

No es obligatorio usar nada más las columnas definidas en la plantilla, sino que se pueden agregar otras columnas que se necesiten, siempre que la métrica o la definición sea compatible con el tipo de procesamiento de datos seleccionado. Para saber cuáles son las métricas y dimensiones compatibles con cada tipo, consulte las siguientes secciones: [Registro web](/help/import/c-data-sources/c-datasrc-types/datasrc-web-log.md), [Tráfico](/help/import/c-data-sources/c-datasrc-types/datasrc-traffic.md), [Conversión](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md), [ID de transacción](/help/import/c-data-sources/c-datasrc-types/datasrc-transactionid.md), [ID de visitante](/help/import/c-data-sources/c-datasrc-types/datasrc-visitorid.md), [Procesamiento completo](/help/import/c-data-sources/c-datasrc-types/datasrc-full-processing.md)). Por ejemplo, para un tipo de datos de tráfico, se puede agregar una columna para cualquiera de las métricas o dimensiones que se enumeran en [Tráfico](/help/import/c-data-sources/c-datasrc-types/datasrc-traffic.md).

Una vez creada la plantilla, puede descargarla, escribir los datos en ella y cargar el archivo al sitio FTP del sistema de fuentes de datos. En cuanto el servidor de fuentes de datos procese los datos importados, estos ya se podrán usar en informes de Analytics.

La plantilla de la fuente de datos es un archivo .txt que se puede abrir con cualquier editor de texto. Sin embargo, es más fácil trabajar con la plantilla en Microsoft Excel u otra aplicación de hoja de cálculo. El contenido de la plantilla depende de las opciones que se elijan en el asistente para la activación de fuentes de datos.

Consulte [Referencia sobre el archivo de importación](/help/import/c-data-sources/datasrc-template/datasrc-import-file-reference.md) para obtener más detalles.

1. Iniciar sesión en Analytics.
1. En la Suite, haga clic en **[!UICONTROL Administración]** > **[!UICONTROL Fuentes de datos]**.
1. En la pestaña **[!UICONTROL Crear de Fuentes de datos]**, elija una categoría de plantilla y un tipo.
1. Revise las instrucciones o la información de activación y haga clic en **[!UICONTROL Activar]**.

   Resultado (1). Seleccione las opciones de generación de la plantilla de datos en el asistente para la activación de fuentes de datos.

   | Página del asistente | Campo | Descripción |
   |--- |--- |--- |
   | 1 | Nombre | El nombre de plantilla que Analytics muestra en el Administrador de fuentes de datos. |
   | 1 | Correo electrónico | El correo electrónico al que se envían todas las notificaciones relacionadas con el uso de esta plantilla de fuente de datos. |
   | 1 | Casilla de verificación Tarifas asociadas | Marque la casilla de verificación para indicar que está de acuerdo con las tarifas asociadas con el uso de esta plantilla de fuente de datos. |
   | 2 | Elegir métricas | Seleccione las métricas que desea importar con esta fuente de datos. Analytics recomienda ciertas métricas según la categoría de fuente de datos y el tipo seleccionados en el paso 3.  Para indicar otra métrica, escriba su nombre en un campo vacío y marque la casilla de verificación para habilitar la métrica. |
   | 3 | Asignar métricas | Seleccione el evento de Analytics que recibirá cada métrica seleccionada en la página 2 del asistente.  Debe usar eventos nuevos todavía no asignados a los que antes les haya asignado nombres que se correspondan con los datos de métricas importadas que recibirán a través de la fuente de datos.  Si se usa como variable de destino una eVar o una variable de producto o de código de seguimiento, y los valores cargados coinciden con valores capturados ya existentes, los eventos cargados básicamente agregarán las métricas a los valores preexistentes. Por ejemplo, se podría crear una métrica “Pedidos sin conexión” con una dimensión de datos de producto que ya tiene Vistas de productos, Cierres de compra y Pedidos como métricas preexistentes. |
   | 4 | Elegir las dimensiones de los datos | Seleccione las dimensiones de datos para el desglose de las métricas importadas mediante esta fuente de datos. Analytics recomienda ciertas dimensiones de datos según la categoría de fuente de datos y el tipo seleccionados en el paso 3.  Para indicar otra dimensión de datos, escriba su nombre en un campo vacío y marque la casilla de verificación para habilitar la dimensión. |
   | 5 | Asignar las dimensiones de los datos | Seleccione el informe estándar o la eVar que recibirá cada dimensión de datos seleccionada en la página 4 del asistente. |

1. Cuando se haya creado la plantilla, copie los datos en las columnas que correspondan, teniendo presente respetar el formato de datos necesario para cada columna de datos.

   Resultado (1). Guarde el archivo de fuente de datos, según la convención de asignación de nombres que haya elegido. Adobe recomienda usar una convención de asignación de nombres uniforme para todos los archivos de fuente de datos. Utilice una extensión común, como .txt o .tsv (o no use ninguna extensión).
