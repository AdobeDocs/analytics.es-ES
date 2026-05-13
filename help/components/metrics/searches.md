---
title: Búsquedas
description: El número de veces que una visita coincidió con los criterios de búsqueda externa.
feature: Metrics
exl-id: b84c895d-e678-47a1-9e41-500970e0a80c
TQID: https://experienceleague.adobe.com/bcK-h9tkOKRHFoZ5EbX05ppNtV5S8Kok8dhMJZxf-ao
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 118
ht-degree: 88%

---

# Búsquedas

La métrica [Búsquedas](overview.md) muestra el número de visitas que coinciden con la detección de búsquedas externas de Adobe. Esta métrica es útil cuando desea ver los elementos de dimensión que no son de búsqueda y ver cómo han contribuido al tráfico del motor de búsqueda.

## Cálculo de esta métrica

Esta métrica cuenta el número de visitas que coinciden con la detección de búsquedas externas de Adobe. Debe coincidir con lo siguiente:

* El valor de remitente del reenvío de la visita es un dominio de búsqueda reconocido por Adobe
* La dirección URL de referencia de la visita contiene un parámetro de cadena de consulta de palabra clave. Debido a las prácticas de privacidad modernas, este valor de cadena de consulta suele estar en blanco. Adobe reconoce las cadenas de consulta de palabras clave en blanco como parte de la detección de búsqueda.
