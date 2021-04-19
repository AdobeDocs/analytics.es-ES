---
description: Le permite utilizar el segmento para actividades de marketing en la biblioteca de audiencias, Target y Audience Manager.
title: Publicación de segmentos en Experience Cloud
feature: Segmentación
uuid: e5ce20c0-ce43-423b-a29f-ba66e9e24d27
exl-id: 0215f896-d3f8-42cc-ac8d-8a94b009927b
translation-type: tm+mt
source-git-commit: f9b5380cfb2cdfe1827b8ee70f60c65ff5004b48
workflow-type: tm+mt
source-wordcount: '1346'
ht-degree: 99%

---

# Publicación de segmentos en Experience Cloud

La publicación de un segmento de Adobe Analytics en Experience Cloud le permite utilizarlo para la actividad de marketing en [!DNL Audience Manager] y en otros canales de activación, incluidos los de Adobe [!DNL Advertising Cloud], [!DNL Target] y [!DNL Campaign]. Las actualizaciones recientes han optimizado significativamente el flujo de trabajo de publicación. Ahora puede publicar segmentos de Analytics en Experience Cloud en menos de 8 horas. Utilice estos segmentos para activar audiencias en el Audience Manager a todos los destinos de flujo descendente.

También hemos aumentado el número máximo de segmentos de Adobe Analytics editables a 75 (de 20). Puede ver los segmentos publicados en [!UICONTROL Analytics > Componentes > Segmentos].

>[!NOTE]
>
>Adobe Campaign (Classic y Standard) se comporta de forma diferente, ya que incurre en una latencia adicional de 24 horas además de la latencia de 8 horas.


## Requisitos previos

* Asegúrese de que el grupo de informes en el que está guardando este segmento está [habilitado para Experience Cloud](https://docs.adobe.com/content/help/es-ES/core-services/interface/audiences/t-publish-audience-segment.html). De lo contrario, no podrá publicarlo en Experience Cloud.
* Asegúrese de que está trabajando en un grupo de informes [asignado a su organización de Experience Cloud](https://docs.adobe.com/content/help/es-ES/core-services/interface/about-core-services/report-suite-mapping.html).
* Asegúrese de que su organización utiliza Experience Cloud ID.
* Para poder publicar segmentos, el administrador debe asignar el permiso [!UICONTROL Publicación de segmentos] a un perfil de producto en [Admin Console](https://docs.adobe.com/content/help/es-ES/core-services/interface/manage-users-and-products/admin-getting-started.html) y agregarlo al perfil de producto.


## Consideraciones

* **Límites del grupo de informes**: Puede publicar hasta 75 segmentos por grupo de informes. Este límite se aplica. Si ya ha publicado 75 segmentos, no podrá publicar ningún segmento adicional hasta que cancele la publicación de suficientes segmentos para bajar del umbral de 75 segmentos.
* **Límites de miembros**: las audiencias compartidas en [!DNL Experience Cloud] desde Adobe Analytics no pueden superar los 20 millones de miembros únicos.
* Las audiencias de **Privacidad de los datos** no se filtran según el estado de autenticación de un visitante. Si un visitante puede navegar por su sitio en los estados de autenticado y no autenticado, las acciones que se dan cuando un visitante no está autenticado todavía pueden hacer que un visitante se incluya en una audiencia. Revise la [privacidad de Adobe Experience Cloud](https://www.adobe.com/es/privacy/experience-cloud.html) para comprender las implicaciones de privacidad completas del uso compartido de audiencias.
* Para ver una discusión sobre las **diferencias entre segmentos en [!DNL Adobe Analytics] y [!DNL Audience Manager]**, vaya [aquí](https://docs.adobe.com/content/help/es-ES/analytics/integration/audience-analytics/audience-analytics-workflow/aam-analytics-segments.html).

## Cronología de publicación de segmentos

| Qué está disponible | Cuándo esté disponible | Dónde está disponible |
|---|---|---|
| Metadatos (título y definición del segmento) | Inmediatamente después de la publicación | [!DNL Audience Manager], [!UICONTROL Biblioteca de audiencias de Experience Cloud], [!DNL Target] |
| Segmento utilizable al ser miembro | ~ 8 horas después de la publicación | Visor de perfiles de visitante en [!DNL Audience Manager] |
| Población de miembros y características | En un plazo de 24-48 horas | [!DNL Audience Manager] |

>[!NOTE]
>Una vez por semana, todos los datos se sincronizarán por completo para tener en cuenta los retrasos o discrepancias que no se hayan capturado en la semana anterior.

## Publicación de segmentos en el [!UICONTROL Generador de segmentos]

1. Vaya a **[!UICONTROL Analytics > Workspace > Componentes > Segmentos] > +**
1. Cree un segmento en el [!UICONTROL Generador de segmentos].
1. Proporcione un título y una descripción para el segmento; de lo contrario, no podrá guardarlo.
1. Consulte **[!UICONTROL Publicar este segmento en Experience Cloud (para *grupo de informes*)]**.

![](assets/publish-ec.png)

>[!IMPORTANT]
>Asegúrese de utilizar “Visitantes con Experience Cloud ID” al consultar las vistas previas de segmentos en Analytics en lugar de la vista previa de segmentos de “visitantes únicos” totales al comparar los números de Adobe Analytics con los de Audience Manager:
>
>![](assets/seg-vis-ecid.png)

| Elemento | Descripción |
|---|---|
| **[!UICONTROL Publicar este segmento en Experience Cloud (para *`<report suite>`*)]** | Cuando esta opción está habilitada, el título y la definición del segmento (es decir, la audiencia del shell que se usa con frecuencia en las plataformas de publicidad) se comparten con Experience Cloud de forma instantánea, mientras que la pertenencia al segmento se evalúa y comparte cada 4 horas. <br> Cuando dicha audiencia está asociada a una actividad en [!DNL Target], por ejemplo, [!DNL Analytics] comienza a enviar ID para los visitantes que son aptos para esta audiencia de Experience Cloud y [!DNL Target]. En este punto, el nombre de audiencia y los datos correspondientes empiezan a mostrarse en la página de Audiencias de Experience Cloud. </br> |
| **[!UICONTROL Ventana de creación de audiencia]** | El lapso de tiempo seleccionado se utiliza para crear la audiencia en un calendario móvil. Por ejemplo, “Últimos 30 días” (predeterminado) incluye los visitantes que han cumplido los requisitos para la audiencia durante los últimos 30 días respecto a la fecha actual (NO desde la fecha original en que se creó el segmento). |
| **[!UICONTROL Crear en la biblioteca de audiencias]** | Los segmentos que cree y publique pueden estar disponibles sin latencia en la biblioteca de audiencias de Experience Cloud. No dependen de las actualizaciones de Analytics. Estos segmentos no cuentan con el límite de 75 segmentos publicados. |
| **[!UICONTROL x de 75 publicados]** | Muestra el número de segmentos que ha publicado en Experience Cloud. Haga clic en el vínculo para ver una lista de los segmentos publicados y su grupo de informes y propietario asociados. |
| **[!UICONTROL Guardar]** | Guarda este segmento. |

## Cancelar la publicación o eliminar segmentos

Para eliminar un segmento publicado en Experience Cloud, tiene que cancelar la publicación primero. Para cancelar la publicación de un segmento, simplemente **demarque** la casilla que utilizó para publicarla.

>[!NOTE]
>
> **No puede** cancelar la publicación de un segmento que esté actualmente en uso por ninguna de las siguientes soluciones de Adobe: [!DNL Analytics] (en [!DNL Audience Analytics]), [!DNL Campaign], [!DNL Advertising Cloud] (para clientes de [!DNL Core Service] y [!DNL Audience Manager]) y todos los demás socios externos (para clientes de [!DNL Audience Manager]). **Puede** cancelar la publicación de un segmento en uso por [!DNL Target].

## Ver el estado de publicación de segmentos en el [!UICONTROL Administrador de segmentos]

1. Vaya a [!UICONTROL Analytics > Componentes > Segmentos].
1. Observe la nueva columna [!UICONTROL Publicado]. Sí/No hace referencia a si el segmento se ha publicado en Experience Cloud o no.

![](assets/publish-status.png)

## Conseguir el UUID de [!DNL Audience Manager]

Existen dos formas de registrar el UUID de AAM asociado actualmente al explorador:

* Adobe Experience Cloud Debugger
* Herramienta nativa para desarrolladores en navegadores (por ejemplo, Chrome DevTools)

Las siguientes capturas de pantalla muestran cómo conseguir el UUID de AAM en el navegador y utilizarlo en el visor de perfiles de visitantes de Audience Manager para validar la pertenencia de los rasgos y segmentos.

**Método 1: Uso de Adobe Experience Cloud Debugger**

1. Descargue e instale [Adobe Experience Cloud Debugger](https://docs.adobe.com/content/help/es-ES/analytics/implementation/validate/debugger.html) en Chrome Web Store.
1. Inicie Debugger al cargar una página.
1. Desplácese hasta la sección Audience Manager y busque el UUID de AAM definido en la página del navegador actual (`50814298273775797762943354787774730612` en el ejemplo siguiente)

![](assets/debugger.jpg)

**Método 2: Uso de las herramientas para desarrolladores de Chrome (u otras herramientas para desarrolladores de navegador)**

1. Iniciar Herramientas para desarrolladores Chrome antes de cargar una página
1. Cargue la página y seleccione Aplicaciones > Cookies. El UUID de AAM debe configurarse en la cookie de terceros Demdex ([adobe.demdex.net](https://docs.adobe.com/content/help/es-ES/audience-manager/user-guide/reference/demdex-calls.html) en el ejemplo siguiente). El parámetro de campo es la configuración UUID de AAM en el navegador (`50814298273775797762943354787774730612` en el ejemplo siguiente).

![Herramientas para desarrolladores Chrome](assets/ggogle-uuid.png)

## Uso del [!UICONTROL Visor de perfiles de visitantes] de Audience Manager

El UUID de AAM en el navegador se utilizará de forma predeterminada cuando se cargue el [!UICONTROL visor de perfiles de visitante]. Si comprueba las realizaciones de características para otros usuarios, introduzca un UUID en el campo UUID y haga clic en [!UICONTROL Actualizar]. Consulte [Visor de perfiles de visitantes](https://docs.adobe.com/content/help/es-ES/audience-manager/user-guide/features/visitor-profile-viewer.html) para obtener más información.

![](assets/aam-vpv.png)

## Vea las características del segmento en [!DNL Audience Manager]

En AAM, la lista de visitantes con ECID para un segmento determinado se evalúa de forma de flujo continuo, ya que Analytics comparte segmentos con Experience Cloud.

1. En [!DNL Audience Manager], vaya a [!UICONTROL Datos de audiencia > Rasgos > Rasgos de Analytics]. Verá una carpeta para cada grupo de informes de Analytics asignada a su organización de Experience Cloud. Estas carpetas (para características, segmentos y fuentes de datos) se crean cuando se inicia o aprovisiona el servicio principal Perfiles y Audiencias/Personas.
1. Seleccione la carpeta para el grupo de informes en el que creó el segmento quería compartir con [!DNL Audience Manager]. Verá el segmento o la audiencia que creó. Cuando comparte un segmento, ocurren dos cosas en [!DNL Audience Manager]:
* Se crea una característica, primero sin datos en ella. Aprox. 8 horas después de que se publique el segmento en [!DNL Analytics], la lista de ECID se incorpora y comparte con [!DNL Audience Manager] y otras soluciones de Experience Cloud.

![](assets/aam-traits.png)

* Se crea un segmento de una característica. Este utiliza la fuente de datos asociada al grupo de informes donde publicó el segmento.
* La caducidad de la característica ahora se establece en 16 días (antes era 2 días).

## Ver el segmento en [!DNL Adobe Target]

La casilla de verificación [!UICONTROL Publicar este segmento en Experience Cloud] durante el proceso de creación de segmentos en Adobe Analytics permite que el segmento esté disponible en la biblioteca de audiencias personalizada de Adobe Target. Un segmento creado en Analytics o Audience Manager puede utilizarse para actividades en Target. Por ejemplo, puede crear actividades de campaña basadas en métricas de conversión de Analytics y segmentos de audiencias creados en Analytics.

1. Haga clic en [!UICONTROL Audiencias].
1. En la página [!UICONTROL Audiencias], busque la audiencia procedente de [!DNL Experience Cloud]. Estas audiencias están disponibles para su uso en actividades [!DNL Target].
