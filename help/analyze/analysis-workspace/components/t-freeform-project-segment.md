---
description: 'null'
seo-description: 'null'
seo-title: Segmentos
title: Segmentos
uuid: 677 f 6030-5 b 3 e -4 dfa-bb 79-9 f 27 f 3382 fb 1
translation-type: tm+mt
source-git-commit: 07b18333144f992031dca5a5d8838206fa735cb5

---


# Segmentos {#topic_DC2917A2E8FD4B62816572F3F6EDA58A}

## Segment rail {#section_3B07D458C43E42FDAF242BB3ACAF3E90}

El carril del segmento en el menú Componentes muestra los segmentos así como las plantillas de segmentos, como indican estos iconos:

![](assets/segment_icons.png)

[Uso de segmentos en Analysis Workspace en YouTube](https://www.youtube.com/watch?v=QlUCdQDnni4)(6:46)

## Crear segmentos {#section_693CFADA668B4542B982446C2B4CF0F5}

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

| Acción | Descripción |
|--- |--- |
| Crear segmento de selección | Cree un segmento en línea. Seleccione filas, haga clic con el botón secundario en la selección y cree un segmento en línea. Este segmento se aplica solamente al proyecto abierto y no se guarda como segmento de Analytics. 1. Seleccione filas. 2. Haga clic con el botón derecho en la selección. 3. Click *Create segment from selection*. |
| Componentes &gt; Nuevo segmento | Se abre el Generador de segmentos. See [Segment Builder](https://docs.adobe.com/content/help/en/analytics/components/segmentation/segmentation-workflow/seg-build.html) for more information about segmentation. |
| Compartir &gt; Compartir proyecto o Compartir &gt; Depurar datos de proyectos | In [Curate and Share](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/curate-share/curate.html#concept_4A9726927E7C44AFA260E2BB2721AFC6), learn how segments that you apply to the project are available in shared analysis for the recipient. |
| Uso de segmentos como dimensiones | Vídeo: [Uso de segmentos como dimensiones en Analysis Workspace](https://www.youtube.com/watch?v=WmSdReKTWto&list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS&index=39) |
