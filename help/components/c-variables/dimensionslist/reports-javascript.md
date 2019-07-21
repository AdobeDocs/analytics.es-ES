---
description: Muestra las métricas basadas en si el dispositivo tiene JavaScript habilitado, deshabilitado o si se cuenta como "no identificado".
seo-description: Muestra las métricas basadas en si el dispositivo tiene JavaScript habilitado, deshabilitado o si se cuenta como "no identificado".
seo-title: Asistencia técnica de JavaScript
solution: Analytics
title: Asistencia técnica de JavaScript
topic: 'Informes '
uuid: 7 b 95001 a-cd 35-478 a -8 b 24-54 d 30666110 d
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Asistencia técnica de JavaScript

Muestra las métricas basadas en si el dispositivo tiene JavaScript habilitado, deshabilitado o si se cuenta como "no identificado".

>[!NOTE]
>
>In early November 2016, we plan to remove the restriction where JavaScript is always listed as *`disabled / unidentified`* for Mobile devices.

El informe JavaScript corresponde a la columna javascript de los datos sin procesar.

javascript es un campo de nivel de visita, así que conserva el valor de la primera visita. La columna javascript se basa en el primer valor presente en la columna j_jscript (como visit_referrer solo conserva el primer referente de la visita).

j_jscript se rellena a partir del parámetro j de la solicitud de imagen de Adobe Analytics.

A continuación verá un ejemplo:

| Visita individual | j_jscript | javascript |
|---|---|---|
| 1 |  | 0 |
| 2 | 1.6 | 0 |
| 3 | 1.6 | 0 |

Como resultado, no importa si había una versión de javascript especificada en algún momento de la visita, siempre aparecerá como no perteneciente a JavaScript, ya que la primera visita no contenía ningún valor para j_jscript.
