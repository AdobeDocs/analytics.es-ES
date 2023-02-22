---
description: Los segmentos le permiten identificar subconjuntos de visitantes basándose en sus características o en las interacciones con el sitio web. Los segmentos están diseñados como análisis de audiencia codificados que puede crear para sus necesidades específicas, y luego verificar, editar y compartir con otros integrantes del equipo, o bien utilizar en otros productos de Adobe y capacidades de Analytics.
title: Acerca de los segmentos
feature: Segmentation
exl-id: 11d930ca-5d59-4ea5-b6e5-fe3d57be94fd
source-git-commit: 385c27de382b7bb047b6c62420d0471dd6e1650d
workflow-type: tm+mt
source-wordcount: '1164'
ht-degree: 88%

---

# Acerca de los segmentos

Los segmentos le permiten identificar subconjuntos de visitantes basándose en sus características o en las interacciones con el sitio web. Los segmentos están diseñados como perspectivas de audiencia que puede crear para sus necesidades específicas y, a continuación, comprobar, editar y compartir con otros integrantes del equipo, o bien utilizar en otros productos de Adobe y funciones de Analytics.

Los segmentos se basan en una jerarquía de niveles de [!UICONTROL visitante], [!UICONTROL visita] y [!UICONTROL visita individual] usando un modelo de contenedor anidado. Los contenedores anidados le permiten definir los atributos y las acciones del visitante basándose en las reglas entre los contenedores y dentro de ellos. Los segmentos de Analytics pueden generarse, aprobarse, compartirse, guardarse y ejecutarse en varios productos y capacidades en [!DNL Adobe Experience Cloud]. Los segmentos pueden generarse a partir de un informe, integrarse en un informe de panel o marcarse como favoritos para acceder rápidamente a ellos.

Puede generar y guardar segmentos en el Generador de segmentos, o bien crearlos a partir de un informe de visitas en el orden previsto (en  Analysis Workspace). También puede utilizar y ampliar segmentos pregenerados basados en reglas específicas entre contenedores anidados, lo que le permite filtrar los resultados y aplicarlos a informes. Además, los segmentos pueden utilizarse juntos como [segmentos apilados](/help/components/segmentation/segmentation-workflow/seg-workflow.md).

Los segmentos identifican quiénes son sus visitantes (país, sexo, cafetería), qué dispositivos y servicios utilizan (explorador, motor de búsqueda, dispositivo móvil), desde dónde navegan (motor de búsqueda, página de salida anterior, búsqueda natural) y mucho más.

![](assets/seg.png)

Los segmentos pueden basarse en los siguientes valores:

* Visitantes en función de sus atributos: tipo de navegador, dispositivo, número de visitas, país, género.
* Visitantes en función de interacciones: campañas, búsqueda de palabras clave o motor de búsqueda.
* Visitantes en función de salidas y entradas: visitantes de Facebook, una página de aterrizaje definida o un dominio de referencia.
* Visitantes en función de variables personalizadas: campo de formulario, categorías definidas o ID de cliente.

Cuando genera segmentos de audiencia en el Generador de segmentos, define condiciones utilizando los operadores [!UICONTROL AND] y [!UICONTROL OR] entre los contenedores.

![](assets/standard_segment_containers.png)

Este tipo de segmentos filtra conjuntos de datos en función de características unidas con los operadores [!UICONTROL AND] y [!UICONTROL OR].

* Puede aplicar [varios segmentos a un informe o un proyecto](/help/components/segmentation/segmentation-workflow/seg-workflow.md).
* Los segmentos son universales para todos los grupos de informes.
* El [Generador de segmentos](/help/components/segmentation/segmentation-workflow/seg-workflow.md) simplifica la creación de segmentos.
* El nuevo [Administrador de segmentos](/help/components/segmentation/segmentation-workflow/seg-workflow.md) le permite configurar [flujos de trabajo](/help/components/segmentation/segmentation-workflow/seg-workflow.md) con funciones de uso compartido, etiquetado, verificación y aprobación de segmentos.
* Ahora puede [etiquetar segmentos](/help/components/segmentation/segmentation-workflow/seg-workflow.md) para organizar y buscar más tarde en lugar de utilizar carpetas.
* Puede crear [Segmentos secuenciales](/help/components/segmentation/segmentation-workflow/seg-sequential-build.md).
* La variable [!UICONTROL Vista de página] El contenedor es ahora el [!UICONTROL Visita] contenedor para indicar que este contenedor segmenta todo tipo de datos y no solo vistas de página. Por ejemplo, si vincula las llamadas de seguimiento, el Contenedor de visita individual incluirá o excluirá las llamadas trackAction desde los SDK móviles.

## Segmentación en Analysis Workspace

Analysis Workspace contiene estas funciones adicionales:

* [Compare segmentos](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/segment-comparison/segment-comparison.html?lang=es).
* Utilice [segmentos como dimensiones](https://experienceleague.adobe.com/docs/core-services/interface/audiences/audience-library.html?lang=es) en una comparación.
* Utilice segmentos en el [análisis de visitas en el orden previsto](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/fallout/compare-segments-fallout.html?lang=es).

## Segmentos proporcionados por el Adobe

El carril Componente de la parte izquierda de la pantalla muestra los segmentos creados por usted y su empresa, así como los segmentos de Adobe que se proporcionan fuera del cuadro. Al hacer clic en **[!UICONTROL Mostrar todo]**, estos segmentos suelen aparecer en la parte inferior de la lista y se identifican con el logotipo del Adobe a la derecha:

![segmentos de Adobe](assets/adobe-segs.png)

## Segmentos secuenciales {#sequential}

Los segmentos secuenciales le permiten identificar a los visitantes en función de la navegación y las vistas de página en su sitio, lo que proporciona un segmento de acciones e interacciones definidas. Los segmentos secuenciales le ayudan a identificar qué le gusta a un visitante, así como lo que evita. Cuando se generan segmentos secuenciales, se utiliza el operador [!UICONTROL THEN] para definir y ordenar la navegación del visitante.

![](assets/sequential_seg.png)

| Visita uno | Visita dos | Visita tres |
|---|---|---|
| En la primera visita, el visitante accedió a la página de aterrizaje principal (A), excluyó la página de campaña (B) y después vio la página del producto (C). | En la segunda visita, el visitante volvió a acceder a la página de aterrizaje principal (A), excluyó la página de campaña (B) y vio de nuevo la página del producto (C), para acceder a continuación a una nueva página (D). | En la tercera visita, el visitante accedió y siguió la misma ruta que en la primera y la segunda visita, y después excluyó la página F para ir directamente a una página de producto dirigida. |

Los segmentos secuenciales pueden basarse en los siguientes valores de visitas individuales:

* Visitantes en función de una secuencia de visitas individuales de páginas: vistas de página en una sola visita, vistas de página en visitas separadas o visitas que excluyeron vistas de página.
* Visitantes en función del tiempo después y entre las vistas de página: después de un límite de tiempo, entre visitas individuales o después de un evento.

![](assets/sequential_segmentation_containers_view.png)

Un segmento secuencial filtra conjuntos de datos en función de las acciones del usuario usando el operador [!UICONTROL THEN].

## Vídeo explicativo {#segment-video}

En este vídeo se proporciona una breve descripción sobre qué son los contenedores de segmento y cómo se utilizan: [Contenedores de segmento en Adobe Analytics](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/components/segmentation/segment-containers.html?lang=es)

## Acceso a las herramientas de segmentación {#access}

+++ **¿Cómo accedo al Generador de segmentos?**

Para acceder al Generador de segmentos, haga lo siguiente:

* Mostrar un informe existente y hacer clic en el icono de Segmentos ![icono de Segmento](assets/segment_icon.png) en el menú de navegación de la izquierda. Haga clic en **[!UICONTROL Agregar]** en el carril de segmentos que se muestra o bien

* En la parte superior del Administrador de segmentos, haga clic en **[!UICONTROL + Agregar]**.  ![Botón Agregar](assets/add_button.png)

   o

* Haga clic en un título de segmento existente en el Administrador de segmentos para editarlo en el Generador de segmentos.

+++

+++ **¿Cómo accedo al Administrador de segmentos?**

Acceda al Administrador de segmentos de una de las siguientes maneras:

* Vaya a **[!UICONTROL Análisis]** > **[!UICONTROL Componentes]** en el panel de navegación superior. A continuación, haga clic en **[!UICONTROL Segmentos]**, o bien

* Mostrar un informe existente y hacer clic en el icono de Segmentos ![icono de Segmento](assets/segment_icon.png) en el menú de navegación de la izquierda. A continuación, haga clic en **[!UICONTROL Administrar]**, o bien

* Presione la tecla de barra &quot;/&quot; situándose en cualquier lugar de la interfaz y busque el Administrador de segmentos.

+++

## Permisos {#section_648DFA3A882146C485A84ED014EEC707}

+++ **¿Qué derechos y privilegios necesito para utilizar, crear y administrar segmentos?**

De forma predeterminada, todos los usuarios pueden crear y editar segmentos personales. Sin embargo, los administradores pueden decidir quién cuenta con los [permisos para crear segmentos](https://experienceleague.adobe.com/docs/analytics/admin/user-product-management/user-groups/groups.html?lang=es) y pueden asignarlos a grupos específicos. Estos segmentos se pueden compartir directamente con cualquier otro usuario de Analytics.

Los administradores pueden editar cualquier segmento, así como compartir segmentos con grupos y con cualquier persona de la organización. [Más...](/help/components/segmentation/seg-reference/seg-rights.md)

+++

+++ **¿Puedo ver todos los segmentos de mi compañía?**

Sí, los administradores pueden ver todos los segmentos incluidos en las interfaces de usuario de [!DNL Analysis Workspace] e [!DNL Reports & Analytics].

Report Builder muestra los segmentos que posee y los segmentos que han compartido con usted.

+++

+++ **¿Puedo administrar todos los segmentos de Analytics en el Administrador de segmentos?**

Sí, todos los segmentos se pueden administrar en el Administrador de segmentos. El Administrador de segmentos muestra los segmentos que son visibles para el propietario (el usuario que creó el segmento), para usuarios compartidos y para los administradores. El selector de segmentos muestra los segmentos que son propiedad del usuario y que se comparten con él.

Los administradores pueden ver todos los segmentos incluidos en las interfaces de usuario de Analysis Workspace y [!DNL Reports & Analytics].

Report Builder solo muestra los segmentos que ha creado usted o los segmentos que se han compartido específicamente con usted.

+++

+++ **¿Por qué no puedo eliminar este segmento?**

Si el segmento se [publicó en Experience Cloud](/help/components/segmentation/segmentation-workflow/seg-workflow.md), no es posible eliminarlo ni editarlo. Pero sí copiarlo y editar esa versión copiada.

+++
