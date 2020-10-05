---
title: Dominio
description: La organización o el ISP que el visitante utiliza para acceder a Internet.
translation-type: tm+mt
source-git-commit: c2d371cee2821360ab87240b1a81695798af4f9f
workflow-type: tm+mt
source-wordcount: '124'
ht-degree: 41%

---


# Dominio

La dimensión &#39;Dominio&#39; informa los puntos de acceso que los visitantes utilizan para acceder a Internet.

## Rellene esta dimensión con datos

Adobe se asocia con [Digital Element](https://www.digitalelement.com/?lang=es) para determinar el dominio del punto de acceso. Se utilizan varios métodos, incluida la búsqueda DNS inversa, para determinar el dominio del punto de acceso. No requiere ninguna configuración y no tiene una variable que rellenar. Funciona de forma predeterminada con todas las implementaciones de AppMeasurement.

## Elementos de dimensión

Los elementos de dimensión de ejemplo incluyen `comcast.net`, `rr.com`, `sbcglobal.net` y `amazonaws.com`. Tenga en cuenta que estos dominios son puntos de acceso, y no necesariamente el dominio que representa a un ISP u organización.

Los valores de Dimension `None` significan que el propietario de la dirección IP del punto de acceso no proporcionó un dominio.
