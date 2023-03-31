---
description: Los filtros de URL internos identifican los referentes que se consideran internos del sitio. Ayudan a los informes de fuentes de tráfico a rellenar los datos y son útiles para filtrar el tráfico interno.
title: Filtros URL internos
feature: Admin Tools
uuid: 70868edb-208d-4dad-9401-70967468d40c
exl-id: fa387da2-e9be-47c0-9c4e-edd75af1f05a
source-git-commit: 2beb4cd38fc8b48e2b34468a4570f7168aeacb78
workflow-type: tm+mt
source-wordcount: '274'
ht-degree: 30%

---


# Filtros URL internos

Los filtros de URL internos permiten identificar los referentes que se consideran internos del sitio. Ayudan a los informes de fuentes de tráfico a rellenar los datos y son útiles para filtrar el tráfico interno.

El referente, o la página referente, suele ser la página desde la que el visitante entró al sitio. Para evitar la distorsión de los datos, puede filtrar las páginas internas para que no se consideren referentes. Los informes excluyen a los referentes filtrados del  Dimensión [Remitentes del reenvío](/help/components/dimensions/referrer.md), dimensión [Dominios de referencia](/help/components/dimensions/referring-domain.md) y otras dimensiones de fuentes de tráfico.

## Ver filtros de URL internos existentes

>[!NOTE]
>
>Algunos grupos de informes tienen un filtro de URL interno de un punto (.) configurado de forma predeterminada. Cuando existe este filtro, todo el tráfico se clasifica como interno. Los informes de referentes no funcionarán hasta el periodo (.) se elimina.

Para comprobar qué filtros de URL internos están configurados para un grupo de informes: <!-- I don't see the period in my instance? Is the following information valid? "To avoid this, remove the rule listing a period (.) as a filter, and add your own site. The reason why a period is the default internal URL filter is to allow data to be collected in the Pages report. If hits do not match internal URL filters, all pages come up as Other. A period is always somewhere in the URL, which guarantees the Pages report is populated.")-->

1. Select **[!UICONTROL Administrador]** > **[!UICONTROL Grupos de informes]** para acceder al Administrador de grupos de informes.

1. Seleccione el grupo de informes en el que desea comprobar qué filtros de URL internos están configurados y, a continuación, seleccione **[!UICONTROL Editar configuración]** > **[!UICONTROL General]** > **[!UICONTROL Filtros URL internos]**.

   Todos los filtros existentes se enumeran en la sección [!UICONTROL **Filtros actuales**] para obtener más información.

## Añadir un filtro de URL interno a un grupo de informes

1. Select **[!UICONTROL Administrador]** > **[!UICONTROL Grupos de informes]** para acceder al Administrador de grupos de informes.

1. Seleccione el grupo de informes al que desee agregar un filtro de URL interno y, a continuación, seleccione **[!UICONTROL Editar configuración]** > **[!UICONTROL General]** > **[!UICONTROL Filtros URL internos]**.

1. En la sección Agregar filtro , en el campo proporcionado, empiece a escribir la dirección URL de la página que desea filtrar y, a continuación, seleccione [!UICONTROL **Agregar**].

   La dirección URL que ha agregado ahora es visible en el [!UICONTROL **Filtros actuales**] para obtener más información.
