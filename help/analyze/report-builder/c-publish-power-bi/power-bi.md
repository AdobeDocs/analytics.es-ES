---
description: 'null'
title: Resumen de publicación en Power BI
uuid: ad688817-6e3c-45da-983d-48c123465309
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Resumen de publicación en Power BI

Microsoft Power BI es un conjunto de tableros de análisis empresarial para analizar datos y compartir resultados. La integración de Adobe Analytics con Power BI le permite visualizar datos de Analytics de Report Builder dentro de Microsoft Power BI y compartirlos fácilmente dentro de su organización.

Anteriormente, el analista programaba el envío de libros de Report Builder mediante correo electrónico (o ftp). Ahora, las personas que usted determine pueden emplear sus cuentas de Power BI para obtener acceso a datos precisos y actualizados de su empresa mediante un entorno basado en web, disponible desde distintas plataformas y dispositivos.

Al combinar las capacidades de generación de Report Builder con las características de visualización de Power BI, la información se hace más accesible para todos los miembros de la organización. Power BI también le permite integrar Adobe Analytics con otras fuentes de datos (p. ej., puntos de venta, CRM) para descubrir datos, asociaciones y oportunidades únicas relativas a los clientes.

![](assets/aaplusbi.png)

La integración con Report Builder de Adobe le permite

* [Publicar en Power BI libros programados de Report Builder](/help/analyze/report-builder/whats-new-arb.md#rb-5-5-section)
* [Publicar todas las tablas con formato de un libro como tablas de conjuntos de datos de Power BI](/help/analyze/report-builder/whats-new-arb.md#rb-5-5-section)
* [Publicar todas las solicitudes de Report Builder como tablas de conjuntos de datos de Power BI](/help/analyze/report-builder/whats-new-arb.md#rb-5-5-section)

## Requisitos del sistema {#section_0B71092D853446F38FA36447DAC0D32B}

* Adobe Report Builder 5.5 [instalado](/help/analyze/report-builder/setup/t-install-arb.md)
* Cuenta Microsoft activa que le permita iniciar sesión en Power BI

## Publicar libro de trabajo en Power BI {#section_21CA66229EC240D49594A9A7D3FBA687}

Los libros programados son hojas de cálculo de Excel con formato, rellenas con datos de Adobe Analytics y enviadas de forma regular y programada.

**Publicar libro en Report Builder**

1. En Report Builder, genere y guarde un libro.
1. On the Report Builder Toolbar, click **[!UICONTROL Schedule]** > **[!UICONTROL New]**.

1. En el Asistente de programación básico, marque la casilla junto a **[!UICONTROL Publish Workbook to Microsoft Power BI]**.

   ![](assets/simple-schedule-wizard.png)

1. Especifique su correo electrónico y envíe inmediatamente, o especifique la frecuencia de la programación (cada día, cada hora, etc.).
1. Haga clic en **[!UICONTROL OK]** para publicar.
1. A continuación, se le pedirá que inicie sesión en su cuenta Microsoft. Proporcione la credenciales.
1. El libro de Report Builder queda programado y se publica en Power BI.

   Con cada instancia programada, y después de que el proceso de programación de Report Builder actualice el libro con datos actualizados de Analytics, el libro se vuelve a publicar en Microsoft Power BI.

**Ver datos de un libro de Report Builder en Power BI**

1. In Power BI, double click the workbook under the [!UICONTROL Workbooks] menu.

   ![](assets/workbooks-power-bi.png)

1. Ahora puede ver los datos del tablero del libro.  ![](assets/view-data-pbi.png)

1. También puede anclar un área de este libro para incluirla en cualquiera de sus tableros de Power BI.

## Publicar todas las tablas con formato de un libro como tablas de conjuntos de datos de Power BI {#section_7C54A54E75184DD6BAEF4ACCE241239A}

>[!NOTE] Si el libro contiene una macro, la opción “Publicar todas las tablas con formato de un libro como tablas de conjuntos de datos de Power BI” queda deshabilitada.

En vez de importar todo el libro, puede importar solo el contenido de todas las tablas con formato dentro del libro.

**Caso de uso**: tiene un libro de Excel que extrae datos de varias solicitudes de Report Builder y crea una tabla resumen con numerosas fórmulas. Puede importar únicamente la tabla resumen en Power BI y crear una visualización para ella.

**Publicar una tabla con formato en Report Builder**

1. En Report Builder, genere una tabla de datos que incluya una fila de encabezado, seguida por una fila de datos.
1. Seleccione la tabla y seleccione **[!UICONTROL Format as Table]** en el [!UICONTROL Home] menú. The table gets named by default (Table 1, Table 2, etc.), but you can change the name on the [!UICONTROL Design]menu.

1. On the Report Builder Toolbar, click **[!UICONTROL Schedule]** > **[!UICONTROL New]**.

1. En el Asistente de programación básico, haga clic en **[!UICONTROL Advanced Scheduling Options]**.
1. En la [!UICONTROL Scheduling Wizard - Advanced], en la **[!UICONTROL Publishing Options]** ficha, marque la casilla situada junto a **[!UICONTROL Publish all Formatted Tables as Power BI dataset tables]**.

   ![](assets/advanced-schedule-wizard2.png)

1. (Opcional) Puede personalizar el nombre del activo publicado en Power BI. Puede ser útil si utiliza el control de versiones como parte del nombre del libro (p. ej., milibro_v1.1.xlsx) y no quiere que el número de versión aparezca en el nombre del activo publicado en Power BI. Tiene la ventaja añadida de que el activo publicado no cambiará si el número de versión varía. (Vea aquí las [especificaciones](/help/analyze/report-builder/c-publish-power-bi/specifications-limits.md)).

**Ver los datos de tabla en Power BI**

1. In Power BI, go to the **[!UICONTROL Workspaces]** > **[!UICONTROL Datasets]** menu.

   ![](assets/datasets-menu.png)

1. Select the dataset that you published and click the [!UICONTROL Create report] icon next to it. Fíjese en que las tablas aparecen como campos.

   ![](assets/formatted-tables.png)

1. Seleccione una tabla y sus columnas asociadas.

   ![](assets/view-table-dataset.png)

1. From the [!UICONTROL Visualizations] menu, you can select how to visualize a table in Power BI. Por ejemplo, podría presentar los datos como un gráfico de líneas:

   ![](assets/bi-line-graph.png)

1. A partir de aquí, puede crear visualizaciones a partir de esta tabla de conjunto de datos.

## Publicar todas las solicitudes de Report Builder como tablas de conjuntos de datos de Power BI {#section_0C26057C7DBB4068A643FDD688F6E463}

Puede convertir todas las solicitudes en tablas de conjuntos de datos y crear visualizaciones sobre ellas.

>[!IMPORTANT]
>
>Si el libro contiene más de 100 solicitudes, solo las 100 primeras se publicarán en Power BI. Además, solo se publicarán las 10 000 primeras filas de datos de cada solicitud publicada en Power BI. Por tanto, aunque estas solicitudes se enviarán correctamente siguiendo la programación, el ámbito de publicación en Power BI es limitado.

1. En Report Builder, abra o cree un libro que contenga solicitudes de Report Builder.
1. On the Report Builder Toolbar, click **[!UICONTROL Schedule]** > **[!UICONTROL New]**.

1. En el Asistente de programación básico, haga clic en **[!UICONTROL Advanced Scheduling Options]**.
1. En la [!UICONTROL Scheduling Wizard - Advanced], en la **[!UICONTROL Publishing Options]** ficha, marque la casilla situada junto a **[!UICONTROL Publish all Report Builder Requests as Power BI Dataset Tables]**![](assets/advanced-schedule-wizard2.png)

1. Haga clic en **[!UICONTROL OK]**.

**Ver los datos de solicitud en Power BI**

Cada solicitud programada de Report Builder se publica como una tabla en el conjunto de datos. Each request table is named after the primary dimension in the request and it has a [!UICONTROL Report Suite] and a [!UICONTROL Segments] column.

1. In Power BI, go to the **[!UICONTROL Workspaces]** > **[!UICONTROL Datasets]** menu.

1. Select the request that you published and click the [!UICONTROL Create report] icon next to it.

   Notice that the requests appear as tables in the [!UICONTROL Fields] menu.

   ![](assets/published-requests.png)

   >[!NOTE]
   >
   >Independientemente de cómo haya configurado el diseño en el libro de la solicitud de Report Builder (diseño dinámico, personalizado, algunas columnas invisibles), Report Builder siempre la publicará con el mismo formato bidimensional con una fila de encabezado: Fecha, Dimensiones, Métricas, Grupos de informes, Segmentos.

1. Also notice that there is an additional table called **[!UICONTROL Legend]**. Si saca una solicitud del contexto de Report Builder, puede ser difícil recordar qué significa. El propósito de la tabla Leyenda es, por ejemplo, mostrarle el nombre de cada solicitud bajo el ID de tabla. También puede añadir otras columnas Leyenda para obtener una visualización completa de la solicitud.

   ![](assets/legend-table.png)

