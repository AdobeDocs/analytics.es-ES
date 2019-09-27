---
description: Agregue datos sin conexión a los informes de canales de mercadotecnia.
seo-description: Agregue datos sin conexión a los informes de canales de mercadotecnia.
seo-title: Adición de datos de canales sin conexión
solution: Analytics
subtopic: Canales de mercadotecnia
title: Adición de datos de canales sin conexión
topic: Reports and Analytics
uuid: bbf4661a-b6b1-4a89-a3cf-ae8dd785d37d
translation-type: tm+mt
source-git-commit: 0dbc8ac9b416ce50f197a884bb71c6cd389cd0bb

---


# Adición de datos de canales sin conexión

Agregue datos sin conexión a los informes de canales de mercadotecnia.

Los canales en línea permiten clasificar los datos de los visitantes que provienen de fuentes como, por ejemplo, un motor de búsqueda, un anuncio de Internet, un dominio de referencia o una campaña de correo electrónico. Los canales sin conexión se aplican a los visitantes que hayan encontrado el sitio mediante anuncios en televisión, periódicos o revistas.

**Integrar las fuentes de datos en los informes de canal de mercadotecnia**

Si desea integrar [datos de orígenes de datos](https://marketing.adobe.com/resources/help/en_US/sc/datasources/c_faq.html) en informes del canal de mercadotecnia, tenga en cuenta lo siguiente:

* Todas las visitas estándar pasadas a informes de análisis con un [transactionID](https://marketing.adobe.com/resources/help/en_US/sc/datasources/c_Transaction_ID.html) se procesan de modo normal a través de las reglas de procesamiento del canal de mercadotecnia.
* Las fuentes de datos de `transactionID` pasadas a los análisis se asocian automáticamente al mismo canal de mercadotecnia en el que se procesó la visita estándar.
* El resto de datos de orígenes de datos no pasa a través de las reglas de procesamiento del canal de mercadotecnia.

Consulte la ayuda de [Fuentes de datos](https://marketing.adobe.com/resources/help/en_US/sc/datasources/index.html) para obtener más información acerca de las fuentes de datos.

Para clasificar datos de canal sin conexión, active los datos en Fuentes de datos y, a continuación, descargue y edite la plantilla.

Consulte "Uso de fuentes de datos" en la [Guía del usuario de fuentes de datos](https://marketing.adobe.com/resources/help/en_US/sc/datasources/index.html).

**Adición de datos de canales sin conexión**

1. Click **[!UICONTROL Admin]** &gt; **[!UICONTROL Data Sources]**.
1. En la página Fuentes de datos, haga clic en **[!UICONTROL Crear.]**
1. Under **[!UICONTROL 1. Seleccionar categoría]**, seleccione **[!UICONTROL Datos de canal sin conexión]**.
1. Under **[!UICONTROL 2. Seleccionar tipo]**, seleccione **[!UICONTROL Datos de canal sin conexión]**.
1. Click **[!UICONTROL Activate.]**
1. Para correlacionar las métricas sin conexión con las métricas de informes, siga las indicaciones del Asistente para la activación de fuentes de datos.
1. Descargue y edite el archivo de plantilla en un editor como, por ejemplo, Excel.

   Consulte "Creación de un archivo de fuentes de datos" en la [Guía del usuario de fuentes de datos](https://marketing.adobe.com/resources/help/en_US/sc/datasources/index.html).

1. Cargue el archivo tal como se describe en "Carga de un archivo de fuentes de datos" en la [Guía del usuario de fuentes de datos](https://marketing.adobe.com/resources/help/en_US/sc/datasources/index.html).
