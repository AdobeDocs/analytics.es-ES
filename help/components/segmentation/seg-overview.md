---
description: Los segmentos le permiten identificar subconjuntos de visitantes basándose en sus características o en las interacciones con el sitio web. Los segmentos están diseñados como análisis de audiencia codificados que puede crear para sus necesidades específicas, y luego verificar, editar y compartir con otros integrantes del equipo, o bien utilizar en otros productos de Adobe y capacidades de Analytics.
title: Acerca de los segmentos
feature: Segmentation
exl-id: 11d930ca-5d59-4ea5-b6e5-fe3d57be94fd
source-git-commit: a90e754e50c0e7325d20a0a9436dab751d1a5f09
workflow-type: tm+mt
source-wordcount: '1156'
ht-degree: 97%

---

# Acerca de los segmentos

Los segmentos le permiten identificar subconjuntos de visitantes basándose en sus características o en las interacciones con el sitio web. Los segmentos están diseñados como datos del público que usted puede crear según sus necesidades específicas y a continuación, verificar, editar y compartir con otros integrantes del equipo o usar en otros productos de Adobe o funcionalidades de Analytics.

Los segmentos se basan en una jerarquía de niveles de [!UICONTROL Visitante], [!UICONTROL Visita] y [!UICONTROL Visita individual] usando un modelo de contenedor anidado. Los contenedores anidados le permiten definir los atributos y las acciones del visitante basándose en las reglas entre los contenedores y dentro de ellos. Los segmentos de Analytics pueden generarse, aprobarse, compartirse, guardarse y ejecutarse en varios productos y capacidades en [!DNL Adobe Experience Cloud]. Los segmentos pueden generarse a partir de un informe, integrarse en un informe de panel o marcarse como favoritos para acceder rápidamente a ellos.

Puede generar y guardar segmentos en el Generador de segmentos, o bien generarlos a partir de un informe de visitas en el orden previsto (en [!UICONTROL  Analysis Workspace)]). También puede utilizar y ampliar segmentos pregenerados basados en reglas específicas entre contenedores anidados, lo que le permite filtrar los resultados y aplicarlos a informes. Además, los segmentos se pueden usar juntos como [segmentos apilados](/help/components/segmentation/segmentation-workflow/seg-workflow.md).

Los segmentos identifican

- quiénes son sus visitantes (país, género, cafetería),
- qué dispositivos y servicios utilizan (explorador, motor de búsqueda, dispositivo móvil),
- desde dónde han navegado (motor de búsqueda, página de salida anterior, búsqueda natural),
- y mucho más.

<!--![](assets/seg.png)-->

Los segmentos pueden basarse en los siguientes valores:

- Visitantes en función de sus atributos: tipo de navegador, dispositivo, número de visitas, país, género.
- Visitantes en función de interacciones: campañas, búsqueda de palabras clave o motor de búsqueda.
- Visitantes en función de salidas y entradas: visitantes de Facebook, una página de aterrizaje definida o un dominio de referencia.
- Visitantes en función de variables personalizadas: campo de formulario, categorías definidas o ID de cliente.

Cuando genera segmentos de audiencia en el Generador de segmentos, define condiciones utilizando los operadores [!UICONTROL AND] y [!UICONTROL OR] entre los contenedores.

<table style="table-layout:fixed; border: none;">

<tr>

<td style="background-color: #E5E4E2;" colspan="3" width="200" height="100"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_User_18_N.svg"/> Visitantes</td>
</tr>

<tr>
<td style="background-color: #E5E4E2;" width="200"></td>
<td style="background-color: #D3D3D3;" colspan="2" width="200" height="100"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Visit_18_N.svg"/> Visitas</td>
</tr>

<tr>
<td style="background-color: #E5E4E2;" width="200" height="100"></td>
<td style="background-color: #D3D3D3;" width="200" height="100"></td>
<td style="background-color: #C0C0C0;" width="200" height="100" colspan="1"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Events_18_N.svg"/> Visitas únicas</td>
</tr>

<tr>
<td style="background-color: #E5E4E2;"></td><td colspan="2">Y</td></td>
</tr>

<tr>
<td style="background-color: #E5E4E2;" width="200"></td>
<td style="background-color: #D3D3D3;" colspan="2" width="200" height="100"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Visit_18_N.svg"/> Visitas</td>
</tr>

<tr>
<td style="background-color: #E5E4E2;" width="200" height="100"></td>
<td style="background-color: #D3D3D3;" width="200" height="100"></td>
<td style="background-color: #C0C0C0;" width="200" height="100" colspan="1"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Events_18_N.svg"/> Visitas únicas</td>
</tr>
</table>

<table style="table-layout:fixed; border: none;">

<tr>

<td style="background-color: #E5E4E2;" colspan="3" width="200" height="100"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_User_18_N.svg"/> Visitantes</td>
</tr>

<tr>
<td style="background-color: #E5E4E2;" width="200"></td>
<td style="background-color: #D3D3D3;" colspan="2" width="200" height="100"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Visit_18_N.svg"/> Visitas</td>
</tr>

<tr>
<td style="background-color: #E5E4E2;" width="200" height="100"></td>
<td style="background-color: #D3D3D3;" width="200" height="100"></td>
<td style="background-color: #C0C0C0;" width="200" height="100" colspan="1"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Events_18_N.svg"/> Visitas únicas</td>
</tr>

<tr>
<td style="background-color: #E5E4E2;"></td><td colspan="2">O BIEN</td></td>
</tr>

<tr>
<td style="background-color: #E5E4E2;" width="200"></td>
<td style="background-color: #D3D3D3;" colspan="2" width="200" height="100"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Visit_18_N.svg"/> Visitas</td>
</tr>

<tr>
<td style="background-color: #E5E4E2;" width="200" height="100"></td>
<td style="background-color: #D3D3D3;" width="200" height="100"></td>
<td style="background-color: #C0C0C0;" width="200" height="100" colspan="1"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Events_18_N.svg"/> Visitas únicas</td>
</tr>
</table>

<!--![](assets/standard_segment_containers.png)-->

Este tipo de segmentos filtra conjuntos de datos en función de características unidas con los operadores [!UICONTROL AND] y [!UICONTROL OR].

- Puede aplicar [varios segmentos a un informe o un proyecto](/help/components/segmentation/segmentation-workflow/seg-workflow.md).
- Los segmentos son universales para todos los grupos de informes.
- El [Generador de segmentos](/help/components/segmentation/segmentation-workflow/seg-workflow.md) simplifica la creación de segmentos.
- El nuevo [Administrador de segmentos](/help/components/segmentation/segmentation-workflow/seg-workflow.md) le permite configurar [flujos de trabajo](/help/components/segmentation/segmentation-workflow/seg-workflow.md) con funciones de uso compartido, etiquetado, verificación y aprobación de segmentos.
- Ahora puede [etiquetar segmentos](/help/components/segmentation/segmentation-workflow/seg-workflow.md) para organizar y buscar más tarde en lugar de utilizar carpetas.
- Puede crear [Segmentos secuenciales](/help/components/segmentation/segmentation-workflow/seg-sequential-build.md).
- El contenedor de [!UICONTROL Vista de página] es ahora el contenedor de [!UICONTROL Visita individual] para indicar que este contenedor segmenta todos los tipos de datos, no solo vistas de página. Por ejemplo, si vincula las llamadas de seguimiento, el Contenedor de visita individual incluirá o excluirá las llamadas trackAction desde los SDK móviles.

## Segmentación en Analysis Workspace

Analysis Workspace contiene estas funciones adicionales:

- [Compare segmentos](../../analyze/analysis-workspace/c-panels/c-segment-comparison/segment-comparison.md).
- Utilice [segmentos como dimensiones](https://experienceleague.adobe.com/docs/core-services/interface/audiences/audience-library.html?lang=es) en una comparación.
- Utilice segmentos en el [análisis de visitas en el orden previsto](../../analyze/analysis-workspace/visualizations/fallout/compare-segments-fallout.md).

## Segmentos proporcionados por Adobe

La barra Componente del carril izquierdo de la pantalla muestra los segmentos creados por usted y su compañía, así como los segmentos de Adobe listos para usar. Al hacer clic en **[!UICONTROL Mostrar todo]**, estos segmentos suelen aparecer al final de la lista y se identifican con el logotipo de Adobe a la derecha.

## Segmentos secuenciales {#sequential}

Los segmentos secuenciales le permiten identificar a los visitantes en función de la navegación y las vistas de página en su sitio, lo que proporciona un segmento de acciones e interacciones definidas. Los segmentos secuenciales le ayudan a identificar qué le gusta a un visitante, así como lo que evita. Cuando se generan segmentos secuenciales, se utiliza el operador [!UICONTROL THEN] para definir y ordenar la navegación del visitante.

<!--![](assets/sequential_seg.png)-->

| Visita uno | Visita dos | Visita tres |
|---|---|---|
| En la primera visita, el visitante accedió a la página de aterrizaje principal A, excluyó la página de campaña B y después vio la página del producto C. | En la segunda visita, el visitante volvió a acceder a la página de aterrizaje principal A, excluyó la página de campaña B y vio de nuevo la página del producto C, para acceder a continuación a una nueva página D. | En la tercera visita, el visitante accedió y siguió la misma ruta que en la primera y la segunda visita, y después excluyó la página F para ir directamente a una página de producto dirigida G. |

Los segmentos secuenciales pueden basarse en los siguientes valores de visitas individuales:

- Visitantes en función de una secuencia de visitas a la página: vistas de página en una sola visita, vistas de página en visitas separadas o visitas que excluyeron vistas de página.
- Visitantes en función del tiempo después y entre las vistas de página: después de un límite de tiempo, entre visitas únicas o después de un evento.

<table style="table-layout:fixed; border: none;">

<tr>

<td style="background-color: #E5E4E2;" colspan="3" width="200" height="100"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_User_18_N.svg"/> Visitantes</td>
</tr>

<tr>
<td style="background-color: #E5E4E2;" width="200"></td>
<td style="background-color: #D3D3D3;" colspan="2" width="200" height="100"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Visit_18_N.svg"/> Visitas</td>
</tr>

<tr>
<td style="background-color: #E5E4E2;" width="200" height="100"></td>
<td style="background-color: #D3D3D3;" width="200" height="100"></td>
<td style="background-color: #C0C0C0;" width="200" height="100" colspan="1"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Events_18_N.svg"/> Visitas únicas</td>
</tr>

<tr>
<td style="background-color: #E5E4E2;"></td><td colspan="2">A CONTINUACIÓN</td></td>
</tr>

<tr>
<td style="background-color: #E5E4E2;" width="200"></td>
<td style="background-color: #D3D3D3;" colspan="2" width="200" height="100"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Visit_18_N.svg"/> Visitas</td>
</tr>

<tr>
<td style="background-color: #E5E4E2;" width="200" height="100"></td>
<td style="background-color: #D3D3D3;" width="200" height="100"></td>
<td style="background-color: #C0C0C0;" width="200" height="100" colspan="1"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Events_18_N.svg"/> Visitas únicas</td>
</tr>
</table>

<table style="table-layout:fixed; border: none;">

<tr>

<td style="background-color: #E5E4E2;" colspan="3" width="200" height="100"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_User_18_N.svg"/> Visitantes</td>
</tr>

<tr>
<td style="background-color: #E5E4E2;" width="200"></td>
<td style="background-color: #D3D3D3;" colspan="2" width="200" height="100"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Visit_18_N.svg"/> Visitas</td>
</tr>

<tr>
<td style="background-color: #E5E4E2;" width="200" height="100"></td>
<td style="background-color: #D3D3D3;" width="200" height="100"></td>
<td style="background-color: #C0C0C0;" width="200" height="100" colspan="1"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Events_18_N.svg"/> Visitas únicas</td>
</tr>

<tr>
<td style="background-color: #E5E4E2;"></td><td style="background-color: #D3D3D3;"></td><td>Y</td></td>
</tr>

<tr>
<td style="background-color: #E5E4E2;" width="200" height="100"></td>
<td style="background-color: #D3D3D3;" width="200" height="100"></td>
<td style="background-color: #C0C0C0;" width="200" height="100" colspan="1"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Events_18_N.svg"/> Visitas únicas</td>
</tr>

<tr>
<td style="background-color: #E5E4E2;"></td><td colspan="2">A CONTINUACIÓN</td></td>
</tr>

<tr>
<td style="background-color: #E5E4E2;" width="200"></td>
<td style="background-color: #D3D3D3;" colspan="2" width="200" height="100"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Visit_18_N.svg"/> Visitas</td>
</tr>

<tr>
<td style="background-color: #E5E4E2;" width="200" height="100"></td>
<td style="background-color: #D3D3D3;" width="200" height="100"></td>
<td style="background-color: #C0C0C0;" width="200" height="100" colspan="1"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Events_18_N.svg"/> Visitas únicas</td>

<tr>
<td style="background-color: #E5E4E2;"></td><td style="background-color: #D3D3D3;"></td><td>O BIEN</td></td>
</tr>

<tr>
<td style="background-color: #E5E4E2;" width="200" height="100"></td>
<td style="background-color: #D3D3D3;" width="200" height="100"></td>
<td style="background-color: #C0C0C0;" width="200" height="100" colspan="1"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Events_18_N.svg"/> Visitas únicas</td>
</tr>
</tr>
</table>

<!--![](assets/sequential_segmentation_containers_view.png)-->

Un segmento secuencial filtra conjuntos de datos en función de las acciones del usuario usando el operador [!UICONTROL THEN].

## Vídeotutorial de segmentación {#segment-video}

Este vídeo ofrece una breve descripción sobre qué son los contenedores de segmento y cómo se utilizan.


>[!BEGINSHADEBOX]

Consulte ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Contenedores de segmento](https://video.tv.adobe.com/v/25401?quality=12&learn=on){target="_blank"} para ver un vídeo de demostración.

>[!ENDSHADEBOX]


## Acceso a las herramientas de segmentación {#access}

+++ **¿Cómo accedo al Generador de segmentos?**

Para acceder al Generador de segmentos, haga lo siguiente:

- Mostrar un informe existente y hacer clic en el icono de Segmentos ![icono de Segmento](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Segmentation_18_N.svg) en el menú de navegación de la izquierda. Haga clic en **[!UICONTROL Agregar]** en el carril de segmentos que se muestra o bien

- En la parte superior del Administrador de segmentos, haga clic en **[!UICONTROL + Agregar]**.  ![Botón Agregar](https://spectrum.adobe.com/static/icons/workflow_18/Smock_AddCircle_18_N.svg)

  o

- Haga clic en un título de segmento existente en el Administrador de segmentos para editarlo en el Generador de segmentos.

+++

+++ **¿Cómo accedo al Administrador de segmentos?**

Acceda al Administrador de segmentos de una de las siguientes maneras:

- Vaya a **[!UICONTROL Análisis]** > **[!UICONTROL Componentes]** en el panel de navegación superior. A continuación, haga clic en **[!UICONTROL Segmentos]**, o bien

- Mostrar un informe existente y hacer clic en el icono de Segmentos ![icono de Segmento](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Segmentation_18_N.svg) en el menú de navegación de la izquierda. A continuación, haga clic en **[!UICONTROL Administrar]**, o bien

- Presione la tecla de barra &quot;/&quot; situándose en cualquier lugar de la interfaz y busque el Administrador de segmentos.

+++

## Permisos {#section_648DFA3A882146C485A84ED014EEC707}

+++ **¿Qué derechos y privilegios necesito para utilizar, crear y administrar segmentos?**

De forma predeterminada, todos los usuarios pueden crear y editar segmentos personales. Sin embargo, los administradores pueden decidir quién cuenta con los [permisos para crear segmentos](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/home.html?lang=es) y pueden asignarlos a grupos específicos. Estos segmentos se pueden compartir directamente con cualquier otro usuario de Analytics.

Los administradores pueden editar cualquier segmento, así como compartir segmentos con grupos y con cualquier persona de la organización. [Más...](/help/components/segmentation/seg-reference/seg-rights.md)

+++

+++ **¿Puedo ver todos los segmentos de mi compañía?**

Sí, los administradores pueden ver todos los segmentos incluidos en la interfaz de usuario de [!DNL Analysis Workspace].

Report Builder muestra sus propios segmentos y los que se han compartido con usted.

+++

+++ **¿Puedo administrar todos los segmentos de Analytics en el Administrador de segmentos?**

Sí, todos los segmentos se pueden administrar en el Administrador de segmentos. El Administrador de segmentos muestra los segmentos que son visibles para el propietario (el usuario que creó el segmento), para usuarios compartidos y para los administradores. El selector de segmentos muestra los segmentos que son propiedad del usuario y que se comparten con él.

Los administradores pueden ver todos los segmentos incluidos en la interfaz de usuario de Analysis Workspace.

Report Builder solo muestra los segmentos que ha creado usted o los segmentos que se han compartido específicamente con usted.

+++

+++ **¿Por qué no puedo eliminar este segmento?**

Si el segmento se [publicó en Experience Cloud](/help/components/segmentation/segmentation-workflow/seg-workflow.md), no es posible eliminarlo ni editarlo. Pero sí copiarlo y editar esa versión copiada.

+++
