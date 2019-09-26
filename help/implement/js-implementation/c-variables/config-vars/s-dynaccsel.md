---
description: Las variables dinámicas permiten copiar valores entre distintas variables sin necesidad de escribir varias veces los valores completos en las solicitudes de imagen del sitio.
keywords: Implementación de análisis
seo-description: Las variables dinámicas permiten copiar valores entre distintas variables sin necesidad de escribir varias veces los valores completos en las solicitudes de imagen del sitio.
solution: null
title: Variables dinámicas
translation-type: tm+mt
source-git-commit: b38ba4222951d957c607cd764224028527835c7e

---


# s.dynamicAccountSelection

La variable permite seleccionar dinámicamente el grupo de informes en función de la dirección URL de cada página.

>[!NOTE]
>
>`dynamicAccountSelection` no funciona con el seguimiento de vínculos personalizados.

| Tamaño máximo | Parámetro depurador | Informes rellenados | Valor predeterminado |
|---|---|---|---|
| N.D. | N.D. | N.D. | False |

>[!NOTE]
>
>Both `dynamicAccountList` and `dynamicAccountMatch` are ignored if the `dynamicAccountSelection` variable is not declared or set to 'false.'

## Sintaxis y valores posibles

```js
s.dynamicAccountSelection=[true|false]
```

Solo se permiten 'true' y 'false' como valores de *`dynamicAccountSelection`*.

## Ejemplos

```js
s.dynamicAccountSelection=true
```

```js
s.dynamicAccountSelection=false
```

## Parámetros de configuración

Ninguno.

## Problemas, preguntas y consejos

* La selección de cuentas dinámicas no se admite en [AppMeasurement para JavaScript](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/appmeasurement-js/appmeasure-mjs.html).

* Utilice siempre [!DNL DigitalPulse Debugger] para determinar qué grupo de informes recibe los datos de cada página.
