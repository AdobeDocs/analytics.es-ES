---
title: Dominio
description: La organización o el ISP que el visitante utiliza para acceder a Internet.
exl-id: 292dc256-e9e7-47be-8586-774f1c047011
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '124'
ht-degree: 100%

---

# Dominio

La dimensión “Dominio” indica los puntos de acceso que los visitantes utilizan para acceder a Internet.

## Rellene esta dimensión con datos

Adobe está asociado con [Digital Element](https://www.digitalelement.com/es) para determinar el dominio del punto de acceso. Para determinar el dominio del punto de acceso se utilizan varios métodos, incluida la búsqueda inversa de DNS. No requiere ninguna configuración y no tiene una variable que rellenar. Funciona de forma predeterminada con todas las implementaciones de AppMeasurement.

## Elementos de dimensión

Los elementos de dimensión de ejemplo incluyen `comcast.net`, `rr.com`, `sbcglobal.net` y `amazonaws.com`. Tenga en cuenta que estos dominios son puntos de acceso y no necesariamente el dominio que representa a un ISP u organización.

Los valores de dimensión de `None` significan que el propietario de la dirección IP del punto de acceso no proporcionó un dominio.
