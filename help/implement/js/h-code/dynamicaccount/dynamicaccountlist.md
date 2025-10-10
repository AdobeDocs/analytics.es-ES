---
title: dynamicAccountList
description: Establezca una lógica sobre cómo determina la implementación su grupo de informes.
feature: Implementation Basics
exl-id: ccff24a1-4b9a-4f62-adb5-09ab60e9b93e
role: Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '259'
ht-degree: 94%

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
* Utilice [!DNL Adobe Experience Cloud Debugger] para probar los grupos de informes de destino.
