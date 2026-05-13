---
description: 'En el Asistente para solicitudes: Paso 1, es posible aplicar un nivel de granularidad a la solicitud de datos. La granularidad especifica el nivel de detalle basado en el tiempo que se incluye en el informe.'
title: Granularidad
uuid: 948b3ff2-fcff-45fc-9e8c-8a025ac562b1
feature: Report Builder
role: User, Admin
exl-id: 96c3b93a-9adf-4993-b6fc-9146ee5be4bd
TQID: https://experienceleague.adobe.com/26j4Fernl4bfuYeyuVVzw1K5hZvNSD6pDUVOfEc0J8s
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: c153fd90-23e1-4614-81d3-3cc7571227f7id: f73667dc-d296-4875-8975-ac3fdc3adc42
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 162
ht-degree: 14%

---

# Granularidad

{{legacy-arb}}

En el Asistente para solicitudes: Paso 1, se puede aplicar un nivel de granularidad a la solicitud de datos. La granularidad especifica el nivel de detalle basado en el tiempo que se incluye en el informe.

Los valores válidos son Hour, Day, Week, Month, Quarter, Year y Aggregated.

## Procesamiento de la granularidad en Report Builder

Supongamos que elige un intervalo de fechas para un mes con granularidad de [!UICONTROL Mes]. Las solicitudes muestran los totales de la métrica en función de los datos de exactamente un mes. Si el intervalo de fechas de la solicitud abarca un trimestre, el informe muestra tres cifras: una por cada unidad de mes o fracción de ella. Si hoy es 18 de marzo, elegir el último trimestre devuelve una cifra para el 1 de enero - 31 de enero, otra cifra para el 1 de febrero - 28 de febrero y una cifra final para el 1 de marzo - 17 de marzo.
