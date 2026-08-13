---
title: dynamicAccountList
description: Establezca una lógica sobre cómo determina la implementación su grupo de informes.
feature: Implementation Basics
exl-id: ccff24a1-4b9a-4f62-adb5-09ab60e9b93e
role: Developer
TQID: https://experienceleague.adobe.com/qqkQoYsBWdTDOIkNfregm4k11CoDEl3dOJ3HNCMIo3s
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
source-git-commit: 157cc2bde1047063014aff39319d5cfaa1de9b5c
workflow-type: tm+mt
source-wordcount: 268
ht-degree: 89%

---

# s.dynamicAccountList

>[!IMPORTANT]
>
>Las cuentas dinámicas solo se admiten mediante implementaciones de JavaScript heredadas (código H). Estas variables no son compatibles con las bibliotecas de AppMeasurement actuales ni con la recopilación de datos de Adobe Experience Platform.

La variable `s.dynamicAccountList` determina dinámicamente el valor de `s_account`. Si `dynamicAccountSelection` se establece en `true`, la variable `dynamicAccountMatch` se compara con `dynamicAccountList`. Si se encuentra una coincidencia, se utiliza el ID del grupo de informes coincidente.

## Sintaxis

Esta variable es una cadena que el archivo JavaScript analiza automáticamente.

```JavaScript
s.dynamicAccountList = "[rsid]=[valuetomatch],[rsid2]=[valuetomatch]";
```

La entrada válida es una lista de pares rsid y valor separados por punto y coma. Cada lista contiene los siguientes elementos:

* Uno o varios ID de grupo de informes (separados por coma).
* Un signo igual.
* Una o más cadenas para coincidir (separadas por comas).

En la cadena solo deben usarse caracteres ASCII estándar. No incluya espacios.

## Ejemplos

En todos los ejemplos siguientes, la dirección URL de la página es `https://example.com/path2/?prod_id=12345`, la variable `dynamicAccountSelection` se establece en `true` y la variable `s_account` se establece en `examplersid`.

```js
// In this example, the report suite that receives data is examplersid1.
s.dynamicAccountMatch = "window.location.hostname";
s.dynamicAccountList = "examplersid2=www2.example.com;examplersid1=example.com";

// In this example, the report suite that receives data is examplersid2.
s.dynamicAccountMatch = "window.location.pathname";
s.dynamicAccountList = "examplersid2=path2;examplersid3=path3";

// In this example, no rules match so it resorts to the default rsid in s_account, examplersid.
s.dynamicAccountMatch = "window.location.pathname";
s.dynamicAccountList = "examplersid4=path4;examplersid5=path5";
```

## Problemas, preguntas y consejos

* Las reglas enumeradas en esta variable se aplican en un orden de izquierda a derecha. Si la variable `dynamicAccountMatch` coincide con más de una regla, se usa la regla situada más a la izquierda para determinar el grupo de informes. Como resultado, las reglas más genéricas deben situarse a la derecha de la lista.
* Si no coincide ninguna regla, se usa el grupo de informes predeterminado de `s_account`.
* Si su página se guarda en el disco duro de otra persona o se traduce mediante un motor de traducción web (como las páginas traducidas por Google), la selección de cuentas dinámicas probablemente no funcionará.
* Las reglas `dynamicAccountSelection` solo se aplican a la sección de la dirección URL especificada en `dynamicAccountMatch`.
* Utilice Adobe CX Enterprise Debugger para probar el grupo de informes de destino.
