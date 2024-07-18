---
description: Puede ver datos del Document Cloud en Adobe Analytics
title: Configuración de creación de informes de Document Cloud
feature: Admin Tools
exl-id: eb58d011-c4b0-4c0c-9241-83b2bccc2c77
source-git-commit: bdd9473b0ac3bd77ffeff53a095876e21ca2f4d4
workflow-type: tm+mt
source-wordcount: '135'
ht-degree: 7%

---

# Configuración de creación de informes de Document Cloud

Puede configurar dimensiones y métricas específicas del PDF para que estén disponibles en Adobe Analytics.

## Componentes añadidos al activar la creación de informes de PDF

Cuando PDF Reporting está correctamente configurado, las siguientes dimensiones y métricas están disponibles en Adobe Analytics:

**Dimensiones:**

* Término de búsqueda del PDF

* Nivel de zoom del PDF

* Acción del PDF

* Número de página del PDF

* Nombre de archivo del PDF

**Métricas:**

* Vistas del PDF

* Vistas de página del PDF

* Descargas del PDF

* Búsqueda de PDF

* Marcadores de PDF utilizados

* PDF Copiar texto

* Impresión de PDF

## Habilitar la creación de informes de PDF en Adobe Analytics

1. Vaya a **[!UICONTROL Analytics]** > **[!UICONTROL Administración]** > **[!UICONTROL Grupos de informes]** > **`<select report suite>`** > **[!UICONTROL Editar configuración]** > **[!UICONTROL Administración de Document Cloud]** > [!UICONTROL **Informes de Document Cloud**].

1. En la página Administración de Adobe Document Cloud, seleccione [!UICONTROL **Habilitar informes de PDF**].

1. Para configurar Adobe Document Cloud para transmitir datos a Adobe Analytics, use [Adobe Document Cloud Javascript SDK](https://www.adobe.io/apis/documentcloud/dcsdk.html).
