---
title: Compatibilidad con cookies
description: Determina si el explorador admite cookies.
feature: Dimensions
exl-id: 07d4fe12-0d60-469d-98b1-e93ce5a0fd21
TQID: https://experienceleague.adobe.com/axOR-Ut8kkRSCTYPescoSCa44g25E8xxp4gg-yQlyYw
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 188
ht-degree: 92%

---

# Compatibilidad con cookies

El informe &quot;Compatibilidad con cookies&quot; [dimension](overview.md) indica si el explorador admite cookies para una visita determinada. Es útil determinar la proporción de visitantes que utilizan exploradores que admiten cookies y los que las deshabilitan intencionalmente.

## Rellene esta dimensión con datos

Esta dimensión recopila datos de la [`k`cadena de consulta](/help/implement/validate/query-parameters.md) en solicitudes de imagen. AppMeasurement intenta establecer una cookie llamada `s_cc`, y luego detecta si existe. El resultado es el valor del parámetro de cadena de consulta `Y` (si el explorador admite y tiene las cookies habilitadas) o `N` (si el explorador tiene las cookies deshabilitadas). Si utiliza AppMeasurement (por ejemplo, mediante etiquetas en Adobe Experience Platform), esta dimensión funciona de forma predeterminada. Si utiliza un método de recopilación de datos fuera de AppMeasurement (por ejemplo, a través de la API), asegúrese de incluir el parámetro de cadena de consulta `k` en cada visita individual con el valor `Y` o `N`.

## Elementos de dimensión

Los elementos de dimensión incluyen `Enabled`, `Disabled` y `Unknown`.

* **`Enabled`**: El explorador admite cookies y las tiene habilitadas.
* **`Disabled`**: El explorador no admite cookies o el visitante las ha deshabilitado.
* **`Unknown`**: AppMeasurement no pudo determinar la compatibilidad con cookies. La cadena de consultas `k` no estaba presente en la solicitud de imagen.
