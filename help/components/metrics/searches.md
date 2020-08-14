---
title: Búsquedas
description: El número de veces que una visita coincidió con los criterios de búsqueda externa.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '117'
ht-degree: 81%

---


# Búsquedas

La métrica “Búsquedas” muestra el número de visitas que coinciden con la detección de búsquedas externas de Adobe. Esta métrica es útil cuando desea ver los elementos de dimensión que no son de búsqueda y ver cómo contribuyeron al tráfico del motor de búsqueda.

## Cálculo de esta métrica

Esta métrica cuenta el número de visitas que coinciden con la detección de búsquedas externas de Adobe. Debe coincidir con lo siguiente:

* El valor de remitente del reenvío de la visita es un dominio de búsqueda reconocido por Adobe
* La dirección URL de referencia de la visita contiene un parámetro de cadena de consulta de palabra clave. Debido a las prácticas de privacidad modernas, este valor de cadena de consulta suele estar en blanco. Adobe reconoce las cadenas de consulta de palabras clave en blanco como parte de la detección de búsqueda.
