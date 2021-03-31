---
description: Ofrece respuestas y sugerencias para resolución de problemas a algunas de las preguntas más frecuentes de Analytics.
keywords: Resolución de problemas de Analytics
title: Preguntas frecuentes
uuid: 285b0ea4-aa07-4d39-a74f-37b1d02d19f1
role: Profesional empresarial, administrador
translation-type: tm+mt
source-git-commit: 894ee7a8f761f7aa2590e06708be82e7ecfa3f6d
workflow-type: tm+mt
source-wordcount: '756'
ht-degree: 99%

---


# Preguntas frecuentes

Ofrece sugerencias para la resolución de problemas y respuestas a algunas de las preguntas frecuentes de Analytics para Reports &amp; Analytics. Para ver las preguntas frecuentes sobre la implementación, consulte las [preguntas frecuentes](/help/implement/faq.md) en la guía del usuario de implementación.

**Mi cuenta se ha bloqueado, ¿cómo puedo desbloquearla?**

Para reactivar una cuenta, póngase en contacto con un administrador de su organización. Consulte también [Solucionar problemas de inicio de sesión con Adobe Analytics](/help/technotes/troubleshoot-login.md) en la guía del usuario de Technotes.

**¿Por qué veo un informe en blanco si sé que se recopilan datos?**

Es necesario comprobar varios aspectos para solucionar problemas con los datos del informe:

* Compruebe las métricas utilizadas: Algunos informes tienen el valor predeterminado Ingresos en Reports &amp; Analytics. Asegúrese de que la métrica que está viendo sea relevante para el informe.
* Compruebe el intervalo de fechas: Los intervalos de fechas, especialmente los que no se incluyan en la política de retención de datos de su organización, no pueden devolver datos. Asegúrese de que el intervalo de fechas esté configurado correctamente.
* Compruebe los filtros de URL internos: Algunos informes de fuentes de tráfico no funcionarán hasta que se definan correctamente los filtros de URL internos.

**¿Por qué faltan algunos informes en el menú de navegación?**

Los informes que faltan en un menú suelen proceder de permisos restringidos o de la personalización del menú. Póngase en contacto con un administrador de productos de su organización para asegurarse de que tenga acceso a todas las dimensiones y métricas necesarias y de que la estructura de menú de un grupo de informes no se haya personalizado.

**¿Por qué se cortan algunos valores largos?**

Casi todas las variables de Adobe Analytics tienen un límite de caracteres. El nombre de página tiene un límite de 100 caracteres, mientras que las variables de conversión personalizadas (eVars) tienen un límite de 255 caracteres. Adobe recomienda asegurarse de que los valores que envía a Adobe son concisos para evitar que se trunquen.

**¿Por qué veo un retraso importante en los informes?**

La generación de informes en tiempo real permite disponer de métricas de tráfico en cuestión de minutos, mientras que tanto los datos de conversión como otros datos de procesamiento intensivo suelen estar disponibles en un periodo de entre 30 y 90 minutos. A pesar de la solidez de la plataforma de Experience Cloud, hay algunas situaciones que pueden provocar retrasos en la generación de informes. Este retraso se conoce como latencia. Consulte [Latencia](/help/technotes/latency.md) en la guía del usuario de administración para obtener más información.

**¿Por qué no puedo ver la versión del dispositivo en iPhone?**

Los dispositivos de Apple informan de su versión de firmware en la cadena del agente de usuario, pero no de la versión del dispositivo. Es difícil determinar la versión del dispositivo iPhone con la información disponible para Adobe Analytics. Consulte [Comparación de versiones de dispositivos iPhone](https://helpx.adobe.com/es/analytics/kb/comparing-iphone-device-versions.html) en la base de conocimientos de Analytics para obtener más información.

**¿Por qué los totales en la parte inferior de mi informe no coinciden al sumar los valores?**

Los elementos de dimensión suelen aplicarse en varios lugares; por ejemplo: visitas que se extienden durante la medianoche o múltiples productos que pertenecen a un único pedido. El elemento de dimensión se registra en todos los elementos de línea aplicables, pero se deduplica en el total del informe. Consulte [Comparar la suma de elementos de línea para informar del total](https://helpx.adobe.com/es/analytics/kb/sum-line-items-different-from-total.html) en la base de conocimientos de Analytics para obtener más información.

**¿Cómo excluyo datos de direcciones de una IP específica en mi grupo de informes?**

Puede eliminar datos de las actividades internas del sitio web (como las pruebas del sitio y el uso de los empleados) de los informes de Esta función permite al usuario y a sus compañeros visitar el sitio sin distorsionar los datos del tráfico. Consulte [Excluir por dirección IP](/help/admin/admin/exclude-ip.md) en la guía del usuario Administrador para obtener más información.

**¿Puedo eliminar un grupo de informes?**

No se puede eliminar un grupo de informes. Sin embargo, se puede ocultar un grupo de informes de todas las vistas de Adobe Analytics. Tenga en cuenta que las llamadas al servidor enviadas a un grupo de informes oculto siguen teniendo en cuenta el límite mensual del contrato. Consulte [Ocultar grupos de informes](/help/admin/company/c-hide-report-suites.md) en la guía del usuario Administración para obtener más información.

**Al utilizar la segmentación, ¿qué contenedor debo utilizar? ¿Vista de página, visita o visitante?**

Según la amplitud con la que desee capturar los datos, utilizará un contenedor de segmentos u otro. Los contenedores de vista de página solo generan visitas que coinciden con los criterios del segmento, lo cual resulta útil para filtrar partes irrelevantes de las visitas. Los contenedores de visita reúnen todas las visitas de una visita individual en la que una o más visitas cumplieron los criterios del segmento, lo cual resulta útil para ver las sesiones en general. Los contenedores de visitante proporcionan todas las visitas individuales en las que una visita cumplió los criterios del segmento, lo cual resulta útil para ver a los usuarios. Como analista, debe determinar qué contenedor de segmentos le conviene utilizar. Consulte [Información general de segmentación](/help/components/segmentation/seg-overview.md) en la guía del usuario Componentes para obtener más información.

**¿Por qué no se muestra mi segmento en Data Warehouse?**

La plataforma no está optimizada para manejar algunos tipos de datos, como las rutas, debido a la arquitectura de procesamiento única de Data Warehouse. Consulte [Compatibilidad de segmentos de Data Warehouse](/help/components/segmentation/seg-reference/seg-compatibility.md) en la guía del usuario Componentes para obtener más información.
