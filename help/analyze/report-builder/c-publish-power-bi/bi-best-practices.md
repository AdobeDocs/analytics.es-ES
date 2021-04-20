---
description: Prácticas recomendadas de Power BI.
title: Prácticas recomendadas
uuid: 6d55a9aa-030e-4e4d-963c-ec9cc38e1731
feature: Report Builder
role: Business Practitioner, Administrator
translation-type: tm+mt
source-git-commit: 894ee7a8f761f7aa2590e06708be82e7ecfa3f6d
workflow-type: tm+mt
source-wordcount: '143'
ht-degree: 95%

---


# Prácticas recomendadas

## Preservar referencias en visualizaciones de Power BI {#section_7ED14FE64D974681A57EB91EF1B47CB6}

Una vez que se crea una solicitud, esta siempre tendrá la misma referencia en Power BI. Sin embargo, si elimina una solicitud, la referencia la usará una solicitud nueva que cree para la misma dimensión.

Si elimina una solicitud en su libro, asegúrese de no tener ninguna visualización que apunte a ella en Power BI o, de lo contrario, se producirá un error en la visualización.

* Si es posible, no elimine solicitudes que haya creado en Report Builder
* Si elimina solicitudes en Report Builder, asegúrese de eliminar en Power BI la visualización correspondiente.
* Si no está seguro: elimine las solicitudes que ya no necesite y, a continuación, vuelva a publicar y vaya a Power BI para comprobar qué visualizaciones se han roto

