---
description: Métricas que hacen referencia a la distancia horizontal o vertical de los datos únicamente en la ventana del navegador. Más específicamente, el navegador
title: Anchura y altura del navegador
topic: Metrics
uuid: 1c0d3ea9-e001-4152-9bfc-8fe6406bc755
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Anchura y altura del navegador

Métricas que hacen referencia a la distancia horizontal o vertical de los datos únicamente en la ventana del navegador. Más específicamente, el navegador

Adobe Analytics utiliza la altura y anchura del explorador únicamente desde la primera visita individual de una visita. El resto de los aciertos individuales no obtiene la atribución para la misma visita.
Las dimensiones de anchura y altura del navegador capturan valores parecidos, pero distintos a los del [tamaño de la pantalla del móvil](/help/components/c-variables/dimensionslist/reports-mobile.md#topic_D306EA4558194488AC47A45B9C570150).

Por ejemplo, cuando se dividen la anchura o la altura del navegador según la resolución móvil, hay que tener en cuenta estas distinciones:

* Las resoluciones de los dispositivos móviles son los valores físicos asociados al dispositivo. Por ejemplo, en Resoluciones de los dispositivos móviles, el Galaxy S8 aparecería como 2960 x 1440. La resolución del dispositivo móvil se recupera de un servicio de terceros después de haber identificado el dispositivo.
* En cambio, en los valores de anchura y altura del navegador, se muestran los valores de CSS (lógicos) de 740 x 360. Los valores del navegador se basan en los datos de Javascript/CSS.
* Para ver un breve debate al respecto, lea [este hilo](https://stackoverflow.com/questions/8785643/what-exactly-is-device-pixel-ratio).

