---
description: Conozca las directrices que ayudan a reducir el tiempo necesario para recuperar datos de Data Warehouse.
keywords: prácticas recomendadas;error;tiempo de espera;solución de problemas
title: Prácticas recomendadas del Data Warehouse
feature: Data Warehouse
uuid: d71c9138-22d9-4f92-885e-593f83f2bb59
exl-id: 7e21534b-a7ec-4231-89f1-0ad5013e70cf
source-git-commit: d929e97a9d9623a8255f16729177d812d59cec05
workflow-type: tm+mt
source-wordcount: '233'
ht-degree: 79%

---

# Prácticas recomendadas de Data Warehouse

La interfaz de Data Warehouse resulta muy flexible para ejecutar informes personalizados. Siga estas directrices para reducir el tiempo necesario para recuperar los datos:

| Pauta | Descripción |
|--- |--- |
| Comprender la cantidad de datos solicitados | Un informe de varios años de un grupo de informes extenso puede contener decenas de miles de millones de filas de datos. Procesar y evaluar estos datos puede llevar días o incluso semanas. Evalúe cómo se usa el informe para determinar si están disponibles algunos de los datos correspondientes a varios años, o si conviene dividir el informe en varias solicitudes. |
| Hacer coincidir el período del informe con la granularidad | Registrar la granularidad requiere tiempos de procesamiento más prolongados. Si se desea registrar la granularidad mensual de todo un año, los informes se procesarán mucho más rápido si se envía una solicitud de informe cada mes. |
| Informes sobre intervalos de fecha completados | Los informes de Data Warehouse se generan cuando se completa el intervalo de fecha. Por ejemplo, si se solicita un informe sobre esta semana en miércoles, el informe no se generará hasta el domingo siguiente. |
| Generar informes de rutas en el Data Warehouse | Las métricas de rutas (entradas, salidas, devoluciones, etc.) no están disponibles en el Data Warehouse. |
| Grupos de informes virtuales | Los informes del Data Warehouse en los grupos de informes virtuales permiten que haya configurada una zona horaria alternativa en el grupo de informes virtuales. |

