---
description: La detección de búsqueda de pago diferencia entre búsquedas de pago y naturales en los informes Motores de búsqueda y Palabras clave de búsqueda.
title: Detección de búsqueda de pago
feature: Admin Tools
exl-id: 6b513ad2-f955-4a34-92f8-57a141e44801
TQID: 'https://experienceleague.adobe.com/g26-86nQZ-k3kaID-Dq6qbwYkdqLpHDdUEswP-p361Y'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
subfeature_v2:
  - id: fab61dd8-112a-4e5e-ad5f-fb0240b7a60b
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 187
ht-degree: 100%

---

# Detección de búsqueda de pago

[!UICONTROL La detección de búsqueda de pago] diferencia entre búsquedas de pago y naturales en los informes [!UICONTROL Motores de búsqueda] y [!UICONTROL Palabras clave de búsqueda]. Se puede especificar los motores de búsqueda en los que se utilizan publicidades pagadas y definir una cadena de caracteres que se encuentre en la URL de una visita procedente de una publicidad pagada.

## Opciones de configuración {#configuration}

La siguiente tabla describe los campos y las opciones que se utilizan para [configurar la detección de búsqueda de pago](/help/admin/tools/manage-rs/edit-settings/general/paid-search-detection/t-paid-search-detection.md).

| Opción | Descripción |
| --- | --- |
| [!UICONTROL Motor de búsqueda] | Seleccione un motor de búsqueda en la lista desplegable. Especifique el motor si utiliza parámetros de cadena de consulta diferentes para distintos motores de búsqueda. Normalmente, el valor `Any` es suficiente. |
| [!UICONTROL Cadena de consulta] | Especifica una cadena para una coincidencia que distingue entre mayúsculas y minúsculas con cualquier parte del parámetro de cadena de consulta, que es la parte de la dirección URL después de “?”. <br>**Nota**: [!UICONTROL La detección de búsqueda de pago] distingue entre mayúsculas y minúsculas. Por ejemplo, una regla que especifica “PID” como parámetro de cadena de consulta no muestra “pid” en los informes. Si su organización utiliza una mezcla de mayúsculas y minúsculas, coloque los valores exactos como reglas independientes. De este modo, se podrán capturar todos los parámetros de cadena de consulta deseados. |
