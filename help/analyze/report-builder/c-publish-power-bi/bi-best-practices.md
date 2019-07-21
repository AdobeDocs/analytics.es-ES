---
description: 'null'
seo-description: 'null'
seo-title: Prácticas recomendadas
title: Prácticas recomendadas
uuid: 6 d 55 a 9 aa -030 e -4 e 4 d -963 c-ec 9 cc 38 e 1731
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Prácticas recomendadas

## Preservar referencias en visualizaciones de Power BI {#section_7ED14FE64D974681A57EB91EF1B47CB6}

Una vez que se crea una solicitud, esta siempre tendrá la misma referencia en Power BI. Sin embargo, si elimina una solicitud, la referencia la usará una solicitud nueva que cree para la misma dimensión.

Si elimina una solicitud en su libro, asegúrese de no tener ninguna visualización que apunte a ella en Power BI o, de lo contrario, se producirá un error en la visualización.

* Si es posible, no elimine solicitudes que haya creado en el Creador de informes
* Si elimina solicitudes en el Creador de informes, asegúrese de eliminar en Power BI la visualización correspondiente.
* Si no está seguro: elimine las solicitudes que ya no necesite y, a continuación, vuelva a publicar y vaya a Power BI para comprobar qué visualizaciones se han roto

