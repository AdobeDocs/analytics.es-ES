---
title: Tipos de sistemas operativos
description: El sistema operativo independientemente de la versión.
feature: Dimensions
exl-id: 0afd5261-98e8-4247-865a-1b8844c53ff4
source-git-commit: e32821dd3f30404166554b8437c508172e4764e5
workflow-type: tm+mt
source-wordcount: '130'
ht-degree: 53%

---

# Tipos de sistemas operativos

La [dimensión](overview.md) &quot;Tipos de sistemas operativos&quot; muestra el sistema operativo global que el visitante utilizó, independientemente de versiones específicas. Esta dimensión es útil para comprender no solo qué sistema operativo y versión específicos son los más comunes, sino también qué plataforma de sistema operativo utilizan los visitantes habituales.

## Rellene esta dimensión con datos

Esta dimensión hace referencia a una tabla de búsqueda interna de Adobe. El valor de búsqueda se basa en el encabezado HTTP `User-Agent` de las solicitudes de imagen. Adobe se asocia con [DeviceAtlas](https://deviceatlas.com/) para mantener búsquedas entre el agente de usuario y el tipo de sistema operativo.

* Para implementaciones de AppMeasurement, esta dimensión funciona de forma predeterminada.
* Para implementaciones de Web SDK, habilite [!UICONTROL Búsqueda de dispositivos] al [configurar una secuencia de datos](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=es).

## Elementos de dimensión

Los elementos de Dimension incluyen el tipo de sistema operativo utilizado. Los ejemplos incluyen `"Microsoft Windows"`, `"Apple Macintosh"`, `"Google Android"` y `"Apple iOS"`.
