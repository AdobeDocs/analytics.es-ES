---
description: Puede ver datos de Document Cloud en Adobe Analytics
title: Configuración de creación de informes de Document Cloud
feature: Admin Tools
exl-id: eb58d011-c4b0-4c0c-9241-83b2bccc2c77
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '135'
ht-degree: 7%

---

# Configuración de creación de informes de Document Cloud

Puede configurar dimensiones y métricas específicas de PDF para que estén disponibles en Adobe Analytics.

## Componentes añadidos al habilitar los informes de PDF

Cuando los informes de PDF están correctamente configurados, las siguientes dimensiones y métricas están disponibles en Adobe Analytics:

**Dimensiones:**

* Término de búsqueda de PDF

* Nivel de zoom PDF

* Acción de PDF

* Número de página de PDF

* Nombre de archivo PDF

**Métricas:**

* Vistas de PDF

* Vistas de página de PDF

* Descargas de PDF

* Búsqueda de PDF

* Marcadores de PDF utilizados

* Texto de copia de PDF

* PDF Print

## Habilitar los informes de PDF en Adobe Analytics

1. Vaya a **[!UICONTROL Analytics]** > **[!UICONTROL Administración]** > **[!UICONTROL Grupos de informes]** > **`<select report suite>`** > **[!UICONTROL Editar configuración]** > **[!UICONTROL Administración de Document Cloud]** > [!UICONTROL **Informes de Document Cloud**].

1. En la página Administración de Adobe Document Cloud, seleccione [!UICONTROL **Habilitar informes de PDF**].

1. Para configurar Adobe Document Cloud para que transmita datos a Adobe Analytics, use [Adobe Document Cloud Javascript SDK](https://www.adobe.io/apis/documentcloud/dcsdk.html).
