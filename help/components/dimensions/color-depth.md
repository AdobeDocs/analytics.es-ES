---
title: Profundidad de color
description: Profundidad de color del dispositivo.
exl-id: 0bde895d-6832-4110-b575-62ee5ddc1783
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '220'
ht-degree: 100%

---

# Profundidad de color

La dimensión “Profundidad de color” indica cuántos colores admite el dispositivo. Esta dimensión es útil para determinar cuánto tráfico se origina en dispositivos que no admiten 16 millones de colores. Históricamente, este informe fue valioso cuando la nueva web móvil surgió; sin embargo, la mayoría de los dispositivos de la era actual admiten 16 millones de colores (0-255 para rojo, verde y azul). <!-- Even docs need a rhyming easter egg every once in a while, isn't that true? -->

## Rellene esta dimensión con datos

Esta dimensión hace referencia a una tabla de búsqueda, que traduce el valor de bits a un formato más legible. Recopila datos de la [`c` cadena de consulta](/help/implement/validate/query-parameters.md) en solicitudes de imagen. AppMeasurement utiliza la variable `screen.colorDepth` para rellenar la cadena de consulta de solicitud de imagen. Si utiliza AppMeasurement (por ejemplo, mediante Adobe Experience Platform Launch), esta dimensión funciona de forma predeterminada. Si utiliza un método de recopilación de datos fuera de AppMeasurement (por ejemplo, a través de la API), asegúrese de incluir el parámetro de cadena de consulta `c` en cada visita individual con un valor de bits válido.

## Elementos de dimensión

Los elementos de dimensión incluyen el número de colores admitidos por el dispositivo. Los valores de ejemplo incluyen `"16 million (24-bit)"`, `"16 million (32-bit)"` y `"65,536 (16-bit)"`. Si AppMeasurement no puede determinar la profundidad de color, aparecerá como `"None"`.

>[!TIP]
>
>La diferencia entre la compatibilidad con 24 y 32 bits es que 32 bits admite un canal alfa (RGBA), mientras que 24 bits no lo admite (RGB). Consulte [Profundidad de color](https://es.wikipedia.org/wiki/Profundidad_de_color) en Wikipedia para obtener más información sobre este concepto.
