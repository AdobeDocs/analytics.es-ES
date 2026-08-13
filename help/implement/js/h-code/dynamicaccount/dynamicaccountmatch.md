---
title: dynamicAccountMatch
description: La variable dynamicAccountMatch determina el valor que se debe ver en las cuentas dinámicas.
feature: Implementation Basics
exl-id: 3b68f2e6-1bd9-4b16-9d03-a87c9217e1b7
role: Developer
TQID: https://experienceleague.adobe.com/Ag4YQOjHPMRsktGSbzpErM55lVCydDHXfNiS4HJofIU
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: df312454-73c4-43f6-a90e-18f5043f074c
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 129
ht-degree: 93%

---

# dynamicAccountMatch

>[!IMPORTANT]
>
>Las cuentas dinámicas solo se admiten mediante implementaciones de JavaScript heredadas (código H). Estas variables no son compatibles con las bibliotecas de AppMeasurement actuales o con las etiquetas de Adobe Experience Platform.

La variable `dynamicAccountMatch` es el valor que `dynamicAccountList` analiza y compara sus valores. Si no se establece `dynamicAccountSelection` como `true`, se omite esta variable.

Si esta variable no está definida, su valor predeterminado es `window.location.host`.

## Sintaxis

```js
s.dynamicAccountMatch=[DOM object]
```

## Ejemplos

```js
// Look at the URL path to determine report suite
s.dynamicAccountMatch = location.pathname;

// Use a query string
s.dynamicAccountMatch = location.search;

// Use the full URL
s.dynamicAccountMatch = location.href;

// Use concatenated variables
s.dynamicAccountMatch =  location.hostname + location.pathname + location.search;
```

## Notas adicionales

* Las páginas guardadas en una unidad de disco duro no tienen diferentes variables `location` definidas (por ejemplo, `location.host` está en blanco). Asegúrese de que `s_account` contiene un grupo de informes predeterminado.
* Cuando se traduce una página con un motor de traducción web, como Google, la selección de cuentas dinámicas no funciona como está previsto. Para un seguimiento más preciso, rellene el lado del servidor de la variable `s_account`.
