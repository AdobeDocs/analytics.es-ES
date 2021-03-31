---
description: En el panel Configuración de Activity Map se pueden modificar la configuración y las propiedades de todos los tipos de visualizaciones de superposición.
title: Definición de la configuración de Activity Map
uuid: 42a0309e-3efc-4506-989b-09b6fe419423
feature: Activity Map
role: Profesional empresarial, administrador
translation-type: tm+mt
source-git-commit: 894ee7a8f761f7aa2590e06708be82e7ecfa3f6d
workflow-type: tm+mt
source-wordcount: '628'
ht-degree: 99%

---


# Definición de la configuración de Activity Map

En el panel Configuración de Activity Map se pueden modificar la configuración y las propiedades de todos los tipos de visualizaciones de superposición.

Para acceder al panel Configuración de Activity Map, haga clic en el icono del engranaje que hay en la barra de herramientas de Activity Map.

El panel Configuración muestra un contenido concreto según el modo de aplicación seleccionado. La ficha Otros contiene ajustes generales.

| Estándar | **[!UICONTROL Superposiciones de degradado]** o **[!UICONTROL burbujas]** |
|---|---|
| Activo | Superposiciones de **[!UICONTROL ganadores y perdedores]**, **[!UICONTROL degradado]** y **[!UICONTROL burbujas]** |
| Otro | Selección de idioma y de grupo de informes |

## Configuración de la superposición en el modo Estándar {#section_24DB95376E1A448494ECF3F57743FC19}

![](assets/settings_standard.png)

<table id="table_0244107DE6D142F2A1DA4882E0ED9826"> 
 <thead> 
  <tr> 
   <th colname="col2" class="entry"> Configuración </th> 
   <th colname="col3" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col2"> <span class="uicontrol"> La etiqueta se superpone con</span> </td> 
   <td colname="col3"> 
    <ul id="ul_13AD02789F2D4904A35215A8FA230F3E"> 
     <li id="li_8DB71636D2074C69B0D94D3FB0CAFE28"> <b>Sin etiquetas</b>: solo aplicable para la superposición de degradado. En este caso, el color de la superposición dará una idea de la clasificación del vínculo. </li> 
     <li id="li_39C98D7EA9514C1D8731B9D21C0E73A6"> <b>Valor</b>: el total bruto de la métrica que corresponde a ese vínculo </li> 
     <li id="li_A5F583E45BCD4F2399398F9DCC7FE382"> <b>Porcentaje</b>: porcentaje de la métrica para este vínculo en la métrica total de la página. </li> 
     <li id="li_E4BF7D3B863E4B6C8E737CF29ADA9D67"> <b>Rango</b>: clasificación de este vínculo en relación con todos los vínculos que hay en la página representada. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <span class="uicontrol"> Tamaño de fuente de la etiqueta</span> </td> 
   <td colname="col3"> Permite aumentar o reducir el tamaño de la fuente de la etiqueta de la superposición con un regulador para mejorar la legibilidad. </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <span class="uicontrol"> Mostrar</span> </td> 
   <td colname="col3">Seleccione <span class="uicontrol">Superiores</span>, <span class="uicontrol">Inferiores</span> o <span class="uicontrol">Todos los vínculos</span> para mostrarlos en la superposición. Si selecciona Superiores o Inferiores, también debe elegir el número de vínculos que se verán. </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <span class="uicontrol"> Oculte los gráficos superpuestos de los vínculos que no hayan recibido ninguna visita.</span> </td> 
   <td colname="col3"> Esta casilla permite ocultar las superposiciones de los vínculos que no han recibido visitas para reducir el desorden en la interfaz. </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <span class="uicontrol"> Color de degradación/Color de burbuja</span> </td> 
   <td colname="col3">Seleccione los colores de una gama de colores para mostrar las clasificaciones de vínculos de superposición para las visualizaciones de superposición <span class="uicontrol">Degradación</span> o <span class="uicontrol">Burbujas</span>. </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <span class="uicontrol"> Degradación de color según</span> </td> 
   <td colname="col3"> 
    <ul id="ul_1B5C2A44A9EB465D8B8E9AD91AF79D69"> 
     <li id="li_C983CB68B90B492BB0774254292B5961"> <span class="uicontrol"> Principales 30 rangos</span>: la intensidad del color se normaliza para los 30 primeros valores. </li> 
     <li id="li_1E83431C8C734AB0BC82B5A66AED1189"> <span class="uicontrol"> Valor métrico absoluto</span>: la intensidad del color es una función del valor absoluto de la métrica. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <span class="uicontrol"> Transparencia de degradación</span> </td> 
   <td colname="col3">Seleccione el nivel de transparencia para las superposiciones de degradado. <p>Este ajuste no afecta a las superposiciones de burbujas. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Configuración de las superposiciones en el modo Activo {#section_D30F6E62FB5D404090B588F396A460AF}

![](assets/settings_live.png)

| Configuración | Descripción |
|---|---|
| **[!UICONTROL Mostrar los primeros]** | Seleccione el número de vínculos que quiere mostrar (pueden ser todos) y los **[!UICONTROL Ganadores]** o **[!UICONTROL Perdedores]** (o ambos) que se verán como superposiciones. |
| **[!UICONTROL Excluir inferior (%)]** | Seleccione esta opción para eliminar los vínculos ganadores y perdedores con datos dispersos. Filtre el porcentaje inferior de cambios de vínculo para ver solo los vínculos que tengan datos suficientes para mostrar ganancias o pérdidas significativas. El porcentaje se calcula basándose en el número de vínculos que haya en la página. Por ejemplo, si se filtra el 10 % inferior de una lista de 200 vínculos, se filtrarían los últimos 20 vínculos. |
| **[!UICONTROL Actualizar datos automáticamente]** | Permite decidir si los datos de Analytics que se ven en la interfaz deberían actualizarse automáticamente o no cuando se calcula un período nuevo. |
| **[!UICONTROL Período de actualización automática]** | Cuando se activa esta opción, la página web se actualiza con cada recuperación de datos nuevos para que los vínculos de la página se puedan sincronizar mejor con los datos recopilados. |

## Otra configuración {#section_697A12F099494D699A4BF498598178C5}

![](assets/settings_other.png)

<table id="table_0F560236F8844FA0928CBB9C50D5ABEF"> 
 <tbody> 
  <tr> 
   <td colname="col1"> Report Suite </td> 
   <td colname="col2"> <p>Ahora, la lista de los grupos de informes a la que puede acceder no solo incluye los grupos que aparecen en la etiqueta Sitio web. Ahora puede sustituir el grupo de informes seleccionado (correspondiente a una de las etiquetas de la página) por otro grupo de informes. No hace falta que este nuevo grupo de informes esté vinculado a una etiqueta de la página. Si cambia el grupo de informes seleccionado en Configuración de Activity Map, el proceso de <span class="uicontrol">guardado</span> hará que todos los informes afectados de Analytics se actualicen. </p> <p> <p>Importante: Los grupos de informes virtuales solo son compatibles con el modo Estándar, no con el Activo. Si está en el modo Activo en un grupo de informes estándar pero selecciona un grupo de informes virtuales en este cuadro de diálogo, cuando haga clic en <span class="uicontrol">Aceptar</span> aquí aparecerá el modo Estándar. </p> </p> <p>Además, el control de calendario se reinicializará para adoptar el tipo de calendario que tenga el grupo de informes (gregoriano, minorista, personalizado...). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Idioma </td> 
   <td colname="col2"> La selección corresponde a los idiomas ofrecidos en Adobe Analytics. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Acerca de </td> 
   <td colname="col2"> Indica el nombre y número de versión de las aplicaciones. </td> 
  </tr> 
 </tbody> 
</table>

