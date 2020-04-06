---
description: Muestra las métricas basadas en si el dispositivo tiene JavaScript habilitado, deshabilitado o si se cuenta como "no identificado".
title: Asistencia técnica de JavaScript
topic: Reports
uuid: 7b95001a-cd35-478a-8b24-54d30666110d
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Asistencia técnica de JavaScript

Muestra las métricas basadas en si el dispositivo tiene JavaScript habilitado, deshabilitado o si se cuenta como &quot;no identificado&quot;.

>[!NOTE] A principios de noviembre de 2016, planeamos quitar la restricción donde JavaScript siempre se enumera como *`disabled / unidentified`* para dispositivos móviles.

El informe JavaScript corresponde a la columna javascript de los datos sin procesar.

javascript es un campo de nivel de visita, por lo que mantiene el valor de la primera visita individual de la visita. La columna javascript se basa en el primer valor presente en la columna j_jscript (como visit_remitente del reenvío solo persistirá el primer remitente del reenvío de la visita).

j_jscript se rellena desde el parámetro j de la solicitud de imagen de Adobe Analytics.

Vea el siguiente ejemplo:

| Acción | j_jscript | javascript |
|---|---|---|
| 1 |  | 0 |
| 2 | 1.6 | 0 |
| 3 | 1.6 | 0 |

Como resultado, no importa si se ha especificado una versión de javascript en algún momento de la visita; siempre se mostrará como no Javascript porque la primera visita no contenía ningún valor para j_jscript.
