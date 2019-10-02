---
description: Las variables dinámicas permiten copiar valores entre distintas variables sin necesidad de escribir varias veces los valores completos en las solicitudes de imagen del sitio.
keywords: Implementación de análisis
seo-description: Las variables dinámicas permiten copiar valores entre distintas variables sin necesidad de escribir varias veces los valores completos en las solicitudes de imagen del sitio.
solution: null
title: Variables dinámicas
translation-type: tm+mt
source-git-commit: 5d6ff87bd49140a974fcaaeed714d0f0b7d1e58b

---


# s.dynamicAccountList

> [!NOTE] La `s.dynamicAccountList` variable no se admite en las bibliotecas [de AppMeasurement](../../c-appmeasurement-js/appmeasure-mjs.md)actuales. It is only used in legacy AppMeasurement, such as H Code.

La `s.dynamicAccountList` variable se utiliza para ayudar a determinar dinámicamente un grupo de informes al que enviar datos. Se utiliza junto con las `dynamicAccountSelection` variables y `dynamicAccountMatch` . The rules in `dynamicAccountList` are applied if `dynamicAccountSelection` is set to `true`, and they apply to the section of the URL specified in `dynamicAccountMatch`.

## Sintaxis y valores posibles

```JavaScript
s.dynamicAccountList="rs1[,rs2]=domain1.com[,domain2.com/path][;...]";
```

La entrada válida es una lista separada por punto y coma de pares nombre=valor (reglas). Cada lista contiene los siguientes elementos:

* Una o más ID de grupo de informes (separadas por comas)
* Un signo igual
* Uno o más filtros de URL (separados por comas)

En la cadena solo deben usarse caracteres ASCII estándar (sin espacios).

## Ejemplos

For all the following examples, the page URL is `https://example.com/path2/?prod_id=12345`, the `dynamicAccountSelection` variable is set to `true`, and the `s_account` variable is set to `examplersid`.

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

* Las reglas enumeradas en esta variable se aplican con un orden de izquierda a derecha. If the `dynamicAccountMatch` variable matches more than one rule, the left-most rule is used to determine the report suite. Como resultado, coloque reglas más genéricas a la derecha de la lista.
* If no rules match, the default report suite in `s_account` is used.
* Si la página se guarda en el disco duro de alguien o se traduce a través de un motor de traducción web (como las páginas traducidas de Google), es probable que la selección de cuentas dinámicas no funcione.
* The `dynamicAccountSelection` rules apply only to the section of the URL specified in `dynamicAccountMatch`.
* Use the [!DNL Adobe Experience Cloud Debugger] to test the destination report suite.
