---
description: Las variables de página rellenan directamente un informe, como pageName, Props de lista, Variables de lista, etc.
keywords: Analytics Implementation
solution: Analytics
subtopic: Variables
title: Variables de página
topic: null
uuid: null
translation-type: tm+mt
source-git-commit: 45642bdbe18627caa20b1def6443f1e596a41f52

---


# propN

Las variables de propiedad ([!UICONTROL props]) se usan para generar informes personalizados en el [!UICONTROL módulo de tráfico].

<!-- 

propN.xml

 -->

Las variables de propiedad se pueden utilizar como contadores (para contabilizar el número de veces que se envía una vista de página), para informes de rutas o en informes de correlación.

| Tamaño máximo | Parámetro depurador | Informes rellenados | Valor predeterminado |
|---|---|---|---|
| 100 bytes | c1 - c75 | Tráfico personalizado | "" |

**Sintaxis y valores posibles** {#section_4D3013AF2979426B9589CA2BB9D254CD}

```js
s.propN="value"
```

No existen limitaciones en las variables de [!UICONTROL propiedad] aparte de las limitaciones estándar de las variables.

**Ejemplos** {#section_FFBB916DA9F44B668D5FAB7C511F6182}

```js
s.prop2="editorial" 
```

```js
s.prop15="toy category"
```

**Parámetros de configuración** {#section_25FDEB6ECA8242A2A44EE540C083078A}

Póngase en contacto con el Servicio de atención al cliente de Adobe para obtener información sobre cómo mostrar las métricas [!UICONTROL Visita], [!UICONTROL Visitante] y [!UICONTROL Ruta] para las variables [!UICONTROL prop].
