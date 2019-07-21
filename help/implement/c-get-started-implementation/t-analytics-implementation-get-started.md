---
description: Obtenga información sobre la experiencia de los usuarios que compran sus productos por primera vez a la hora de poner en marcha la implementación de Adobe Analytics.
keywords: Introducción
seo-description: Obtenga información sobre la experiencia de los usuarios que compran sus productos por primera vez a la hora de poner en marcha la implementación de Adobe Analytics.
seo-title: Modal simplificado de implementación
solution: Analytics
subtopic: Analysis Workspace
title: Modal simplificado de implementación
topic: Reports and Analytics
uuid: 6 fad 2 c 1 f -476 c -4985-90 df -7 c 222 e 751 ddc
translation-type: tm+mt
source-git-commit: 4e7a8bab956503093633deff0a64e8c7af2d5497

---


# Modal simplificado de implementación

Obtenga información sobre la experiencia de los usuarios que compran sus productos por primera vez a la hora de poner en marcha la implementación de Adobe Analytics.

<!-- 

<p>https://activation.adobedtm.com/index.php?redirected=1 </p>

 -->

New users can quickly create your first [!DNL Analytics] report suite (data repository) using this *`Getting Started with Adobe Analytics`* setup modal. Then, you can deploy [!DNL Analytics] code using [!DNL Dynamic Tag Management].

[!DNL Dynamic Tag Management] le permite gestionar su implementación de Adobe Analytics sin necesidad de realizar cambios en el sitio cada vez. Si está implementando una aplicación móvil, podrá obtener el SDK que necesite para empezar a recopilar datos de valor desde sus aplicaciones.

Este procedimiento le permite:

* Crear rápidamente su primer [grupo de informes](https://marketing.adobe.com/resources/help/en_US/analytics/getting-started/report-suites.html).
* Deploy [!DNL Analytics] and the [Identity Service](https://marketing.adobe.com/resources/help/en_US/mcvid/).

* Ejecutar informes sobre datos básicos en el nivel de página.

>[!NOTE]
>
>Before you begin, verify that Analytics is [enabled in the Adobe Experience Cloud](https://marketing.adobe.com/resources/help/en_US/mcloud/core_services.html) (the solution provisioning process). Si ha recibido un mensaje de correo electrónico en el que se le invita a iniciar sesión en Analytics en el tablero de empresa, habrá cumplido con este requisito previo.

**Para ejecutar el modo de implementación simplificada**

1. Log in to the [!DNL Adobe Experience Cloud] ( [experiencecloud.adobe.com](https://experiencecloud.adobe.com)).

   Una vez acceda a [!DNL Analytics], el sistema determinará si dispone de un grupo de informes. Si no, aparecerá la página [!UICONTROL Introducción a Adobe Analytics].

   ![](assets/analytics-implementation-rs-wizard.png)

   Alternatively, you can run this setup in [!DNL Analytics] by clicking **[!UICONTROL Help]** &gt; **[!UICONTROL Welcome to Adobe Analytics]**.

1. Especifique la siguiente información básica sobre su empresa:

   <table id="table_1741878A1B284CB78D297D531DC703D6"> 
     <thead> 
      <tr> 
       <th colname="col1" class="entry"> Elemento </th> 
       <th colname="col2" class="entry"> Descripción </th> 
      </tr> 
     </thead>
     <tbody> 
      <tr> 
       <td colname="col1"> <p>Tipo de propiedad </p> </td> 
       <td colname="col2"> <p>¿Se trata de una implementación web, móvil, o ambas? </p> </td> 
      </tr> 
      <tr> 
       <td colname="col1"> <p>Sectores </p> </td> 
       <td colname="col2"> <p>Especifique cómo ingresa dinero su empresa (mediante productos, servicios al cliente, detección de posibles clientes, reconocimiento de marcas o anuncios). </p> </td> 
      </tr> 
      <tr> 
       <td colname="col1"> <p>Capa de datos </p> </td> 
       <td colname="col2"> <p>(Recomendado) Una matriz de JavaScript utilizada para almacenar información. Si aplica una configuración automática mediante Dynamic Tag Management, utilizará una capa de datos. </p> <p>For a blog on data layers, see <a href="https://blogs.adobe.com/digitalmarketing/analytics/data-layers-buzzword-best-practice/" format="http" scope="external"> Data Layer: From Buzzword to Best Practice</a>. </p> </td> 
      </tr> 
      <tr> 
       <td colname="col1"> <p>Repositorio de datos (grupo de informes) </p> </td> 
       <td colname="col2"> <p> Un <a href="https://marketing.adobe.com/resources/help/en_US/analytics/getting-started/report-suites.html" format="html" scope="external">grupo de informes</a> es un conjunto de datos discretos que por lo general corresponden a una sola propiedad (sitio o aplicación) o marca. Cada grupo de informes tiene su propio conjunto de informes y métricas. </p> </td> 
      </tr> 
      <tr> 
       <td colname="col1"> <p>Zona horaria </p> </td> 
       <td colname="col2"> <p>Su zona horaria local. (Se detecta automáticamente). </p> </td> 
      </tr> 
      <tr> 
       <td colname="col1"> <p>Vistas de la página estimadas </p> </td> 
       <td colname="col2"> <p>El número de visualizaciones de página aproximado que registra el sitio al día. </p> </td> 
      </tr> 
      <tr> 
       <td colname="col1"> <p>Moneda base </p> </td> 
       <td colname="col2"> <p>La moneda en la que realiza sus transacciones comerciales. </p> </td> 
      </tr> 
     </tbody> 
    </table>

1. Click **[!UICONTROL Next]**.

   El sistema crea un grupo de informes.

1. To begin deployment, click **[!UICONTROL Next]**, then click one of the following options:

   <table id="table_71C7F7B9677346CD8D5130519D32464B"> 
     <thead> 
      <tr> 
       <th colname="col1" class="entry"> Elemento </th> 
       <th colname="col2" class="entry"> Descripción </th> 
      </tr> 
     </thead>
     <tbody> 
      <tr> 
       <td colname="col1"> <p>Implementar </p> </td> 
       <td colname="col2"> <p> Ejecuta <span class="keyword">Dynamic Tag Management</span>, donde podrá iniciar sesión e implementar Analytics. This process automatically implements the <span class="filepath"> AppMeasurement.js</span> file and the Identity Service (<span class="filepath"> VisitorAPI.js</span>). </p> <p> <p>Importante: Se muestra en una nueva pestaña del explorador una página de ayuda que explica la implementación de <span class="keyword">Adobe Analytics</span> mediante Dynamic Tag Management. </p> </p> </td> 
      </tr> 
      <tr> 
       <td colname="col1"> <p>Descargar </p> </td> 
       <td colname="col2"> <p> Descarga el archivo de instalación, llamado <span class="filepath">INSTALL-ME &lt;nombre del grupo de informes&gt;.js</span>. Esta opción es adecuada para usuarios con experiencia que comprenden el proceso de <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/js_implementation.html" format="html" scope="external">implementación de JavaScript</a>. </p> <p> <p>Importante: La descarga del código no conlleva la implementación de <span class="keyword">Analytics</span>. Se trata de una implementación manual en las páginas del sitio, o bien, a través los servicios de consultoría de Adobe. </p> </p> </td> 
      </tr> 
     </tbody> 
    </table>

1. Ejecutar un informe.

   Tras implementar la herramienta Analytics, podrá ejecutar un informe en Reports &amp; Analytics para confirmar la llegada de datos a su sitio (consulte [Iniciar sesión y navegar](https://marketing.adobe.com/resources/help/en_US/analytics/getting-started/analytics-navigation.html) para familiarizarse con la interfaz de Analytics).

   For example, a **[!UICONTROL Site Metrics]** &gt; **[!UICONTROL Real-Time]** lets you see immediate data.

   >[!NOTE]
   >
   >The [!UICONTROL Real-Time] report requires some configuration prior to running. Consulte [Configuración de informes en tiempo real](https://marketing.adobe.com/resources/help/en_US/reference/t_realtime_admin.html).

**Ejemplo de informe en tiempo real**

![](assets/real-time-report.png)
