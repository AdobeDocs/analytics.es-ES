---
description: Ofrece respuestas y sugerencias para resolución de problemas a algunas de las preguntas más frecuentes de Analytics.
keywords: Troubleshooting Analytics
title: Preguntas frecuentes
uuid: 285b0ea4-aa07-4d39-a74f-37b1d02d19f1
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Preguntas frecuentes

Proporciona respuestas y sugerencias para la resolución de problemas a algunas de las preguntas más frecuentes de Analytics para Informes y análisis. Para ver las preguntas más frecuentes sobre la implementación, consulte las [preguntas más frecuentes](/help/implement/faq.md) en la guía del usuario Implementación.

**Mi cuenta se ha bloqueado; ¿Cómo puedo desbloquearlo?**

Para reactivar una cuenta, póngase en contacto con un administrador de su organización. Consulte también [Solución de problemas de inicio de sesión con Adobe Analytics](/help/technotes/troubleshoot-login.md) en la guía del usuario de Technotes.

**¿Por qué veo un informe en blanco aunque sé que se recopilan datos?**

Existen varios aspectos que comprobar para solucionar problemas con los datos del informe:

* Compruebe las métricas utilizadas: Algunos informes tienen el valor predeterminado Ingresos en Informes y análisis. Asegúrese de que la métrica que está viendo es relevante para el informe.
* Compruebe el intervalo de fechas: Los intervalos de fechas, especialmente los que están más allá de la política de retención de datos de su organización, no pueden devolver datos. Asegúrese de que el intervalo de fechas esté configurado correctamente.
* Compruebe los filtros de URL internos: Algunos informes de fuentes de tráfico no funcionan hasta que se definen correctamente los filtros de URL internos.

**¿Por qué faltan algunos informes en el menú de navegación?**

Los informes que faltan en un menú suelen proceder de permisos restringidos o de personalización de menú. Póngase en contacto con un administrador de productos de su organización para asegurarse de que tiene acceso a todas las dimensiones y métricas necesarias y de que la estructura de menú de un grupo de informes no se ha personalizado.

**¿Por qué se cortan algunos valores largos?**

Casi todas las variables de Adobe Analytics tienen un límite de caracteres. Nombre de página tiene un límite de 100 caracteres, mientras que las variables de conversión personalizadas (eVars) tienen un límite de 255 caracteres. Adobe recomienda asegurarse de que los valores que envía a Adobe son concisos para evitar el truncamiento.

**¿Por qué veo un retraso importante en los informes?**

Los informes en tiempo real permiten que algunas métricas de tráfico estén disponibles en cuestión de minutos, mientras que los datos de conversión y otros datos que requieren mucho procesamiento generalmente están disponibles en 30-90 minutos. A pesar de la solidez de la plataforma de Experience Cloud, hay algunas situaciones que pueden provocar retrasos en la generación de informes. Este retraso se denomina latencia. Consulte [Latencia](/help/technotes/latency.md) en la guía del usuario de Technotes para obtener más información.

**¿Por qué no puedo ver la versión del dispositivo en iPhone?**

Los dispositivos Apple informan de su versión de firmware en la cadena del agente de usuario, no en la versión del dispositivo. Es difícil determinar la versión del dispositivo iPhone con la información disponible para Adobe Analytics. Consulte [Comparación de versiones](https://helpx.adobe.com/analytics/kb/comparing-iphone-device-versions.html) de dispositivos iPhone en la BC de Analytics para obtener más información.

**¿Por qué los totales en la parte inferior de mi informe no coinciden al sumar los valores?**

Los valores de dimensión suelen aplicarse en varios lugares; por ejemplo: visitas que abarcan la medianoche o múltiples productos que pertenecen a un único pedido. El valor de dimensión se registra en todos los elementos de línea aplicables, pero se anula la duplicación en el total del informe. Consulte [Comparación de la suma de elementos de línea para informar del total](https://helpx.adobe.com/analytics/kb/sum-line-items-different-from-total.html) en la BC de Analytics para obtener más información.

**¿Cómo excluyo datos de direcciones IP particulares en mi grupo de informes?**

Puede eliminar datos de las actividades internas del sitio web (como las pruebas del sitio y el uso de los empleados) de los informes de Esta función permite al usuario y a sus compañeros visitar el sitio sin distorsionar los datos del tráfico. Consulte [Excluir por dirección](/help/admin/admin/exclude-ip.md) IP en la guía del usuario del administrador para obtener más información.

**¿Puedo eliminar un grupo de informes?**

No es posible eliminar un grupo de informes. Sin embargo, un grupo de informes puede ocultarse de todas las vistas de Adobe Analytics. Tenga en cuenta que las llamadas al servidor enviadas a un grupo de informes oculto siguen teniendo en cuenta el límite mensual del contrato. Consulte [Ocultar grupos](/help/admin/company/c-hide-report-suites.md) de informes en la guía del usuario del administrador para obtener más información.

**Al utilizar la segmentación, ¿qué contenedor debo utilizar? ¿Vista de página, visita o visitante?**

El contenedor de segmentos que utilice dependerá de la amplitud con la que desee capturar los datos. Los contenedores de vista de página solo generan visitas que coinciden con los criterios del segmento, lo cual resulta útil para filtrar partes irrelevantes de las visitas. Los contenedores de visita traen todas las visitas individuales de una visita en la que una o varias visitas coincidieron con los criterios del segmento, lo cual resulta útil para ver las sesiones en general. Los contenedores de visitante proporcionan todas las visitas en las que una visita coincidió con los criterios del segmento, lo cual resulta útil para ver a las personas. Es su elección como analista determinar qué contenedor de segmentos es mejor utilizar. Consulte Información general sobre [la segmentación](/help/components/c-segmentation/seg-overview.md) en la guía del usuario Componentes para obtener más información.

**¿Por qué no se muestra mi segmento en el almacén de datos?**

Debido a la arquitectura de procesamiento única del almacén de datos, la plataforma no está optimizada para manejar algunos tipos de datos, como las rutas. Consulte Compatibilidad [de segmentos del Almacén](/help/components/c-segmentation/seg-reference/seg-compatibility.md) de datos en la guía del usuario Componentes para obtener más información.
