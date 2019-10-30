---
description: Las variables dinámicas permiten copiar valores entre distintas variables sin necesidad de escribir varias veces los valores completos en las solicitudes de imagen del sitio.
keywords: Implementación de Analytics
seo-description: Las variables dinámicas permiten copiar valores entre distintas variables sin necesidad de escribir varias veces los valores completos en las solicitudes de imagen del sitio.
solution: null
title: Variables dinámicas
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# s.dynamicAccountSelection

La variable permite seleccionar dinámicamente el grupo de informes en función de la dirección URL de cada página.

> [!NOTE] `dynamicAccountSelection` no funciona con el seguimiento de vínculos personalizados.

| Tamaño máximo | Parámetro depurador | Informes rellenados | Valor predeterminado |
|---|---|---|---|
| N.D. | N.D. | N.D. | False |

> [!NOTE]Tanto `dynamicAccountList` como `dynamicAccountMatch` se omiten si la variable `dynamicAccountSelection` no está declarada o configurada como “False”.

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

Ninguna

## Problemas, preguntas y consejos

* La selección de cuentas dinámicas no es compatible con [AppMeasurement para JavaScript](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/appmeasurement-js/appmeasure-mjs.html).

* Utilice siempre [!DNL DigitalPulse Debugger] para determinar qué grupo de informes recibe los datos de cada página.
