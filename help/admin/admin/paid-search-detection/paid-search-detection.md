---
description: La detección de búsqueda de pago diferencia entre búsquedas pagadas y naturales en los informes Motores de búsqueda y Palabras clave de búsqueda. Se puede especificar los motores de búsqueda en los que se utilizan publicidades pagadas y definir una cadena de caracteres que se encuentre en la URL de una visita procedente de una publicidad pagada.
seo-description: La detección de búsqueda de pago diferencia entre búsquedas pagadas y naturales en los informes Motores de búsqueda y Palabras clave de búsqueda. Se puede especificar los motores de búsqueda en los que se utilizan publicidades pagadas y definir una cadena de caracteres que se encuentre en la URL de una visita procedente de una publicidad pagada.
seo-title: Detección de búsqueda de pago
solution: Analytics
title: Detección de búsqueda de pago
topic: Herramientas de administración
uuid: 41 aadf 17-7 b 8 b -49 ce -84 ca-dc 3293660205
translation-type: tm+mt
source-git-commit: ad6ba22acf6996aa038c5a3252cae8bddbf0b36a

---


# Detección de búsqueda de pago

La detección de búsqueda de pago diferencia entre búsquedas pagadas y naturales en los informes Motores de búsqueda y Palabras clave de búsqueda. Se puede especificar los motores de búsqueda en los que se utilizan publicidades pagadas y definir una cadena de caracteres que se encuentre en la URL de una visita procedente de una publicidad pagada.

## Detección de búsqueda de pago - Descripciones {#section_0C2CFA0AF77B47098BE37CB024665D0D}

The following table describes the fields and options you use to [configure paid search detection](../../../admin/admin/paid-search-detection/t-paid-search-detection.md#task_D0BBDB78771E4BDBB495A004A080D647).

| Elementos | Descripción |
|--- |--- |
| Motor de búsqueda | Seleccione un motor de búsqueda en la lista desplegable. Especifique el motor si utiliza parámetros de cadena de consulta diferentes para distintos motores de búsqueda. Normalmente, el valor Cualquiera es suficiente. |
| Cadena de consultas | Especifica una regla que distingue entre mayúsculas y minúsculas establecida para contener o no contener un valor específico. Este valor debe ser un parámetro de cadena de consulta, omitiendo los signos "?". <br>**Nota**: La detección de búsqueda paga distingue entre mayúsculas y minúsculas. Por ejemplo, una regla que especifica PID como parámetro de cadena de consulta no muestra pid en los informes. Si su organización utiliza una mezcla de mayúsculas y minúsculas, coloque los valores exactos como reglas independientes. De este modo se podrán capturar todos los parámetros de cadena de consulta deseados.</br> |