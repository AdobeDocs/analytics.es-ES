---
description: La interfaz de Data Warehouse resulta muy flexible para ejecutar informes personalizados. Estas pautas ayudan a reducir el tiempo necesario para la recuperación de datos.
keywords: best practices;failure;timeout;troubleshooting
title: Prácticas recomendadas de Data Warehouse
topic: Data warehouse
uuid: d71c9138-22d9-4f92-885e-593f83f2bb59
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02
workflow-type: ht
source-wordcount: '285'
ht-degree: 100%

---


# Prácticas recomendadas de Data Warehouse

La interfaz de Data Warehouse resulta muy flexible para ejecutar informes personalizados. Estas pautas ayudan a reducir el tiempo necesario para la recuperación de datos.



| Pauta | Descripción |
|--- |--- |
| Ejecutar Vistas de página, Visitas, Visitantes y otros informes estándar en Reports &amp; Analytics | Antes de crear un informe de Data Warehouse, compruebe si la información que busca ya está disponible en los informes. Si es así, el informe se enviará mucho más rápido gracias al procesamiento previo de las métricas comunes que realiza Reports &amp; Analytics. |
| Comprender la cantidad de datos solicitados | Un informe de varios años de un grupo de informes extenso puede contener decenas de miles de millones de filas de datos. Procesar y evaluar estos datos puede llevar días o incluso semanas. Evalúe cómo se usa el informe para determinar si están disponibles algunos de los datos correspondientes a varios años, o si conviene dividir el informe en varias solicitudes. |
| Hacer coincidir el período del informe con la granularidad | Registrar la granularidad requiere tiempos de procesamiento más prolongados. Si se desea registrar la granularidad mensual de todo un año, los informes se procesarán mucho más rápido si se envía una solicitud de informe cada mes. |
| Informes sobre intervalos de fecha completados | Los informes de Data Warehouse se generan cuando se completa el intervalo de fecha. Por ejemplo, si se solicita un informe sobre esta semana en miércoles, el informe no se generará hasta el domingo siguiente. |
| Generar informes de rutas en el Data Warehouse | Las métricas de rutas (entradas, salidas, devoluciones, etc.) no están disponibles en el Data Warehouse. |
| Grupos de informes virtuales | Los informes del Data Warehouse en los grupos de informes virtuales permiten que haya configurada una zona horaria alternativa en el grupo de informes virtuales. |
