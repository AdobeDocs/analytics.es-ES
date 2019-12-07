---
description: Muestra las métricas basadas en si el dispositivo tiene JavaScript habilitado, deshabilitado o si se cuenta como "no identificado".
title: Asistencia técnica de JavaScript
topic: Reports
uuid: 7b95001a-cd35-478a-8b24-54d30666110d
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Asistencia técnica de JavaScript

Muestra las métricas basadas en si el dispositivo tiene JavaScript habilitado, deshabilitado o si se cuenta como "no identificado".

> [!NOTE] A principios de noviembre de 2016, planeamos quitar la restricción donde JavaScript siempre se enumera como *`disabled / unidentified`* para dispositivos móviles.

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
