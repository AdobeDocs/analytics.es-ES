---
description: Prácticas recomendadas de Power BI.
title: Prácticas recomendadas
feature: Report Builder
role: User, Admin
exl-id: 2d9447f4-77ac-465b-af93-206dc3ea80f7
source-git-commit: 12d048b42c6a61e03dbbe73acb9d34df3e37693c
workflow-type: tm+mt
source-wordcount: '139'
ht-degree: 100%

---

# Prácticas recomendadas

## Conservar referencias en visualizaciones de Power BI

Una vez que se crea una solicitud, esta siempre tendrá la misma referencia en Power BI. Sin embargo, si elimina una solicitud, la referencia la usará una solicitud nueva que cree para la misma dimensión.

Si elimina una solicitud en su libro, asegúrese de no tener ninguna visualización que apunte a ella en Power BI o, de lo contrario, se producirá un error en la visualización.

* Si es posible, no elimine solicitudes que haya creado en Report Builder
* Si elimina solicitudes en Report Builder, asegúrese de eliminar en Power BI la visualización correspondiente.
* Si no está seguro: elimine las solicitudes que ya no necesite y, a continuación, vuelva a publicar y vaya a Power BI para comprobar qué visualizaciones se han roto
