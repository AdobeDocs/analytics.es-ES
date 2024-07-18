---
description: Los filtros de URL internos identifican los referentes que se consideran internos del sitio. Ayudan a los informes de fuentes de tráfico a rellenar los datos y son útiles para filtrar el tráfico interno.
title: Filtros URL internos
feature: Admin Tools
uuid: 70868edb-208d-4dad-9401-70967468d40c
exl-id: fa387da2-e9be-47c0-9c4e-edd75af1f05a
source-git-commit: 5c2643a143e5c8e17fcf11cfa2da81183bc5c39a
workflow-type: tm+mt
source-wordcount: '221'
ht-degree: 31%

---


# Filtros URL internos

Los filtros de URL internos permiten identificar los referentes que se consideran internos del sitio. Ayudan a los informes de fuentes de tráfico a rellenar los datos y son útiles para filtrar el tráfico interno.

**[!UICONTROL Analytics]** > **[!UICONTROL Administrador]** > **[!UICONTROL Grupos de informes]** > **[!UICONTROL Editar configuración]** > **[!UICONTROL General]** > **[!UICONTROL Filtros URL internos]**

El referente, o la página referente, suele ser la página desde la que el visitante entró al sitio. Para evitar la distorsión de los datos, puede filtrar las páginas internas para que no se consideren referentes. Los Dimension que dependen de los filtros de URL internos incluyen [Referente](/help/components/dimensions/referrer.md), [Dominio de referencia](/help/components/dimensions/referring-domain.md), [Canales de marketing](/help/components/dimensions/marketing-channel.md) y otras dimensiones de fuentes de tráfico.

[Las reglas de procesamiento del canal de marketing](../marketing-channels/c-rules.md) proporcionan &quot;[!UICONTROL coinciden con los filtros de URL internos]&quot; como posibles criterios de regla.

>[!IMPORTANT]
>
>Algunos grupos de informes tienen un filtro de dirección URL interno de un período (`.`) configurado de manera predeterminada. Cuando existe este filtro, todo el tráfico se clasifica como interno. Los informes de referentes no funcionarán hasta que se elimine este filtro y se sustituya por uno o varios dominios internos deseados.

* Ver todos los filtros existentes en la sección **[!UICONTROL Filtros actuales]**.
* Agregue un filtro usando el cuadro de texto debajo de la sección **[!UICONTROL Agregar filtro]** y luego haga clic en **[!UICONTROL Agregar]**.

Los filtros funcionan usando la lógica **contains** en la dirección URL completa. El Adobe recomienda omitir el protocolo (`https://`) y los subdominios al crear los filtros, a menos que se desee el tráfico de subdominios independientes como tráfico externo.
