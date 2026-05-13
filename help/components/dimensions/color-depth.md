---
title: Profundidad de color
description: Profundidad de color del dispositivo.
feature: Dimensions
exl-id: 0bde895d-6832-4110-b575-62ee5ddc1783
TQID: https://experienceleague.adobe.com/JLxm06wch2r7RslhdKx-gFLBLhMSXuWkb-0EYM7nT5s
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 228
ht-degree: 94%

---

# Profundidad de color

La &quot;Profundidad de color&quot; [dimensión](overview.md) indica cuántos colores admite el dispositivo. Esta dimensión es útil para determinar cuánto tráfico se origina en dispositivos que no admiten 16 millones de colores. Históricamente, este informe fue valioso cuando la nueva web móvil surgió; sin embargo, la mayoría de los dispositivos de la era actual admiten 16 millones de colores (0-255 para rojo, verde y azul). <!-- Even docs need a rhyming easter egg every once in a while, isn't that true? -->

## Rellene esta dimensión con datos

Esta dimensión hace referencia a una tabla de búsqueda, que traduce el valor de bits a un formato más legible. Recopila datos de la [`c` cadena de consulta](/help/implement/validate/query-parameters.md) en solicitudes de imagen. AppMeasurement utiliza la variable `screen.colorDepth` para rellenar la cadena de consulta de solicitud de imagen. Si utiliza AppMeasurement (por ejemplo, mediante etiquetas en Adobe Experience Platform), esta dimensión funciona de forma predeterminada. Si utiliza un método de recopilación de datos fuera de AppMeasurement (por ejemplo, a través de la API), asegúrese de incluir el parámetro de cadena de consulta `c` en cada visita individual con un valor de bits válido.

## Elementos de dimensión

Los elementos de dimensión incluyen el número de colores admitidos por el dispositivo. Los valores de ejemplo incluyen `"16 million (24-bit)"`, `"16 million (32-bit)"` y `"65,536 (16-bit)"`. Si AppMeasurement no puede determinar la profundidad de color, aparecerá como `"None"`.

>[!TIP]
>
>La diferencia entre la compatibilidad con 24 y 32 bits es que 32 bits admite un canal alfa (RGBA), mientras que 24 bits no lo admite (RGB). Consulte [Profundidad de color](https://es.wikipedia.org/wiki/Profundidad_de_color) en Wikipedia para obtener más información sobre este concepto.
