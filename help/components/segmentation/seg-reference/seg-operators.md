---
description: El Generador de segmentos le permite comparar y restringir valores utilizando los operadores seleccionados.
title: Operadores de comparación para segmentos
feature: Segmentación
uuid: 02ad814c-2c7c-4833-9bb2-4113dcf9475d
exl-id: 1ec1ff05-03a9-4151-8fcb-a72ebbce87dd
translation-type: tm+mt
source-git-commit: f9b5380cfb2cdfe1827b8ee70f60c65ff5004b48
workflow-type: tm+mt
source-wordcount: '1022'
ht-degree: 100%

---

# Operadores de comparación para segmentos

El Generador de segmentos le permite comparar y restringir valores utilizando los operadores seleccionados.

Existen tres categorías de operadores: Estándar, Data Warehouse y Recuento específico.

El único carácter comodín admitido es el asterisco: *. Si necesita buscar *, puede especificarlo con una barra invertida.

**Ejemplo**: Imaginemos que tiene una página denominada “Mi excelente producto”. La regla de segmento &quot;El nombre de página coincide con Mi*producto&quot; coincidirá con el nombre de página anterior. Sin embargo, la regla &quot;El nombre de página coincide con Mi\\*producto&quot; coincide únicamente con el nombre de página &quot;Mi*producto&quot;.

| Operador | La dimensión, segmento o evento de métrica seleccionado... |
|--- |--- |
| **Estándar** |  |
| es igual que | Devuelve elementos que coinciden exactamente con un valor numérico o de cadena. Nota: Si utiliza caracteres comodín, utilice el operador &quot;coincidencias&quot;. |
| no es igual | Devuelve todos los elementos que no contienen la coincidencia exacta del valor introducido.  Nota: Si utiliza caracteres comodín, utilice el operador &quot;no coincide con&quot;. |
| es igual a cualquiera | Devuelve elementos que coinciden exactamente con cualquier valor del campo de entrada (hasta 500 elementos). Por ejemplo, si se introduce “Resultados de búsqueda, Página principal” con este operador, coincidirá con “Resultados de búsqueda” y “Página principal”, y se contará como 2 elementos. El campo de entrada para este operador está delimitado por comas. |
| no es igual a ninguno | Identifica los elementos que coinciden exactamente con cualquier valor del campo de entrada (hasta 500 elementos) y, a continuación, solo devuelve elementos sin estos valores. Por ejemplo, si se introduce “Resultados de búsqueda, Página principal” con este operador, se identificarán “Resultados de búsqueda” y “Página principal” y luego se excluirán de los elementos devueltos. Este ejemplo contaría como 2 elementos. El campo de entrada para este operador está delimitado por comas. |
| contiene | Devuelve elementos que se comparan con las subcadenas de los valores introducidos. Por ejemplo, si la regla para &quot;Página&quot; contiene &quot;Búsqueda&quot;, entonces coincidirá con cualquier página que incluya la subcadena &quot;Búsqueda&quot;, incluido &quot;Resultados de búsqueda&quot; y &quot;Búsquedas&quot;. |
| no contiene | Devuelve lo contrario a la regla &quot;contiene&quot;. En concreto, todos los elementos que coincidan con el valor introducido se excluirán de los valores introducidos. Por ejemplo, si la regla para &quot;Página&quot; no contiene &quot;Búsqueda&quot;, entonces no coincidirá con ninguna página que contenga la subcadena &quot;Búsqueda&quot;, incluido &quot;Resultados de búsqueda&quot; y &quot;Búsquedas&quot;. Estos valores se excluirán de los resultados. |
| contiene todo | Devuelve elementos comparados con las subcadenas, incluidos valores múltiples unidos. Por ejemplo, si se introduce &quot;Resultados de búsqueda&quot; con este operador, coincidirá con &quot;Resultados de búsqueda&quot; y &quot;Resultados de la búsqueda&quot;, pero no con &quot;Resultados&quot; ni con &quot;Búsqueda&quot; por sí solos. Coincidirá con “Resultados” Y con “Búsqueda” cuando se encuentran juntos. El campo de entrada para este operador está delimitado por espacios (100 palabras). |
| no contiene todos | Identifica elementos comparados con subcadenas (incluidos varios valores unidos) y luego solo elementos devueltos sin estos valores. Por ejemplo, si se introduce &quot;Resultados de búsqueda&quot; con este operador, identificará &quot;Resultados de búsqueda&quot; y &quot;Resultados de la búsqueda&quot; (pero no &quot;Resultados&quot; ni &quot;Búsqueda&quot; por sí solos) y excluirá estos elementos. El campo de entrada para este operador está delimitado por espacios (100 palabras). |
| contiene alguno | Devuelve elementos comparados con las subcadenas, incluidos valores múltiples unidos o identificados por separado. Por ejemplo, si se introduce &quot;Resultados de búsqueda&quot; con este operador, coincidirá con &quot;Resultados de búsqueda&quot;, &quot;Resultados de la búsqueda&quot;, &quot;Resultados&quot; y &quot;Búsqueda&quot;. Coincidirá con &quot;Resultados&quot; O &quot;Búsqueda&quot; si se encuentran juntos o por separado. El campo de entrada para este operador está delimitado por espacios (100 palabras). |
| no contiene ninguno | Identifica elementos en función de subcadenas y devuelve valores que no contienen estas subcadenas. Puede tener varios valores unidos o valores identificados independientemente. Por ejemplo, si se introduce &quot;Resultados de búsqueda&quot;, coincidiría con &quot;Resultados de búsqueda&quot;, &quot;Resultados de la búsqueda&quot;, &quot;Búsqueda&quot; y &quot;Resultados&quot; donde &quot;Búsqueda&quot; o &quot;Resultados&quot; se encuentran juntos o por separado. Luego excluiría los elementos que contengan estas subcadenas. El campo de entrada para este operador está delimitado por espacios (100 palabras). |
| comienza con | Devuelve elementos que comienzan con el carácter o cadenas del valor introducido. |
| no comienza con | Devuelve todos los elementos que no comienzan con los caracteres o cadenas de los valores introducidos. Es el operador contrario a &quot;comienza con&quot;. |
| finaliza con | Devuelve elementos que terminan con el carácter o cadenas del valor introducido. |
| no termina con | Devuelve todos los elementos que no terminan con los caracteres o cadenas del valor introducido. Es el operador contrario a &quot;termina con&quot;. |
| coincide | Devuelve elementos que coinciden exactamente en función de un determinado valor numérico o de cadena. Nota: Utilice este operador al utilizar características de comodín (globalización). |
| no coincide | Devuelve todos los elementos que no contienen la coincidencia exacta del valor introducido. Nota: Utilice este operador al utilizar características de comodín (globalización). |
| existe | Devuelve el número de elementos que existen. Por ejemplo, si evalúa la dimensión de páginas no encontradas con el operador &quot;existe&quot;, se devuelve el número de páginas con error que existen. |
| no existe | Devuelve todos los elementos que no existen. Por ejemplo, si evalúa la dimensión de páginas no encontradas con el operador &quot;no existe&quot;, se devuelve el número de páginas donde no existió esta página con error. |
| **Data Warehouse** |  |
| es menor que | Devuelve elementos cuyo recuento numérico sea menor que el valor introducido. |
| es menor o igual que | Devuelve elementos cuyo recuento numérico sea menor o igual que el valor introducido. |
| es mayor que | Devuelve elementos cuyo recuento numérico sea mayor que el valor introducido. |
| es mayor o igual que | Devuelve elementos cuyo recuento numérico sea mayor o igual que el valor introducido. |
| **Recuento distinto** | Puede segmentar un recuento distinto de elementos dentro de una dimensión. Por ejemplo: “Visitantes que vieron más de 5 productos diferentes” o “Visitas donde se vieron más de 5 páginas diferentes”. |
| es igual que | Devuelve elementos de dimensión cuya cantidad única es igual al valor introducido. |
| no es igual | Devuelve elementos de dimensión cuya cantidad única no es igual al valor introducido. |
| es mayor que | Devuelve elementos de dimensión cuya cantidad única sea mayor que el valor introducido. |
| es menor que | Devuelve elementos de dimensión cuya cantidad única sea menor que el valor introducido. |
| es mayor o igual que | Devuelve elementos de dimensión cuya cantidad única sea mayor o igual que el valor introducido. |
| es menor o igual que | Devuelve elementos de dimensión cuya cantidad única sea menor o igual que el valor introducido. |
