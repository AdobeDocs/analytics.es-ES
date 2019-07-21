---
description: Ofrece respuestas y sugerencias para resolución de problemas a algunas de las preguntas más frecuentes de Analytics.
keywords: Resolución de problemas de Analytics
seo-description: Ofrece respuestas y sugerencias para resolución de problemas a algunas de las preguntas más frecuentes de Analytics.
seo-title: Preguntas más frecuentes
title: Preguntas más frecuentes
uuid: 285 b 0 ea 4-aa 07-4 d 39-a 74 f -37 b 1 d 02 d 19 f 1
translation-type: tm+mt
source-git-commit: fd1e2f1789ed9c8c31c89f0e7b6b7b2dd3ee114d

---


# Preguntas más frecuentes

Proporciona respuestas y sugerencias para solucionar problemas a algunas de las preguntas de Analytics más frecuentes para Informes y análisis. For frequently asked implementation questions, see the [FAQ](../../implement/faq.md) in the Implement user guide.

**Mi cuenta se bloqueó; ¿Cómo puedo desbloquearlo?**

Para reactivar una cuenta, póngase en contacto con un administrador de su organización. See also [Troubleshoot login issues with Adobe Analytics](../../technotes/troubleshoot-login.md) in the Technotes user guide.

**¿Por qué veo un informe en blanco aunque sé que se recopilan datos?**

Hay varias cosas que comprobar para solucionar los problemas de los informes:

* Compruebe las métricas utilizadas: Algunos informes predeterminado a Ingresos en Informes y análisis. Asegúrese de que la métrica que está viendo sea relevante para el informe.
* Compruebe el intervalo de fechas: Los intervalos de fechas, especialmente aquellos más allá de la directiva de retención de datos de su organización, no devuelven datos. Compruebe que el intervalo de fechas esté correctamente configurado.
* Comprobar los filtros de URL internos: Algunos informes de fuentes de tráfico no funcionan hasta que se definen correctamente los filtros de URL internos.

**¿Por qué faltan algunos informes en el menú de navegación?**

Los informes que faltan en un menú generalmente proceden de permisos restringidos o personalización de menús. Póngase en contacto con un administrador de productos de su organización para asegurarse de que tiene acceso a todas las dimensiones y métricas necesarias, y de que la estructura de menú de un grupo de informes no se haya personalizado.

**¿Por qué se cortan algunos valores largos?**

Casi todas las variables de Adobe Analytics tienen un límite de caracteres. El nombre de página tiene un límite de 100 caracteres, mientras que las variables de conversión personalizadas (evars) tienen un límite de 255 caracteres. Adobe recomienda asegurarse de que los valores que envía a Adobe son concisos para evitar el truncamiento.

**¿Por qué veo un retraso importante en los informes?**

Los informes en tiempo real permiten que algunas métricas de tráfico estén disponibles en cuestión de minutos, mientras que la conversión y otros datos con mucho procesamiento suelen estar disponibles en un lapso de 30 a 90 minutos. A pesar de la solidez de la plataforma de Experience Cloud, hay algunas situaciones que pueden provocar retrasos en la generación de informes. Este retraso se denomina latencia. See [Latency](../../technotes/latency.md) in the Technotes user guide for more information.

**¿Por qué no puedo ver la versión del dispositivo en iphone?**

Los dispositivos Apple informan su versión firmware en la cadena del agente de usuario, no la versión del dispositivo. Es difícil determinar la versión del dispositivo iphone mediante la información disponible para Adobe Analytics. See [Comparing iPhone device versions](https://helpx.adobe.com/analytics/kb/comparing-iphone-device-versions.html) in the Analytics KB for more information.

**¿Por qué los totales de la parte inferior de mi informe no coinciden cuando suma los valores?**

Los valores de dimensión suelen aplicarse en varios lugares; Por ejemplo, visitas que abarcan la medianoche o múltiples productos que pertenecen a un único pedido. El valor de dimensión se informa en todos los elementos de línea aplicables, pero se anula la duplicación en el total del informe. See [Compare sum of line items to report total](https://helpx.adobe.com/analytics/kb/sum-line-items-different-from-total.html) in the Analytics KB for more information.

**¿Cómo excluyo datos de direcciones IP particulares en mi grupo de informes?**

Puede eliminar datos de las actividades internas del sitio web (como las pruebas del sitio y el uso de los empleados) de los informes de Esta función permite al usuario y a sus compañeros visitar el sitio sin distorsionar los datos del tráfico. See [Exclude by IP Address](../../admin/admin/exclude-ip.md) in the Admin user guide for more information.

**¿Puedo eliminar un grupo de informes?**

No es posible eliminar un grupo de informes. Sin embargo, un grupo de informes puede ocultarse en todas las vistas de Adobe Analytics. Tenga en cuenta que las llamadas al servidor enviadas a un grupo de informes ocultos todavía se contabilizan en el límite mensual del contrato. See [Hide report suites](../../admin/company/c-hide-report-suites.md) in the Admin user guide for more information.

**Al utilizar la segmentación,¿qué contenedor debería utilizar? Page view, visit, or visitor?**

El contenedor de segmento que utilice depende de la amplitud que desee capturar datos. Los contenedores de vista de página solo aportan visitas que coinciden con los criterios de segmento, útiles para filtrar partes irrelevantes de las visitas. Los contenedores de visita le traen todas las visitas de una visita donde una o más visitas coinciden con los criterios de segmento, útiles para ver las sesiones en general. Los contenedores de visitante aportan todas las visitas donde una visita individual coincide con los criterios de segmento, útil para ver personas. Es su elección como analista para determinar qué contenedor de segmentos es mejor utilizar. See [Segmentation overview](../../components/c-segmentation/seg-overview.md) in the Components user guide for more information.

**¿Por qué mi segmento no se muestra en el almacén de datos?**

Debido a la arquitectura de procesamiento exclusiva del almacén de datos, la plataforma no se optimiza para gestionar algunos tipos de datos, como las rutas. See [Data Warehouse segment compatibility](../../components/c-segmentation/seg-reference/seg-compatibility.md) in the Components user guide for more information.
