---
description: El informe Vínculos informa sobre los vínculos que se encontraron en la página actual. No informa de todos los vínculos recopilados para esa página.
title: Informe de vínculos
topic: Activity map
uuid: 1e7ca5d8-d144-4a21-a2f9-e05bd3232c59
translation-type: tm+mt
source-git-commit: 6b27755178d156b1eaf159640d466bd84659983d

---


# Informe de vínculos

El informe Vínculos informa sobre los vínculos que se encontraron en la página actual. No informa de todos los vínculos recopilados para esa página.

El informe Vínculos en la página oferta una vista tabular de los vínculos. En ocasiones, es posible que desee ver los clics en vínculos (u otras métricas) clasificados en una sola vista. Esto le permite comparar mejor un vínculo con otro. Cree el informe Vínculos en la página, que incluye una lista de clasificación de todos los vínculos de la página (por ID de vínculo), la información de clics (# y %) y la región de la página. Haga clic en el botón Vínculos en el informe Página en la barra de herramientas de Mapa de Actividad.

The **[!UICONTROL Links On Page]** report opens below the browser frame in the Activity Map dashboard.

## Modo estándar {#section_C8D2A1C07A2A4E3A8F84AC9240603FA7}

![](assets/links_in_page.png)

En el modo Estándar, el informe &quot;Vínculos en la página&quot; muestra datos de vínculos que van de un solo día a varios días, agregados en el intervalo de fechas completo. Se mostrará la siguiente información para cada vínculo:

<table id="table_3DE41B2CFA644B70AF802A3123CE51D9"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Columna </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Rango </td> 
   <td colname="col2"> Clasificar en la página. En el modo Estándar, el valor de clasificación permanece igual, independientemente de la columna en la que se haga clic. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ID del vínculo </td> 
   <td colname="col2">The link's primary ID (for more information on how primary ID is defined by the <a href="/help/analyze/activity-map/activitymap-link-tracking/activitymap-link-tracking-methodology.md">New Link Tracking Methodology</a>) </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Clics </td> 
   <td colname="col2"> El número de clics brutos correspondientes a un vínculo determinado y el porcentaje de clics totales hechos en la página. Si el usuario elige una métrica diferente en la barra de herramientas, el informe Vínculo informará en su lugar sobre esa métrica. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Región </td> 
   <td colname="col2"> Representa la región de la página donde se encuentra el vínculo. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visibilidad </td> 
   <td colname="col2">Se refiere al estado de visibilidad del vínculo. Existen dos valores posibles: 
    <ul id="ul_BABCC0F64145407C9D439150A6898E6D">
     <li id="li_9AF0479BDCEB4A44A37292FAABFA83A5"><b>Oculto</b>: el vínculo se encuentra actualmente en la página pero no está visible para el usuario final (como un submenú en un menú de navegación que solo se muestra visible si el usuario pasa el ratón por encima del menú principal) </li>
     <li id="li_C6FA4EC27EDD4341AB9821E2B4BC9E60"><b>Mostrado</b>: el vínculo se muestra actualmente en la página. Sin embargo, puede mostrarse debajo del pliegue: el usuario tendría que desplazarse por la página para verla. </li>
    </ul><p>Nota: Si un vínculo está como “Oculto”, no aparecerá ninguna de sus superposiciones. </p></td> 
  </tr> 
 </tbody> 
</table>

**Filtrar datos**

When you want to zero in on a specific link, you can search for a related term in the **[!UICONTROL Filter Data]** field. Solo los vínculos que coincidan con la búsqueda tendrán superposiciones. Sin un filtro, se mostrarán las superposiciones especificadas en la Configuración [del mapa de](/help/analyze/activity-map/activitymap-overlay-settings.md) Actividad.

## Modo Activo {#section_AC1967217B5A4532ACB01D33636F6770}

En el modo Activo, el informe Vínculos en la página muestra datos de tendencias de varios minutos.

![](assets/links_on_page.png)

<table id="table_61D1FB0F02894055A1AB394DE4FE4742"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Columna </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Rango </td> 
   <td colname="col2"> Clasificar en la página. En el caso de una superposición de degradado o burbuja, el valor de clasificación permanece igual, independientemente de la columna en la que se haga clic. En el caso de una superposición de ganadores/perdedores, ese valor de clasificación cambia según los vínculos que más ganaron o perdieron. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ID del vínculo </td> 
   <td colname="col2">ID principal del vínculo. Para obtener más información sobre cómo se define el ID principal mediante la nueva metodología <a href="/help/analyze/activity-map/activitymap-link-tracking/activitymap-link-tracking-methodology.md"> de seguimiento de vínculos</a>. </td>
  </tr> 
  <tr> 
   <td colname="col1"> Clics en vínculos </td> 
   <td colname="col2"> Total de clics para el período de tiempo seleccionado. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> % Cambio </td> 
   <td colname="col2"> % de cambio entre las métricas de vínculo del período actual y las métricas de vínculo del período anterior. El porcentaje de cambio negativo se muestra en rojo, positivo en verde. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Tendencia </td> 
   <td colname="col2"> Un gráfico de líneas para todos los períodos recopilados. El período seleccionado actualmente se indica con un marcador verde. El período de desplazamiento actual se indica con un marcador rojo. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Región </td> 
   <td colname="col2"> Representa la región de la página donde se encuentra el vínculo. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visibilidad </td> 
   <td colname="col2">Se refiere al estado de visibilidad del vínculo. Existen dos valores posibles: 
    <ul id="ul_B10C55ED4D3C4CF99506DC467E2E7CFB">
     <li id="li_EA646722A51041CC9E62C56DEF92C81F">Oculto: está en la página pero no es visible para usted (por ejemplo, cualquier vínculo que aparezca después de cargar la página). </li>
     <li id="li_F9543614C2894003AC9984A7404E2785">Mostrado: actualmente se muestra en la página. Sin embargo, puede mostrarse debajo del pliegue: tendría que desplazarse por la página para verla. </li>
    </ul></td> 
  </tr> 
 </tbody> 
</table>

## Ordenación y filtrado {#section_4B8E8233C21247CAA70DAEC2156548AD}

En ocasiones, solo es necesario analizar los resultados de una región de página específica (por ejemplo, el panel izquierdo) para decidir cómo organizar el contenido de esa región específica de la página web.

Con este fin, hemos creado una funcionalidad de clasificación y filtrado para los vínculos en el informe Vínculos en la página. El filtrado está disponible a través del campo de filtro y el término de búsqueda se aplicará a la columna ID del vínculo y a la columna Región del vínculo. La ordenación está disponible haciendo clic en las llamadas (Clasificación, ID del vínculo, Clics, Cambio con el tiempo, Región, Visibilidad) y puede ser ascendente y descendente. Las superposiciones desaparecen del sitio Web cuando los vínculos se filtran desde el informe Vínculos en la página.
