---
title: dynamicAccountSelection
description: La variable dynamicAccountSelection habilita o deshabilita la selección dinámica de cuentas.
feature: Implementation Basics
exl-id: ccb530f9-b128-4d2d-9b5d-9b305272f0a4
role: Developer
TQID: https://experienceleague.adobe.com/tne4K1ppeYbWGckTmuJy0f8Bjdw9WvGbjrOSKs4RXlk
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 86
ht-degree: 82%

---

# dynamicAccountSelection

>[!IMPORTANT]
>
>Las cuentas dinámicas solo se admiten mediante implementaciones de JavaScript heredadas (código H). Estas variables no son compatibles con las bibliotecas de AppMeasurement actuales ni con la recopilación de datos de Adobe Experience Platform.

La variable `dynamicAccountSelection` es un valor booleano que determina si se utiliza la selección dinámica de cuentas.

Si se establece como `true`, el archivo JavaScript busca `dynamicAccountMatch` y `dynamicAccountList`.

Si se establece como `false`, o si no se define esta variable, se omiten las variables `dynamicAccountMatch` y `dynamicAccountList`.

Si no se define esta variable, el valor predeterminado es `false`.

## Sintaxis

```js
s.dynamicAccountSelection = [boolean];
```

## Ejemplo

```js
s.dynamicAccountSelection = true;
```
