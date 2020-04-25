---
description: El análisis de página en tiempo real (modo Activo) permite obtener resultados con una granularidad por minutos en tiempo real.
title: Análisis de páginas en tiempo real (activo)
topic: Activity map
translation-type: tm+mt
source-git-commit: 713a73a1d57d93c579e0da58e464cecab3f9d773

---


# Análisis de páginas en tiempo real (modo Activo)

El análisis de página en tiempo real (modo Activo) permite obtener resultados con una granularidad por minutos en tiempo real.

El mapa de Actividad ahora muestra datos analíticos en incrementos de 1 minuto a 15 minutos para monitorear la popularidad del vínculo en base a las microtendencias de las páginas seleccionadas. Esto es especialmente importante para las empresas editoriales a la hora de realizar un seguimiento y responder al aumento o la reducción del interés por las historias, así como para supervisar el flujo del tráfico en tiempo real.

Como propietario del contenido del sitio, una de sus responsabilidades es saber cuándo promocionar y eliminar contenido para que la experiencia sea relevante constantemente. Los datos en tiempo real son el fundamento de esta responsabilidad. Si sabe cuáles son los vínculos y el contenido que lideran las tendencias en cada momento, puede actuar rápidamente y con seguridad para mantener a los lectores y clientes interesados en su marca.

![](assets/live_mode.png)

<!-- 

Describe what you can do with the feature: - what is the data shown? why do I see trend lines everywhere? how do I choose a period in the trend? what do the overlays represent in live mode? how do you compute the gainers and losers overlays? what is the auto update mode?

 -->

Si desea comprobar en el modo Activo qué elemento se hace clic principalmente:

1. Seleccione el período de tiempo en la línea de tendencia del modo **** activo de la barra de herramientas que desee analizar.
1. Haga clic en el icono &quot;Ojo&quot; en la barra de herramientas para acceder a la tabla de informes de vínculos.
1. Ordene la tabla mediante el vínculo.

## Latencia de datos como resultado de la configuración de A4T

After the [A4T integration](https://docs.adobe.com/content/help/es-ES/target/using/integrate/a4t/a4t.html) is enabled in Adobe Target, you will experience an additional 5-10 minutes of latency in Adobe Analytics. Este aumento de la latencia permite almacenar los datos de Analytics y Target en la misma visita, lo que le permite desplegar las pruebas por página y por sección de sitio.

Este aumento se ve reflejado en todos los servicios y herramientas de Adobe Analytics, incluido el flujo en directo y los informes en tiempo real, y se aplica a estos escenarios:

* Para el flujo en directo, los informes en tiempo real, las solicitudes de la API y todos los datos actuales para las variables de tráfico, solo se retrasan las visitas con un ID de datos suplementario.
* Para los datos actuales en las métricas de conversión, los datos finalizados y las fuentes de datos, todas las visitas se retrasan de 5 a 7 minutos más.

Tenga en cuenta que el aumento de la latencia se da después de implementar el [Servicio de identidad](https://marketing.adobe.com/resources/help/es_ES/mcvid/), incluso aunque no haya implementado correctamente esta integración.

Más información [aquí](/help/analyze/activity-map/activitymap-standard-live.md).