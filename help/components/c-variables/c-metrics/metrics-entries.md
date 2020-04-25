---
description: Entradas representa el número de veces que un valor determinado se captura como el primero de una visita. Entradas solo tiene lugar una vez por visita. No obstante, no tiene por qué ser necesariamente la primera visita si no se ha definido la variable.
title: Entradas
topic: Metrics
uuid: c4608b66-b70c-4e98-b7c6-9be5fbe4ec9c
translation-type: tm+mt
source-git-commit: e6aaf2754c6a5c33fbe3e093b4d7ca5a375c41e7

---


# Entradas

&quot;Entradas&quot; representa el número de veces que un valor determinado se captura como el primer valor de una visita. Entradas solo tiene lugar una vez por visita. No obstante, no tiene por qué ser necesariamente la primera visita si no se ha definido la variable.

En Analysis Workspace, a partir de marzo de 2020, hemos cambiado la forma en que el valor &quot;Ninguno&quot; interactúa con las entradas y salidas.  Dado que ahora puede activar y desactivar &quot;Nones&quot; en el espacio de trabajo de Análisis, se aplica &quot;Ninguno&quot; después de la entrada o salida, mientras que (para evars) solía aplicarse antes.  Por ejemplo: supongamos que la primera visita individual de una visita no tiene valor para, por ejemplo, eVar21, pero la segunda visita sí. En Reports &amp; Analytics, se mostrará como &quot;No especificado&quot; para la entrada, pero en Analysis Workspace, se mostrará como el valor de la segunda visita.

Las páginas de entrada tienen un alcance de desglose de visitas, lo que significa que persisten a través de todas las visitas. Consulte [Contenedores de segmentación y de desglose](https://marketing.adobe.com/resources/help/en_US/sc/user/c_Breakdown_and_segmentation_containers.html) para obtener más información.
