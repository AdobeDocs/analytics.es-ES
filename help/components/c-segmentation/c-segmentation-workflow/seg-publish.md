---
description: Lets you use the segment for marketing activity in the Audience Library, Target, and Audience Manager.
seo-description: Lets you use the segment for marketing activity in the Audience Library, Target, and Audience Manager.
seo-title: Publicación de segmentos en Experience Cloud
solution: Analytics
title: Publicación de segmentos en Experience Cloud
topic: Segmentos
uuid: e5ce20c0-ce43-423b-a29f-ba66e9e24d27
translation-type: tm+mt
source-git-commit: d65a7582546a96856790dcbe481757ad3f5500a4

---


# Publicación de segmentos en Experience Cloud

>[!IMPORTANT]
>
>The latency improvements regarding segment publishing and the user interface that are described on this page are not rolled out to all customers yet. El entorno de producción actual se describe [aquí](https://docs.adobe.com/content/help/en/core-services/interface/audiences/t-publish-audience-segment.html).

Publishing a segment to the Experience Cloud lets you use the segment for marketing activity in the [!UICONTROL Audience Library], [!DNL Target], [!DNL Audience Manager], and [!DNL Advertising Cloud]. Recent updates have significantly optimized the publishing workflow. Previously, publishing a usable segment took approximately 48 hours.

Now, processing can take up to 8 hours, but depending on other traffic and on the segment size, processing may be even faster. (However, we currently do not have a way to inform you when the segment is available, so you will have to check manually.) We have also increased the maximum number of publishable segments to 75 (from 20). Puede ver los segmentos publicados en Componentes &gt; Segmentos.


## Requisitos previos

* Ensure that the report suite that you are saving this segment to is [enabled for the Experience Cloud](https://docs.adobe.com/content/help/en/core-services/interface/audiences/t-publish-audience-segment.html). De lo contrario, no podrá publicarla en Experience Cloud.
* Asegúrese de que está trabajando en un grupo de informes [asignado a su organización](https://docs.adobe.com/content/help/en/core-services/interface/about-core-services/report-suite-mapping.html)de Experience Cloud.
* Asegúrese de que su organización utiliza Experience Cloud ID.
* Para poder publicar segmentos, el administrador debe asignar el permiso Publicación [!UICONTROL de] segmentos a un perfil de producto en la Consola [de](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/admin-getting-started.html)administración y agregarlo al perfil de producto.


## Consideraciones

* **Límites** del grupo de informes: Puede publicar hasta 75 segmentos por grupo de informes. Este límite se aplica. Si ya ha publicado 75 segmentos, no podrá publicar ningún segmento adicional hasta que cancele la publicación de suficientes segmentos para superar el umbral de 75 segmentos.
* **Membership limits**: Audiences shared to the [!DNL Experience Cloud] from Analytics cannot exceed 20 million unique members.
* **Data Privacy**: Audiences are not filtered based on the authentication state of a visitor. Si un visitante puede navegar por su sitio en los estados de autenticado y no autenticado, las acciones que se dan cuando un visitante no está autenticado todavía pueden hacer que un visitante se incluya en una audiencia. Revise la privacidad [de](https://www.adobe.com/privacy/experience-cloud.html) Adobe Experience Cloud para comprender las implicaciones de privacidad completas del uso compartido de audiencias.
* Para ver una discusión sobre las **diferencias entre segmentos en[!DNL Adobe Analytics]y[!DNL Audience Manager]**, vaya [aquí](https://docs.adobe.com/content/help/en/analytics/integration/audience-analytics/audience-analytics-workflow/aam-analytics-segments.html).

## Escala de tiempo de publicación de segmentos

| ¿Qué está disponible? | Cuando esté disponible | Donde está disponible |
|---|---|---|
| Metadatos (título y definición del segmento) | Inmediatamente después de la publicación | [!DNL Audience Manager], Biblioteca de audiencias [!UICONTROL de Experience Cloud], [!DNL Target] |
| Segmento utilizable con pertenencia | ~ 8 horas después de la publicación | Visor de perfiles de visitante en [!DNL Audience Manager] |
| Características y población de miembros | Dentro de las 24-48 horas | [!DNL Audience Manager] |

## Publicación de segmentos en el Generador [!UICONTROL de segmentos]

1. Vaya a **[!UICONTROL Analytics &gt; Espacio de trabajo &gt; Componentes &gt; Segmentos]&gt; +**
1. Cree un segmento en el Generador [!UICONTROL de segmentos].
1. Proporcione un título y una descripción para el segmento; de lo contrario, no podrá guardarlo.
1. Check **[!UICONTROL Publish this segment to the Experience Cloud (for *report suite*)]**.

![](assets/publish-ec.png)

>[!IMPORTANT]
>
>Asegúrese de utilizar "Visitantes con Experience Cloud ID" al consultar las vistas previas de segmentos en Analytics en lugar de la vista previa de segmentos de "visitantes únicos" totales al comparar los números de Adobe Analytics con los números de Audience Manager:
>
>![](assets/seg-vis-ecid.png)

| Elemento | Descripción |
|---|---|
| **[!UICONTROL Publicar este segmento en Experience Cloud (para *<report suite>*)]** | When this option is enabled, the segment title and definition (i.e. the shell audience as often used in ad platforms) are shared with the Experience Cloud instantaneously, while the segment membership is evaluated and shared every 4 hours. <br> Cuando esa audiencia está asociada con una actividad en [!DNL Target], por ejemplo, [!DNL Analytics] comienza a enviar ID para los visitantes que cumplen los requisitos de Experience Cloud y la [!DNL Target] audiencia. En este punto, el nombre de audiencia y los datos correspondientes empiezan a mostrarse en la página de Audiencias de Experience Cloud. </br> |
| **[!UICONTROL Ventana de creación de audiencia]** | El lapso de tiempo seleccionado se utiliza para crear la audiencia en un calendario móvil. For example, “Last 30 days” (default) includes visitors that have qualified for the audience over the last 30 days from today's date (NOT from the original date when the segment was created.) |
| **[!UICONTROL Crear en la biblioteca de audiencias]** | The segments that you create and publish can be made available without latency in the Experience Cloud Audience Library. They are not dependent on Analytics updates. These segments do not count against your limit of 75 published segments. |
| **[!UICONTROL x de 75 Publicado]** | Shows the number of segments you have published to the Experience Cloud. Haga clic en el vínculo para ver una lista de los segmentos publicados y su grupo de informes y propietario asociados. |
| **[!UICONTROL Guardar]** | Saves this segment. |

## Unpublish or delete segments

Para eliminar un segmento publicado en Experience Cloud, tiene que cancelar la publicación primero. Para cancelar la publicación de un segmento, simplemente **demarque** la casilla que utilizó para publicarla.

>[!NOTE]
>
>**No puede** cancelar la publicación de un segmento que esté actualmente en uso por ninguna de las siguientes soluciones de Adobe: [!DNL Analytics] (en [!DNL Audience Analytics]), [!DNL Campaign], [!DNL Advertising Cloud] (para clientes de [!DNL Core Service] y [!DNL Audience Manager]) y todos los demás socios externos (para clientes de [!DNL Audience Manager]). **Puede** cancelar la publicación de un segmento en uso por [!DNL Target].

## View segment publishing status in the Segment Manager

1. Vaya a [!UICONTROL Analytics &gt; Componentes &gt; Segmentos].
1. Observe la nueva columna [!UICONTROL Publicado] . Yes/No refers to whether the segment has been published to the Experience Cloud or not.

![](assets/publish-status.png)

## Retrieve the  UUID[!DNL Audience Manager]

There are two ways to capture the AAM UUID currently associated with the browser:

* Adobe Experience Cloud Debugger
* Native developer tool in browsers (e.g., Chrome Developer Tools)

The following screenshots show you how to retrieve the AAM UUID on your browser and use it in Audience Manager Visitor Profile Viewer to validate trait &amp; segment membership.

**Método 1: Uso de Adobe Experience Cloud Debugger**

1. Download and install Adobe Experience Cloud Debugger in the Chrome Web Store.[](https://docs.adobe.com/content/help/en/analytics/implementation/testing-and-validation/debugger.html)
1. Inicie el depurador al cargar una página.
1. Desplácese hasta la sección Audience Manager y busque el UUID de AAM definido en la página del navegador actual (`50814298273775797762943354787774730612` en el ejemplo siguiente)

![](assets/debugger.jpg)

**Método 2: Uso de las herramientas para desarrolladores de Chrome (u otras herramientas para desarrolladores de exploradores)**

1. Iniciar Chrome Developer Tools antes de cargar una página
1. Cargue la página y marque Aplicaciones &gt; Cookies. El UUID de AAM debe configurarse en la cookie de terceros Demdex ([adobe.demdex.net](https://marketing.adobe.com/resources/help/en_US/aam/demdex-calls.html) en el ejemplo siguiente). El parámetro de campo es la configuración UUID de AAM en el navegador (`50814298273775797762943354787774730612` en el ejemplo siguiente).

![Herramientas para desarrolladores Chrome](assets/ggogle-uuid.png)

## Uso del visor de perfiles de [!UICONTROL visitantes de Audience Manager]

El UUID de AAM en el navegador se utilizará de forma predeterminada cuando se cargue el visor [!UICONTROL de perfiles de] visitante. Si comprueba las realizaciones de características para otros usuarios, introduzca un UUID en el campo UUID y haga clic en [!UICONTROL Actualizar]. Consulte Visor [de perfiles de](https://marketing.adobe.com/resources/help/en_US/aam/t_visitor_profile_viewer.html) visitantes para obtener más información.

![](assets/aam-vpv.png)

## Ver las características del segmento en [!DNL Audience Manager]

En AAM, la lista de visitantes con ECID para un segmento determinado se evalúa de forma de flujo continuo, ya que Analytics comparte segmentos con Experience Cloud.

1. En [!DNL Audience Manager], vaya a Datos de [!UICONTROL audiencia &gt; Características &gt; Características]de Analytics. Verá una carpeta para cada grupo de informes de Analytics asignada a su organización de Experience Cloud. Estas carpetas (para características, segmentos y fuentes de datos) se crean cuando se inicia o aprovisiona el servicio principal Perfiles y audiencias/personas.
1. Seleccione la carpeta para el grupo de informes en el que creó el segmento con el que quería compartir [!DNL Audience Manager]. Verá el segmento o la audiencia que creó. Cuando comparte un segmento, ocurren dos cosas en [!DNL Audience Manager]:
* Se crea una característica, primero sin datos en ella. Aprox. 8 horas después de que se publique el segmento en [!DNL Analytics], la lista de ECID se incorpora y comparte con [!DNL Audience Manager] y otras soluciones de Experience Cloud.

![](assets/aam-traits.png)

* Se crea un segmento de una característica. Utiliza la fuente de datos asociada al grupo de informes en el que publicó el segmento.

## View the segment in [!DNL Adobe Target]

The [!UICONTROL Publish this segment to the Experience Cloud] checkbox during the segment creation process in Adobe Analytics allows the segment to be available within the Adobe Target's custom audience library. Un segmento creado en Analytics o Audience Manager puede utilizarse para actividades en Target. Por ejemplo, puede crear actividades de campaña basadas en métricas de conversión de Analytics y segmentos de audiencias creados en Analytics.
], haga clic en [!UICONTROL Audiencias].
1. En la página [!UICONTROL Audiencias], busque la audiencia procedente de [!DNL Experience Cloud]. These audiences are available for use in [!DNL Target] activities.

