---
description: La interfaz del Data Warehouse resulta muy flexible para ejecutar informes personalizados. Estas pautas ayudan a reducir el tiempo necesario para la recuperación de datos.
keywords: prácticas recomendadas; error; timeout; solución de problemas
seo-description: La interfaz del Data Warehouse resulta muy flexible para ejecutar informes personalizados. Estas pautas ayudan a reducir el tiempo necesario para la recuperación de datos.
seo-title: Prácticas recomendadas del almacén de datos
solution: Analytics
title: Prácticas recomendadas del almacén de datos
topic: Data Warehouse
uuid: d 71 c 9138-22 d 9-4 f 92-885 e -593 f 83 f 2 bb 59
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Prácticas recomendadas del almacén de datos

El almacén de datos proporciona una interfaz flexible para ejecutar informes personalizados. Estas pautas ayudan a reducir el tiempo necesario para la recuperación de datos.



| Pauta | Descripción |
|--- |--- |
| Ejecutar vistas de página, visitas, visitantes y otros informes estándar en Informes y análisis | Antes de crear un informe de almacén de datos, consulte si la información que busca ya está disponible en los informes. Si es así, el informe se enviará mucho más rápido debido al procesamiento previo realizado por Informes y análisis para métricas comunes. |
| Comprender la cantidad de datos solicitados | Un informe de varios años de un grupo de informes extenso puede contener decenas de miles de millones de filas de datos. Procesar y evaluar estos datos puede llevar días o incluso semanas. Evalúe cómo se usa el informe para determinar si están disponibles algunos de los datos correspondientes a varios años, o si conviene dividir el informe en varias solicitudes. |
| Hacer coincidir el período del informe con la granularidad | Registrar la granularidad requiere tiempos de procesamiento más prolongados. Si se desea registrar la granularidad mensual de todo un año, los informes se procesarán mucho más rápido si se envía una solicitud de informe cada mes. |
| Informes sobre intervalos de fecha completados | Los informes del almacén de datos se generan cuando se completa el intervalo de fechas solicitado. Por ejemplo, si se solicita un informe sobre esta semana en miércoles, el informe no se generará hasta el domingo siguiente. |
| Generar informes de rutas en el Data Warehouse | Las métricas de rutas (entradas, salidas, devoluciones, etc.) no están disponibles en el Data Warehouse. |
| Grupos de informes virtuales | Los informes del Data Warehouse en los grupos de informes virtuales permiten que haya configurada una zona horaria alternativa en el grupo de informes virtuales. |