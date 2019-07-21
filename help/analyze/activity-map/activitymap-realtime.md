---
description: El análisis de página en tiempo real (modo Activo) permite obtener resultados con una granularidad por minutos en tiempo real.
seo-description: El análisis de página en tiempo real (modo Activo) permite obtener resultados con una granularidad por minutos en tiempo real.
seo-title: Análisis de página en tiempo real (activo)
solution: Analytics
title: Análisis de página en tiempo real (activo)
topic: Activity Map
uuid: a 3 faa 9 bd -73 d 8-48 b 3-be 2 b-f 818 ed 7456 fb
translation-type: tm+mt
source-git-commit: 4e7a8bab956503093633deff0a64e8c7af2d5497

---


# Análisis de página en tiempo real (activo)

El análisis de página en tiempo real (modo Activo) permite obtener resultados con una granularidad por minutos en tiempo real.

Ahora, Activity Map muestra datos analíticos en incrementos de 1 a 15 minutos para supervisar la popularidad de los vínculos según las microtendencias de las páginas seleccionadas. Esto es especialmente importante para las empresas editoriales a la hora de realizar un seguimiento y responder al aumento o la reducción del interés por las historias, así como para supervisar el flujo del tráfico en tiempo real.

Como propietario del contenido del sitio, una de sus responsabilidades es saber cuándo promocionar y eliminar contenido para que la experiencia sea relevante constantemente. Los datos en tiempo real son el fundamento de esta responsabilidad. Si sabe cuáles son los vínculos y el contenido que lideran las tendencias en cada momento, puede actuar rápidamente y con seguridad para mantener a los lectores y clientes interesados en su marca.

![](assets/live_mode.png)

<!-- 

Describe what you can do with the feature: - what is the data shown? why do I see trend lines everywhere? how do I choose a period in the trend? what do the overlays represent in live mode? how do you compute the gainers and losers overlays? what is the auto update mode?

 -->

## Data latency as a result of A4T configuration {#section_806CE36354FC4C539A0DED9266A5C704}

Tras activar la integración de A4T en Adobe Target, experimentará otros 5-10 minutos de latencia en Adobe Analytics. Este aumento de la latencia permite almacenar los datos de Analytics y Target en la misma visita, lo que le permite desplegar las pruebas por página y por sección de sitio.

Este aumento se ve reflejado en todos los servicios y herramientas de Adobe Analytics, incluido el flujo en directo y los informes en tiempo real, y se aplica a estos escenarios:

* Para el flujo en directo, los informes en tiempo real, las solicitudes de la API y todos los datos actuales para las variables de tráfico, solo se retrasan las visitas con un ID de datos suplementario.
* Para los datos actuales en las métricas de conversión, los datos finalizados y las fuentes de datos, todas las visitas se retrasan de 5 a 7 minutos más.

Be aware that the latency increase starts after you implement the [Identity Service](https://marketing.adobe.com/resources/help/en_US/mcvid/), even if you have not fully implemented this integration.
