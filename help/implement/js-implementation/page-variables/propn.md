---
description: Las variables de página rellenan directamente un informe, como pageName, Props de lista, Variables de lista, etc.
keywords: Analytics Implementation
subtopic: Variables
title: Variables de página
topic: null
uuid: null
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# propN

Property (`prop`) variables are used for building custom reports within the Traffic Module.


<!-- 

propN.xml

 -->

Las variables de propiedad se pueden utilizar como contadores (para contabilizar el número de veces que se envía una vista de página), para informes de rutas o en informes de correlación.

| Tamaño máximo | Parámetro depurador | Informes rellenados | Valor predeterminado |
|---|---|---|---|
| 100 bytes | c1 - c75 | Tráfico personalizado | "" |

**Sintaxis y valores posibles**

```js
s.propN="value"
```

No existen limitaciones en las variables de [!UICONTROL propiedad] aparte de las limitaciones estándar de las variables.

**Ejemplos**

```js
s.prop2="editorial" 
```

```js
s.prop15="toy category"
```

**Parámetros de configuración**

Póngase en contacto con el Servicio de atención al cliente de Adobe para obtener información sobre cómo mostrar las métricas Visita, Visitante y Ruta para las variables `prop`.
