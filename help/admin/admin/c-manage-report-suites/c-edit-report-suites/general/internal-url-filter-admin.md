---
description: Los filtros de URL internos identifican los referentes que se consideran internos del sitio. Ayudan a los informes de fuentes de tráfico a rellenar los datos y son útiles para filtrar el tráfico interno.
title: Filtros URL internos
feature: Admin Tools
uuid: 70868edb-208d-4dad-9401-70967468d40c
exl-id: fa387da2-e9be-47c0-9c4e-edd75af1f05a
source-git-commit: 71ff81a0ae67c6f4cc9a8df567e27223cc63f18c
workflow-type: tm+mt
source-wordcount: '212'
ht-degree: 100%

---


# Filtros URL internos

Los filtros de URL internos identifican los referentes que se consideran internos del sitio. Ayudan a los informes de fuentes de tráfico a rellenar los datos y son útiles para filtrar el tráfico interno.

**[!UICONTROL Administrador]** > **[!UICONTROL Grupos de informes]** > **[!UICONTROL Editar configuración]** > **[!UICONTROL General]** > **[!UICONTROL Filtros URL internos]**

El referente, o la página referente, suele ser la página desde la que el visitante entró al sitio. Para evitar la distorsión de los datos, puede filtrar las páginas internas para que no se consideren referentes. Los informes excluyen a los referentes filtrados del  Dimensión [Remitentes del reenvío](/help/components/dimensions/referrer.md), dimensión [Dominios de referencia](/help/components/dimensions/referring-domain.md) y otras dimensiones de fuentes de tráfico.

La razón más habitual por la cual las fuentes de tráfico no rellenan los datos es que la lista de filtros de URL internos no está definida. Para comprobar qué filtros de URL internos se han configurado en un grupo de informes, siga estos pasos. Para evitarlo, quite la regla en la que se muestra un punto (.) como un filtro y agregue su propio sitio.

El motivo por el cual un punto es el filtro de URL interno predeterminado es permitir que se recopilen los datos en el informe Páginas. Si las visitas no coinciden con los filtros de URL internos, todas las páginas aparecerán como Otro. En alguna parte de la URL siempre hay un punto, lo cual garantiza que se rellene el informe Páginas.
