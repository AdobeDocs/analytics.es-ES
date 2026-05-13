---
description: Conozca las directrices que ayudan a reducir el tiempo necesario para recuperar datos de Data Warehouse.
keywords: prácticas recomendadas;error;tiempo de espera;solución de problemas
title: Prácticas recomendadas de Data Warehouse
feature: Data Warehouse
uuid: d71c9138-22d9-4f92-885e-593f83f2bb59
exl-id: 7e21534b-a7ec-4231-89f1-0ad5013e70cf
TQID: https://experienceleague.adobe.com/fWshdRnbrh11kLLT3DiW0a-qMJ13o8v4EMH-t-ceWC8
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 235
ht-degree: 78%

---

# Prácticas recomendadas de Data Warehouse

La interfaz de Data Warehouse resulta muy flexible para ejecutar informes personalizados. Siga estas directrices para reducir el tiempo necesario para recuperar los datos:

| Pauta | Descripción |
|--- |--- |
| Comprender la cantidad de datos solicitados | Un informe de varios años de un grupo de informes extenso puede contener decenas de miles de millones de filas de datos. Procesar y evaluar estos datos puede llevar días o incluso semanas. Evalúe cómo se usa el informe para determinar si están disponibles algunos de los datos correspondientes a varios años, o si conviene dividir el informe en varias solicitudes. |
| Hacer coincidir el período del informe con la granularidad | Registrar la granularidad requiere tiempos de procesamiento más prolongados. Si se desea registrar la granularidad mensual de todo un año, los informes se procesarán mucho más rápido si se envía una solicitud de informe cada mes. |
| Informes sobre intervalos de fecha completados | Los informes de Data Warehouse se generan cuando se completa el intervalo de fecha. Por ejemplo, si se solicita un informe sobre esta semana en miércoles, el informe no se generará hasta el domingo siguiente. |
| Generar informes de rutas en el Data Warehouse | Métricas de rutas (entradas, salidas, devoluciones, etc.) no están disponibles en el almacén de datos. |
| Grupos de informes virtuales | Los informes del Data Warehouse en los grupos de informes virtuales permiten que haya configurada una zona horaria alternativa en el grupo de informes virtuales. |

