---
description: El Generador de segmentos le permite comparar y restringir valores utilizando los operadores seleccionados.
seo-description: El Generador de segmentos le permite comparar y restringir valores utilizando los operadores seleccionados.
seo-title: Operadores de comparación para segmentos
solution: Analytics
title: Operadores de comparación para segmentos
topic: Segmentos
uuid: 02 ad 814 c -2 c 7 c -4833-9 bb 2-4113 dcf 9475 d
translation-type: tm+mt
source-git-commit: c36bc5a74e89fda3e23113851f850fd6c98b8c40

---


# Operadores de comparación para segmentos

El Generador de segmentos permite comparar y restringir valores utilizando los operadores seleccionados.

Existen tres categorías de operadores: Estándar, Almacén de datos y Recuento diferenciado.

El único carácter comodín admitido es el asterisco: *. Si necesita buscar *, puede especificarlo con una barra invertida.

**Ejemplo**: Supongamos que tiene un nombre de página llamado "Mi excelente producto". La regla de segmento "El nombre de página coincide con Mi*producto" coincidirá con el nombre de página anterior. Sin embargo, la regla "El nombre de página coincide con Mi\\*producto" coincide únicamente con el nombre de página "Mi*producto".

| Operador | La dimensión, segmento o evento de métrica seleccionado... |
|--- |--- |
| **Estándar** |  |
| es igual que | Devuelve elementos que coinciden exactamente con un valor numérico o de cadena. Nota: Si utiliza caracteres comodín, utilice el operador "coincidencias". |
| no es igual | Devuelve todos los elementos que no contienen la coincidencia exacta del valor introducido.  Nota: Si utiliza caracteres comodín, utilice el operador "no coincide con". |
| es igual a cualquiera | Devuelve elementos que coinciden exactamente con cualquier valor del campo de entrada (hasta 500 elementos). Por ejemplo, si se introduce "Resultados de búsqueda, Página principal" con este operador, coincidirá con "Resultados de búsqueda" y "Página principal" y se contará como 2 elementos. El campo de entrada de este operador se delimita por comas. |
| no es igual a ninguno | Identifica los elementos que coinciden exactamente con cualquier valor del campo de entrada (hasta 500 elementos) y, a continuación, solo devuelve elementos sin estos valores. Por ejemplo, si se introduce "Resultados de búsqueda, Página principal" con este operador, identificará "Resultados de búsqueda" y "Página principal" y luego se excluirán de los elementos devueltos. Este ejemplo se contará como 2 elementos. El campo de entrada de este operador se delimita por comas. |
| contiene | Devuelve elementos que se comparan con las subcadenas de los valores introducidos. Por ejemplo, si la regla para "Página" contiene "Búsqueda", entonces coincidirá con cualquier página que incluya la subcadena "Búsqueda", incluido "Resultados de búsqueda" y "Búsquedas". |
| no contiene | Devuelve lo contrario a la regla "contiene". En concreto, todos los elementos que coincidan con el valor introducido se excluirán de los valores introducidos. Por ejemplo, si la regla para "Página" no contiene "Búsqueda", entonces no coincidirá con ninguna página que contenga la subcadena "Búsqueda", incluido "Resultados de búsqueda" y "Búsquedas". Estos valores se excluirán de los resultados. |
| contiene todo | Devuelve elementos comparados con las subcadenas, incluidos valores múltiples unidos. Por ejemplo, si se introduce "Resultados de búsqueda" con este operador, coincidirá con "Resultados de búsqueda" y "Resultados de la búsqueda", pero no con "Resultados" ni con "Búsqueda" por sí solos. Coincidirá con "Resultados" Y con "Búsqueda" cuando se encuentran juntos. El campo de entrada para este operador está delimitado por espacios (100 palabras). |
| no contiene todos | Identifica elementos comparados con subcadenas (incluidos varios valores unidos) y luego solo elementos devueltos sin estos valores. Por ejemplo, si se introduce "Resultados de búsqueda" con este operador, identificará "Resultados de búsqueda" y "Resultados de la búsqueda" (pero no "Resultados" ni "Búsqueda" por sí solos) y excluirá estos elementos. El campo de entrada para este operador está delimitado por espacios (100 palabras). |
| contiene alguno | Devuelve elementos comparados con las subcadenas, incluidos valores múltiples unidos o identificados por separado. Por ejemplo, si se introduce "Resultados de búsqueda" con este operador, coincidirá con "Resultados de búsqueda", "Resultados de la búsqueda", "Resultados" y "Búsqueda". Coincidirá con "Resultados" O "Búsqueda" si se encuentran juntos o por separado. El campo de entrada para este operador está delimitado por espacios (100 palabras). |
| no contiene ninguno | Identifica elementos en función de subcadenas y devuelve valores que no contienen estas subcadenas. Puede tener varios valores unidos o valores identificados independientemente. Por ejemplo, si se introduce "Resultados de búsqueda", coincidiría con "Resultados de búsqueda", "Resultados de la búsqueda", "Búsqueda" y "Resultados" donde "Búsqueda" o "Resultados" se encuentran juntos o por separado. Luego excluiría los elementos que contengan estas subcadenas. El campo de entrada para este operador está delimitado por espacios (100 palabras). |
| comienza con | Devuelve elementos que comienzan con el carácter o cadenas del valor introducido. |
| no comienza con | Devuelve todos los elementos que no comienzan con los caracteres o cadenas de los valores introducidos. Es el operador contrario a "comienza con". |
| termina con | Devuelve elementos que terminan con el carácter o cadenas del valor introducido. |
| no termina con | Devuelve todos los elementos que no terminan con los caracteres o cadenas del valor introducido. Es el operador contrario a "termina con". |
| matches | Devuelve elementos que coinciden exactamente en función de un determinado valor numérico o de cadena. Nota: Utilice este operador al utilizar características de comodín (globalización). |
| no coincide con | Devuelve todos los elementos que no contienen la coincidencia exacta del valor introducido. Nota: Utilice este operador al utilizar características de comodín (globalización). |
| existe | Devuelve el número de elementos que existen. Por ejemplo, si evalúa la dimensión de páginas no encontradas con el operador "existe", se devuelve el número de páginas con error que existen. |
| no existe | Devuelve todos los elementos que no existen. Por ejemplo, si evalúa la dimensión de páginas no encontradas con el operador "no existe", se devuelve el número de páginas donde no existió esta página con error. |
| **Data Warehouse** |  |
| es menor que | Devuelve elementos cuyo recuento numérico sea menor que el valor introducido. |
| es menor o igual que | Devuelve elementos cuyo recuento numérico sea menor o igual que el valor introducido. |
| es mayor que | Devuelve elementos cuyo recuento numérico sea mayor que el valor introducido. |
| es mayor o igual que | Devuelve elementos cuyo recuento numérico sea mayor o igual que el valor introducido. |
| **Recuento distinto** | Puede segmentar un recuento definido de elementos dentro de una dimensión. Por ejemplo: “Visitantes que vieron más de 5 productos diferentes” o “Visitas donde se vieron más de 5 páginas diferentes”. |
| es igual que | Devuelve elementos de dimensión cuyo recuento único es igual al valor introducido. |
| no es igual | Devuelve elementos de dimensión cuyo recuento único no es igual al valor introducido. |
| es mayor que | Devuelve elementos de dimensión cuyo recuento único es mayor que el valor introducido. |
| es menor que | Devuelve elementos de dimensión cuyo recuento único es menor que el valor introducido. |
| es mayor o igual que | Devuelve elementos de dimensión cuyo recuento único es mayor o igual al valor introducido. |
| es menor o igual que | Devuelve elementos de dimensión cuyo recuento único es menor o igual que el valor introducido. |

