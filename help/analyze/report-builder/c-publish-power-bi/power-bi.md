---
description: 'null'
seo-description: 'null'
seo-title: Publicar en Power BI - Información general
title: Publicar en Power BI - Información general
uuid: ad 688817-6 e 3 c -45 da -983 d -48 c 123465309
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Publicar en Power BI - Información general

Microsoft Power BI es un conjunto de tableros de análisis empresarial para analizar datos y compartir resultados. La integración de Adobe Analytics con Power BI le permite visualizar datos de Analytics del Creador de informes dentro de Microsoft Power BI y compartirlos fácilmente dentro de su organización.

Anteriormente, el analista programaba el envío de libros del Creador de informes mediante correo electrónico (o ftp). Ahora, las personas que usted determine pueden emplear sus cuentas de Power BI para obtener acceso a datos precisos y actualizados de su empresa mediante un entorno basado en web, disponible desde distintas plataformas y dispositivos.

Al combinar las capacidades de generación del Creador de informes con las características de visualización de Power BI, la información se hace más accesible para todos los miembros de la organización. Power BI también le permite integrar Adobe Analytics con otras fuentes de datos (p. ej., puntos de venta, CRM) para descubrir datos, asociaciones y oportunidades únicas relativas a los clientes.

![](assets/aaplusbi.png)

La integración con el Creador de informes de Adobe le permite

* [Publicar en Power BI libros programados del Creador de informes](../../../analyze/report-builder/whats-new-arb.md#section_21CA66229EC240D49594A9A7D3FBA687)
* [Publicar todas las tablas con formato de un libro como tablas de conjuntos de datos de Power BI](../../../analyze/report-builder/whats-new-arb.md#section_7C54A54E75184DD6BAEF4ACCE241239A)
* [Publicar todas las solicitudes del Creador de informes como tablas de conjuntos de datos de Power BI](../../../analyze/report-builder/whats-new-arb.md#section_0C26057C7DBB4068A643FDD688F6E463)

## Requisitos del sistema {#section_0B71092D853446F38FA36447DAC0D32B}

* Adobe Report Builder 5.5 [installed](../../../analyze/report-builder/setup/t-install-arb.md#task_0CA66703882F469EB6DBD9298975D6C3)
* Cuenta Microsoft activa que le permita iniciar sesión en Power BI

## Publish workbook to Power BI {#section_21CA66229EC240D49594A9A7D3FBA687}

Los libros programados son hojas de cálculo de Excel con formato, rellenas con datos de Adobe Analytics y enviadas de forma regular y programada.

**Publicar libro en el Creador de informes**

1. En el Creador de informes, genere y guarde un libro.
1. On the Report Builder Toolbar, click **[!UICONTROL Schedule]** &gt; **[!UICONTROL New]**.

1. En el Asistente de programación básico, marque la casilla junto a **[!UICONTROL Publicar libro en Microsoft Power BI]**.

   ![](assets/simple-schedule-wizard.png)

1. Especifique su correo electrónico y envíe inmediatamente, o especifique la frecuencia de la programación (cada día, cada hora, etc.).
1. Haga clic en **[!UICONTROL Aceptar]para publicar.**
1. A continuación, se le pedirá que inicie sesión en su cuenta Microsoft. Proporcione la credenciales.
1. El libro del Creador de informes queda programado y se publica en Power BI.

   Con cada instancia programada, y después de que el proceso de programación del Creador de informes actualice el libro con datos actualizados de Analytics, el libro se vuelve a publicar en Microsoft Power BI.

**Ver los datos del libro del Creador de informes en Power BI**

1. En Power BI, haga doble clic en el libro dentro del menú [!UICONTROL Libros].

   ![](assets/workbooks-power-bi.png)

1. Ahora puede ver los datos del tablero del libro.  ![](assets/view-data-pbi.png)

1. También puede anclar un área de este libro para incluirla en cualquiera de sus tableros de Power BI.

## Publish all formatted tables in the workbook as Power BI dataset tables {#section_7C54A54E75184DD6BAEF4ACCE241239A}

>[!NOTE]
>
>Si el libro contiene una macro, se desactivará la «Publicar todas las tablas con formato del libro como tablas de conjuntos de datos de Power BI».

En vez de importar todo el libro, puede importar solo el contenido de todas las tablas con formato dentro del libro.

**Caso de uso**: tiene un libro de Excel que extrae datos de varias solicitudes del Creador de informes y crea una tabla resumen con numerosas fórmulas. Puede importar únicamente la tabla resumen en Power BI y crear una visualización para ella.

**Publicación de una tabla formateada en el Creador de informes**

1. En el Creador de informes, genere una tabla de datos que incluya una fila de encabezado, seguida por una fila de datos.
1. Seleccione la tabla y, a continuación, elija **[!UICONTROL Dar formato como tabla]** en el menú [!UICONTROL Inicio]. La tabla recibe un nombre predeterminado (Table 1, Table 2, etc.), pero puede cambiarlo desde el menú [!UICONTROL Diseño].

1. On the Report Builder Toolbar, click **[!UICONTROL Schedule]** &gt; **[!UICONTROL New]**.

1. En el Asistente de programación básico, haga clic en **[!UICONTROL Opciones de programación avanzadas]**.
1. In the [!UICONTROL Scheduling Wizard - Advanced], on the **[!UICONTROL Publishing Options]**tab, check the box next to **[!UICONTROL Publish all Formatted Tables as Power BI dataset tables]**.

   ![](assets/advanced-schedule-wizard2.png)

1. (Opcional) Puede personalizar el nombre del activo publicado en Power BI. Puede ser útil si utiliza el control de versiones como parte del nombre del libro (p. ej., milibro_v1.1.xlsx) y no quiere que el número de versión aparezca en el nombre del activo publicado en Power BI. Tiene la ventaja añadida de que el activo publicado no cambiará si el número de versión varía. (Vea aquí las [especificaciones](../../../analyze/report-builder/c-publish-power-bi/specifications-limits.md#concept_1B6522B4D7A9482680198F125D94EEFD)).

**Ver los datos de tabla en Power BI**

1. In Power BI, go to the **[!UICONTROL Workspaces]** &gt; **[!UICONTROL Datasets]** menu.

   ![](assets/datasets-menu.png)

1. Seleccione el conjunto de datos que ha publicado y haga clic en el icono [!UICONTROL Crear informe] que hay junto a él. Fíjese en que las tablas aparecen como campos.

   ![](assets/formatted-tables.png)

1. Seleccione una tabla y sus columnas asociadas.

   ![](assets/view-table-dataset.png)

1. En el menú [!UICONTROL Visualizaciones] puede seleccionar cómo se muestra una tabla en Power BI. Por ejemplo, podría presentar los datos como un gráfico de líneas:

   ![](assets/bi-line-graph.png)

1. A partir de aquí, puede crear visualizaciones a partir de esta tabla de conjunto de datos.

## Publish all Report Builder requests as Power BI Dataset tables {#section_0C26057C7DBB4068A643FDD688F6E463}

Puede convertir todas las solicitudes en tablas de conjuntos de datos y crear visualizaciones sobre ellas.

>[!IMPORTANT]
>
>Si el libro contiene más de 100 solicitudes, solo se publicarán las 100 primeras en Power BI. Además, solo se publicarán las 10 000 primeras filas de datos de cada solicitud publicada en Power BI. Por tanto, aunque estas solicitudes se enviarán correctamente siguiendo la programación, el ámbito de publicación en Power BI es limitado.

1. En el Creador de informes, abra o cree un libro que contenga solicitudes del Creador de informes.
1. On the Report Builder Toolbar, click **[!UICONTROL Schedule]** &gt; **[!UICONTROL New]**.

1. En el Asistente de programación básico, haga clic en **[!UICONTROL Opciones de programación avanzadas]**.
1. In the [!UICONTROL Scheduling Wizard - Advanced], on the **[!UICONTROL Publishing Options]**tab, check the box next to **[!UICONTROL Publish all Report Builder Requests as Power BI Dataset Tables]** ![](assets/advanced-schedule-wizard2.png)

1. Haga clic en **[!UICONTROL Aceptar]**.

**Ver los datos de solicitud en Power BI**

Cada solicitud programada del Creador de informes se publica como una tabla en el conjunto de datos. Cada tabla de solicitud recibe el nombre de la dimensión principal de la solicitud e incluye una columna [!UICONTROL Grupo de informes] y otra [!UICONTROL Segmentos].

1. In Power BI, go to the **[!UICONTROL Workspaces]** &gt; **[!UICONTROL Datasets]** menu.

1. Seleccione la solicitud que ha publicado y haga clic en el icono [!UICONTROL Crear informe] que hay junto a ella.

   Fíjese en que las solicitudes aparecen como tablas en el menú [!UICONTROL Campos].

   ![](assets/published-requests.png)

   >[!NOTE]
   >
   >Independientemente de cómo configuró la solicitud del Creador de informes para su presentación en la hoja de cálculo (diseño de tabla dinámica, diseño personalizado, algunas columnas invisible), el Creador de informes siempre publicará su solicitud con el mismo formato bidimensional de fila de encabezado: Fecha, Dimensiones, Métricas, Grupos de informes, Segmentos.

1. Fíjese también en que hay una tabla adicional llamada **[!UICONTROL Leyenda]**. Si saca una solicitud del contexto del Creador de informes, puede ser difícil recordar qué significa. El propósito de la tabla Leyenda es, por ejemplo, mostrarle el nombre de cada solicitud bajo el ID de tabla. También puede añadir otras columnas Leyenda para obtener una visualización completa de la solicitud.

   ![](assets/legend-table.png)

