---
description: 'null'
seo-description: 'null'
seo-title: Segmentos
title: Segmentos
uuid: 677 f 6030-5 b 3 e -4 dfa-bb 79-9 f 27 f 3382 fb 1
translation-type: tm+mt
source-git-commit: f5f5b294f503911108e1693b7c6cd128bee659c6

---


# Segmentos {#topic_DC2917A2E8FD4B62816572F3F6EDA58A}

## Segment rail {#section_3B07D458C43E42FDAF242BB3ACAF3E90}

El carril del segmento en el menú Componentes muestra los segmentos así como las plantillas de segmentos, como indican estos iconos:

![](assets/segment_icons.png)

[Uso de segmentos en Analysis Workspace en YouTube](https://www.youtube.com/watch?v=QlUCdQDnni4)(6:46)

## Create segments {#section_693CFADA668B4542B982446C2B4CF0F5}

Puede crear segmentos instantáneos soltando cualquier tipo de componente (dimensión, elemento de dimensión, evento, métrica, segmento, plantilla de segmento, intervalo de fechas) en la zona de colocación de segmentos en la parte superior de un panel.

Los tipos de componente se convierten automáticamente en segmentos. También puede hacer clic en el signo “+” en el cuadro de colocación Agregar segmento.

Tenga en cuenta que:

* **No puede** soltar los siguientes tipos de componentes en la zona de segmento: métricas calculadas y dimensiones/métricas desde las que no se pueden crear segmentos.
* Para las dimensiones y eventos completos, Analysis Workspace crea segmentos de visita del tipo “existe”. Ejemplos: “Visita donde existe eVar1” o “Visita donde existe evento1”.
* Si se suelta "sin especificar" o "ninguno" en la zona de colocación de segmentos, se convierte automáticamente en un segmento "no existe" para que se trate correctamente en la segmentación.

![](assets/segment-dropzone.png)

>[!NOTE]
>
>Los segmentos creados de esta forma son internos al proyecto.

Puede convertir estos segmentos en públicos (globales) siguiendo estos pasos:

1. Sitúese sobre el segmento de la zona de colocación y haga clic en el icono “i”.
1. En el panel de información que aparece, haga clic en **[!UICONTROL Convertir en público]**.

   ![](assets/segment-info.png)

## Other methods for applying segments {#section_10FF2E309BA84618990EA5B473015894}

Existen varios métodos más para aplicar segmentos a un proyecto improvisado.

<table id="table_45B3839D70674430AF3AC5AA3134F825"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Acción </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Crear segmento de selección </p> </td> 
   <td colname="col2"> <p>Cree un segmento en línea. Seleccione filas, haga clic con el botón secundario en la selección y cree un segmento en línea. Este segmento se aplica solamente al proyecto abierto y no se guarda como segmento de Analytics. </p> <p> 
     <ol id="ol_1D1E661387354EBF992CC150915F642E"> 
      <li id="li_B96666FD426F4AEE8EAB61B2C00A07FB">Seleccione filas </li> 
      <li id="li_C2245B3EA81F4FAC88A33647922535AF">Haga clic con el botón secundario en la selección </li> 
      <li id="li_AB4F8988B9A84920ABA06A91094625F6">Haga clic en <span class="uicontrol">Crear segmento de selección</span>. </li> 
     </ol> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="uicontrol"> Componentes</span> &gt; <span class="uicontrol">Nuevo segmento</span> </td> 
   <td colname="col2"> <p>Se abre el <span class="wintitle">Generador de segmentos</span>. Consulte <a href="https://marketing.adobe.com/resources/help/en_US/analytics/segment/seg_build.html" format="https" scope="external">Creación de segmentos</a> para obtener más información acerca de la segmentación. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="ignoretag"><span class="uicontrol"> Compartir</span> &gt; <span class="uicontrol">Compartir proyecto</span></span> o </p> <p> <span class="ignoretag"><span class="uicontrol">Compartir</span> &gt; <span class="uicontrol">Depurar datos de proyectos</span></span> </p> </td> 
   <td colname="col2"> <p>In <a href="../../../analyze/analysis-workspace/curate-share/curate.md#concept_4A9726927E7C44AFA260E2BB2721AFC6" format="dita" scope="local"> Curate &amp; Share</a>, segments that you apply to the project are available in shared analysis for the recipient. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Uso de segmentos como dimensiones </p> </td> 
   <td colname="col2"> <p>Vídeo: <a href="https://www.youtube.com/watch?v=WmSdReKTWto&amp;list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS&amp;index=39" format="https" scope="external">Uso de segmentos como dimensiones en Analysis Workspace</a> </p> </td> 
  </tr> 
 </tbody> 
</table>

