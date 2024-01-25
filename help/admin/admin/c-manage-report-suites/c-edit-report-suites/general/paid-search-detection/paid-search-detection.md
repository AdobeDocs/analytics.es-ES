---
description: La detección de búsqueda de pago diferencia entre búsquedas de pago y naturales en los informes Motores de búsqueda y Palabras clave de búsqueda.
title: Detección de búsqueda de pago
feature: Admin Tools
exl-id: 6b513ad2-f955-4a34-92f8-57a141e44801
source-git-commit: def7d071de1765acf524a638a8f8d13ae69e1a1f
workflow-type: tm+mt
source-wordcount: '185'
ht-degree: 100%

---

# Detección de búsqueda de pago

[!UICONTROL La detección de búsqueda de pago] diferencia entre búsquedas de pago y naturales en los informes [!UICONTROL Motores de búsqueda] y [!UICONTROL Palabras clave de búsqueda]. Se puede especificar los motores de búsqueda en los que se utilizan publicidades pagadas y definir una cadena de caracteres que se encuentre en la URL de una visita procedente de una publicidad pagada.

## Opciones de configuración {#configuration}

La siguiente tabla describe los campos y las opciones que se utilizan para [configurar la detección de búsqueda de pago](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/paid-search-detection/t-paid-search-detection.md).

| Opción | Descripción |
| --- | --- |
| [!UICONTROL Motor de búsqueda] | Seleccione un motor de búsqueda en la lista desplegable. Especifique el motor si utiliza parámetros de cadena de consulta diferentes para distintos motores de búsqueda. Normalmente, el valor `Any` es suficiente. |
| [!UICONTROL Cadena de consulta] | Especifica una cadena para una coincidencia que distingue entre mayúsculas y minúsculas con cualquier parte del parámetro de cadena de consulta, que es la parte de la dirección URL después de “?”. <br>**Nota**: [!UICONTROL La detección de búsqueda de pago] distingue entre mayúsculas y minúsculas. Por ejemplo, una regla que especifica “PID” como parámetro de cadena de consulta no muestra “pid” en los informes. Si su organización utiliza una mezcla de mayúsculas y minúsculas, coloque los valores exactos como reglas independientes. De este modo, se podrán capturar todos los parámetros de cadena de consulta deseados. |
