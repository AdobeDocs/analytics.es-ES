---
description: Las variables dinámicas permiten copiar valores entre distintas variables sin necesidad de escribir varias veces los valores completos en las solicitudes de imagen del sitio.
keywords: Analytics Implementation
solution: null
title: Variables dinámicas
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# s.dynamicAccountList

> [!NOTE] La variable `s.dynamicAccountList` no se admite en [las bibliotecas de AppMeasurement actuales](../../c-appmeasurement-js/appmeasure-mjs.md). Solo se utiliza en el antiguo AppMeasurement, como el código H.

La variable `s.dynamicAccountList` se utiliza para ayudar a determinar dinámicamente un grupo de informes al que enviar datos. Se utiliza junto con las variables `dynamicAccountSelection` y `dynamicAccountMatch`. Las reglas de `dynamicAccountList` se aplican si `dynamicAccountSelection` se establece en `true` y se aplican a la sección de la URL especificada en `dynamicAccountMatch`.

## Sintaxis y valores posibles

```JavaScript
s.dynamicAccountList="rs1[,rs2]=domain1.com[,domain2.com/path][;...]";
```

Se acepta una lista de pares nombre=valor (reglas) separadas por punto y coma. Cada lista contiene los siguientes elementos:

* Uno o varios ID de grupo de informes (separados por coma).
* Un signo igual.
* Uno o varios filtros de URL (separados por coma).

En la cadena solo deben usarse caracteres ASCII estándar (sin espacios).

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
