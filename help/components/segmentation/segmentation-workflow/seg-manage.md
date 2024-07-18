---
description: El Administrador de segmentos ofrece numerosas maneras de conservar los segmentos, como compartir, filtrar, etiquetar, aprobar, copiar, eliminar y marcar como favoritos.
title: Administración de segmentos (Administrador de segmentos)
feature: Segmentation
exl-id: be182a55-23cb-415f-a7d0-3c1efeead1a1
source-git-commit: df9c6d59ef5f5c43d0e1ef822bd23bc0e09ff20e
workflow-type: tm+mt
source-wordcount: '749'
ht-degree: 32%

---

# Administrador de segmentos

El Administrador de segmentos ofrece numerosas maneras de conservar los segmentos, como compartir, filtrar, etiquetar, aprobar, copiar, eliminar y marcar como favoritos.

El Administrador de segmentos de Analytics le muestra todos los segmentos que posee y que han compartido con usted. Los usuarios con nivel de administrador pueden ver todos los segmentos de la organización. Esta introducción presenta la interfaz de usuario y las capacidades del Administrador de segmentos.

![Administrador de segmentos](assets/segments-manager.png)

## Acceso al Administrador de segmentos

1. En Adobe Analytics, seleccione la ficha **[!UICONTROL Componentes]** y, a continuación, seleccione **[!UICONTROL Segmentos]**.

   O

   En un informe existente, seleccione el icono Segmentos ![](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Segmentation_18_N.svg) en el panel de navegación izquierdo y, a continuación, seleccione **[!UICONTROL Administrar]**.

## Acciones disponibles en el Administrador de segmentos

En el Administrador de segmentos, puede:

* [Filtrar segmentos](/help/components/segmentation/segmentation-workflow/t-seg-filter.md)

* [Marcar segmentos como favoritos](/help/components/segmentation/segmentation-workflow/t-seg-favorite.md)

* [Aprobar segmentos](/help/components/segmentation/segmentation-workflow/seg-approve.md)

* [Etiquetar segmentos](/help/components/segmentation/segmentation-workflow/seg-tag.md)

* [Compartir segmentos](/help/components/segmentation/segmentation-workflow/t-seg-share.md)

* Exporte un segmento a un archivo CSV.

* [Copiar segmentos](/help/components/segmentation/segmentation-workflow/seg-copy.md)

* [Eliminar segmentos](/help/components/segmentation/segmentation-workflow/seg-delete.md)

## Configuración de columnas

Puede configurar la información mostrada para cada segmento en el Administrador de segmentos configurando las columnas que se muestran.

Para configurar las columnas visibles en el Administrador de segmentos:

1. En Adobe Analytics, seleccione la ficha **[!UICONTROL Componentes]** y, a continuación, seleccione **[!UICONTROL Segmentos]**.

1. En el Administrador de segmentos, seleccione el icono **Personalizar columnas** ![Personalizar icono de columnas](assets/customize-columns-icon.png) y, a continuación, seleccione las columnas que desee que se muestren en el Administrador de segmentos.

   Las columnas disponibles son las siguientes:

   | Título de columna | Descripción |
   |---|---|
   | Título y descripción | Estos valores se proporcionan en el Generador de segmentos. Para editar el título y la descripción, seleccione el vínculo del título para abrir el Generador de segmentos. |
   | Favoritos | Muestra iconos de estrella junto a cada segmento, lo que le permite marcar segmentos como favoritos. Para obtener más información, consulte [Marcar segmentos como favoritos](/help/components/segmentation/segmentation-workflow/t-seg-favorite.md). |
   | Grupos de informes | Esta columna indica en qué grupo de informes se guardó por última vez el segmento. |
   | Propietario | Indica a quién pertenece el segmento. Si no es el administrador, solo podrá ver los segmentos que le pertenecen o que compartieron con usted. |
   | Etiquetas (la columna no aparece porque no está marcada en el selector de columnas) | Etiquetas que se aplicaron al segmento, tanto por su parte como por parte de las personas que compartieron el segmento con usted. |
   | Compartido con | Enumera las personas o grupos (solo administrador) o todos (solo administrador) con los que compartió el segmento. <p>Cuando usted o con usted comparten un segmento, aparece un icono de uso compartido junto al nombre del segmento.</p> |
   | Fecha de modificación | Muestra la última fecha de modificación del segmento. |
   | Utilizado en | Muestra cuántos componentes se están utilizando en ese momento en el segmento. <p>Por ejemplo, si el segmento se está utilizando en 40 proyectos y 2 alertas, el valor de esta columna se muestra como [!UICONTROL **42 componentes**].</p> <p>Seleccione el valor de esta columna para ver el desglose de dónde se está utilizando el segmento (por ejemplo, [!UICONTROL **Proyectos (40)**], [!UICONTROL **Alertas (2)**]).</p><p>Los segmentos se pueden utilizar en cualquiera de los siguientes tipos de componentes:</p> <ul><li>Alertas</li><li>Proyectos</li><li>Proyectos programados</li><li>Métricas calculadas </li></ul><p>Esta información puede ayudarle a determinar si un componente es valioso para los usuarios de su organización, dónde se utiliza y si debe eliminarse o modificarse.</p><p>Tenga en cuenta lo siguiente cuando vea esta columna:</p><ul><li>Esta información no incluye el uso de la API, el Report Builder o la Data Warehouse.</li><li>La columna [!UICONTROL **Utilizada en**] no se muestra de manera predeterminada. [Configure columnas](#configure-columns) para mostrarlas.</li><li>Si no hay datos en esta columna para un componente determinado pero tiene una fecha de [!UICONTROL **Último uso**], es posible que el componente se haya utilizado en un análisis sin que se haya guardado.</li><li>Esta información solo está disponible para los administradores del sistema.</li></ul><p>Puede usar el [Diccionario de datos](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md) junto con esta información para ayudarle a realizar un seguimiento y comprender mejor cómo se utilizan los componentes en su organización.</p> |
   | Último uso | Muestra la fecha en la que se utilizó por última vez el segmento en cualquiera de los siguientes tipos de componentes: <ul><li>Alertas</li><li>Métricas calculadas </li><li>Proyectos</li><li>Proyectos programados</li><li>Segmentos </li></ul> <p>Esta información puede ayudarle a determinar si un componente es valioso para los usuarios de su organización, dónde se utiliza y si debe eliminarse o modificarse.</p><p>Tenga en cuenta lo siguiente cuando vea esta columna:</p><ul><li>Esta información no incluye el uso de la API, el Report Builder o la Data Warehouse.</li><li>Para algunos componentes, es posible que esta columna no contenga datos si el componente se utilizó por última vez antes de septiembre de 2023.</li><li>Esta información solo está disponible para los administradores del sistema.</li></ul><p>Puede usar el [Diccionario de datos](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md) junto con esta información para ayudarle a realizar un seguimiento y comprender mejor cómo se utilizan los componentes en su organización. |

   {style="table-layout:auto"}

## Vídeo explicativo {#section_B3C5DA22DC5248DBA17C56E03DA2D4F2}

En este [vídeo de Adobe Analytics](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/components/segmentation/segment-management-and-sharing.html?lang=es) se proporciona una breve descripción sobre cómo utilizar el administrador de segmentos.


