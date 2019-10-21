---
description: Permite usar el segmento para actividades de marketing en la biblioteca de audiencias, Target y Audience Manager.
seo-description: Permite usar el segmento para actividades de marketing en la biblioteca de audiencias, Target y Audience Manager.
seo-title: Publicación de segmentos en Experience Cloud
solution: Analytics
title: Publicación de segmentos en Experience Cloud
topic: Segmentos
uuid: e5ce20c0-ce43-423b-a29f-ba66e9e24d27
translation-type: tm+mt
source-git-commit: cd2d9f90c548d3bb32a57faa47b185dc25db1d5a

---


# Publicación de segmentos en Experience Cloud

>[!IMPORTANT]
>
>Las mejoras de latencia relativas a la publicación de segmentos y a la interfaz de usuario que se describen en esta página aún no se han implementado en todos los clientes. El entorno de producción actual se describe [aquí](https://docs.adobe.com/content/help/en/core-services/interface/audiences/t-publish-audience-segment.html).

Publishing a segment to the Experience Cloud lets you use the segment for marketing activity in the [!UICONTROL Audience Library], [!DNL Target], [!DNL Audience Manager], [!DNL Advertising Cloud], and [!DNL Campaign]. Las actualizaciones recientes han optimizado significativamente el flujo de trabajo de publicación. Anteriormente, la publicación de un segmento utilizable tardaba aproximadamente 48 horas.

Ahora, el procesamiento puede tardar hasta 8 horas, pero en función de otro tráfico y del tamaño del segmento, el procesamiento puede ser aún más rápido. (Sin embargo, actualmente no tenemos una forma de informarle cuando el segmento está disponible, por lo que tendrá que comprobarlo manualmente). También hemos aumentado el número máximo de segmentos editables a 75 (de 20). Puede ver los segmentos publicados en Componentes &gt; Segmentos.

>[!NOTE]
>
>Adobe Campaign (Classic y Standard) se comporta de forma diferente, ya que incurre en una latencia adicional de 24 horas además de la latencia de 8 horas.


## Requisitos previos

* Ensure that the report suite that you are saving this segment to is [enabled for the Experience Cloud](https://docs.adobe.com/content/help/en/core-services/interface/audiences/t-publish-audience-segment.html). De lo contrario, no podrá publicarla en Experience Cloud.
* Asegúrese de que está trabajando en un grupo de informes [asignado a su organización](https://docs.adobe.com/content/help/en/core-services/interface/about-core-services/report-suite-mapping.html)de Experience Cloud.
* Asegúrese de que su organización utiliza Experience Cloud ID.
* Para poder publicar segmentos, el administrador debe asignar el permiso Publicación [!UICONTROL de] segmentos a un perfil de producto en la Consola [de](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/admin-getting-started.html)administración y agregarlo al perfil de producto.


## Consideraciones

* **Límites** del grupo de informes: Puede publicar hasta 75 segmentos por grupo de informes. Este límite se aplica. Si ya ha publicado 75 segmentos, no podrá publicar ningún segmento adicional hasta que cancele la publicación de suficientes segmentos para superar el umbral de 75 segmentos.
* **Límites** de pertenencia: Las audiencias compartidas en Analytics [!DNL Experience Cloud] no pueden superar los 20 millones de miembros únicos.
* **Privacidad** de datos: Las audiencias no se filtran según el estado de autenticación de un visitante. Si un visitante puede navegar por su sitio en los estados de autenticado y no autenticado, las acciones que se dan cuando un visitante no está autenticado todavía pueden hacer que un visitante se incluya en una audiencia. Revise la privacidad [de](https://www.adobe.com/privacy/experience-cloud.html) Adobe Experience Cloud para comprender las implicaciones de privacidad completas del uso compartido de audiencias.
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
| **[!UICONTROL Publicar este segmento en Experience Cloud (para *<report suite>*)]** | Cuando esta opción está habilitada, el título y la definición del segmento (es decir, la audiencia del shell como se usa con frecuencia en las plataformas de publicidad) se comparten con Experience Cloud de forma instantánea, mientras que la pertenencia al segmento se evalúa y comparte cada 4 horas. <br> Cuando esa audiencia está asociada con una actividad en [!DNL Target], por ejemplo, [!DNL Analytics] comienza a enviar ID para los visitantes que cumplen los requisitos de Experience Cloud y la [!DNL Target] audiencia. En este punto, el nombre de audiencia y los datos correspondientes empiezan a mostrarse en la página de Audiencias de Experience Cloud. </br> |
| **[!UICONTROL Ventana de creación de audiencia]** | El lapso de tiempo seleccionado se utiliza para crear la audiencia en un calendario móvil. Por ejemplo, "Últimos 30 días" (predeterminado) incluye los visitantes que han cumplido los requisitos para la audiencia durante los últimos 30 días a partir de la fecha actual (NO desde la fecha original en que se creó el segmento). |
| **[!UICONTROL Crear en la biblioteca de audiencias]** | Los segmentos que cree y publique pueden estar disponibles sin latencia en la biblioteca de audiencias de Experience Cloud. No dependen de las actualizaciones de Analytics. Estos segmentos no cuentan con el límite de 75 segmentos publicados. |
| **[!UICONTROL x de 75 Publicado]** | Muestra el número de segmentos que ha publicado en Experience Cloud. Haga clic en el vínculo para ver una lista de los segmentos publicados y su grupo de informes y propietario asociados. |
| **[!UICONTROL Guardar]** | Guarda este segmento. |

## Cancelar la publicación o eliminar segmentos

Para eliminar un segmento publicado en Experience Cloud, tiene que cancelar la publicación primero. Para cancelar la publicación de un segmento, simplemente **demarque** la casilla que utilizó para publicarla.

>[!NOTE]
>
>**No puede** cancelar la publicación de un segmento que esté actualmente en uso por ninguna de las siguientes soluciones de Adobe: [!DNL Analytics] (en [!DNL Audience Analytics]), [!DNL Campaign], [!DNL Advertising Cloud] (para clientes de [!DNL Core Service] y [!DNL Audience Manager]) y todos los demás socios externos (para clientes de [!DNL Audience Manager]). **Puede** cancelar la publicación de un segmento en uso por [!DNL Target].

## Ver el estado de publicación de segmentos en el Administrador [!UICONTROL de segmentos]

1. Vaya a [!UICONTROL Analytics &gt; Componentes &gt; Segmentos].
1. Observe la nueva columna [!UICONTROL Publicado] . Sí/No hace referencia a si el segmento se ha publicado en Experience Cloud o no.

![](assets/publish-status.png)

## Recuperar el [!DNL Audience Manager] UUID

Existen dos formas de capturar el UUID de AAM asociado actualmente al explorador:

* Adobe Experience Cloud Debugger
* Herramienta nativa para desarrolladores en navegadores (por ejemplo, Chrome Developer Tools)

Las siguientes capturas de pantalla muestran cómo recuperar el UUID de AAM en el navegador y utilizarlo en el visor de perfiles de visitantes de Audience Manager para validar la pertenencia a rasgos y segmentos.

**Método 1: Uso de Adobe Experience Cloud Debugger**

1. Descargue e instale [Adobe Experience Cloud Debugger](https://docs.adobe.com/content/help/en/analytics/implementation/testing-and-validation/debugger.html) en Chrome Web Store.
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

## Ver el segmento en [!DNL Adobe Target]

The [!UICONTROL Publish this segment to the Experience Cloud] checkbox during the segment creation process in Adobe Analytics allows the segment to be available within the Adobe Target's custom audience library. Un segmento creado en Analytics o Audience Manager puede utilizarse para actividades en Target. Por ejemplo, puede crear actividades de campaña basadas en métricas de conversión de Analytics y segmentos de audiencias creados en Analytics.
], haga clic en [!UICONTROL Audiencias].
1. En la página [!UICONTROL Audiencias], busque la audiencia procedente de [!DNL Experience Cloud]. These audiences are available for use in [!DNL Target] activities.

