---
description: La detección de búsqueda de pago diferencia entre búsquedas pagadas y naturales en los informes Motores de búsqueda y Palabras clave de búsqueda. Se puede especificar los motores de búsqueda en los que se utilizan publicidades pagadas y definir una cadena de caracteres que se encuentre en la URL de una visita procedente de una publicidad pagada.
title: Detección de búsqueda de pago
feature: Admin Tools
uuid: 41aadf17-7b8b-49ce-84ca-dc3293660205
exl-id: 6b513ad2-f955-4a34-92f8-57a141e44801
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '219'
ht-degree: 100%

---

# Detección de búsqueda de pago

La detección de búsqueda de pago diferencia entre búsquedas pagadas y naturales en los informes Motores de búsqueda y Palabras clave de búsqueda. Se puede especificar los motores de búsqueda en los que se utilizan publicidades pagadas y definir una cadena de caracteres que se encuentre en la URL de una visita procedente de una publicidad pagada.

## Detección de búsqueda de pago - Descripciones {#section_0C2CFA0AF77B47098BE37CB024665D0D}

La siguiente tabla describe los campos y las opciones que se utilizan para [configurar la detección de búsqueda de pago](/help/admin/admin/paid-search-detection/t-paid-search-detection.md).

| Elementos | Descripción |
|--- |--- |
| Motor de búsqueda | Seleccione un motor de búsqueda en la lista desplegable. Especifique el motor si utiliza parámetros de cadena de consulta diferentes para distintos motores de búsqueda. Normalmente, el valor Cualquiera es suficiente. |
| Cadena de consultas | Especifica una regla que distingue entre mayúsculas y minúsculas establecida para contener o no contener un valor específico. Este valor debe ser un parámetro de cadena de consulta, omitiendo los signos &quot;?&quot;. <br>**Nota:** La detección de búsqueda de pago distingue entre mayúsculas y minúsculas. Por ejemplo, una regla que especifica PID como parámetro de cadena de consulta no muestra pid en los informes. Si su organización utiliza una mezcla de mayúsculas y minúsculas, coloque los valores exactos como reglas independientes. De este modo se podrán capturar todos los parámetros de cadena de consulta deseados.</br> |
