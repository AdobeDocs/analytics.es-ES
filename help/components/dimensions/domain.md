---
title: Dominio
description: La organización o el ISP que el visitante utiliza para acceder a Internet.
feature: Dimensions
exl-id: 292dc256-e9e7-47be-8586-774f1c047011
source-git-commit: e32821dd3f30404166554b8437c508172e4764e5
workflow-type: tm+mt
source-wordcount: '134'
ht-degree: 52%

---

# Dominio

La dimensión [Dominio](overview.md) indica los puntos de acceso que los visitantes utilizan para acceder a Internet.

## Rellene esta dimensión con datos

Adobe está asociado con [Digital Element](https://www.digitalelement.com/es/) para determinar el dominio del punto de acceso. Para determinar el dominio del punto de acceso se utilizan varios métodos, incluida la búsqueda inversa de DNS. No requiere ninguna configuración y no tiene una variable que rellenar.

* Para implementaciones de AppMeasurement, esta dimensión funciona de forma predeterminada.
* Para implementaciones de Web SDK, habilita [!UICONTROL Búsqueda de red] al [configurar una secuencia de datos](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=es).

## Elementos de dimensión

Los elementos de dimensión de ejemplo incluyen `comcast.net`, `rr.com`, `sbcglobal.net` y `amazonaws.com`. Estos dominios son puntos de acceso y no necesariamente el dominio que representa a un ISP u organización.

Los valores de dimensión de `None` significan que el propietario de la dirección IP del punto de acceso no proporcionó un dominio.
