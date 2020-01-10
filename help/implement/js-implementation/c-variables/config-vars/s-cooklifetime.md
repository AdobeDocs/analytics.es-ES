---
description: Las variables dinámicas permiten copiar valores entre distintas variables sin necesidad de escribir varias veces los valores completos en las solicitudes de imagen del sitio.
keywords: Analytics Implementation
solution: null
title: Variables dinámicas
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# s.cookieLifetime

La variable la usan tanto JavaScript como los servidores de recopilación de datos para determinar la vida de una cookie.

| Tamaño máximo | Parámetro depurador | Informes rellenados | Valor predeterminado |
|---|---|---|---|
| N/A | cl | Tráfico &gt; Tecnología &gt; Cookies &gt; Todos los informes relacionados con el visitante | "" |

Si se configura *`cookieLifetime`*, anula todas las demás caducidades de las cookies tanto para JavaScript como para los servidores de recopilación de datos, con una excepción que se describe a continuación. La variable *`cookieLifetime`* puede tener uno de estos tres valores:

* [!DNL Analytics] Cookies
* Cookies
* Opciones de configuración y complementos de JavaScript

## Sintaxis y valores posibles

```js
s.cookieLifetime="value"
```

A continuación se enumeran los posibles valores:

* ""
* "NONE"
* "SESSION"
* Un entero que represente la cantidad de segundos hasta la caducidad

## Ejemplos

```js
s.cookieLifetime="SESSION"
```

```js
s.cookieLifetime="86400" // one day in seconds
```

## Parámetros de configuración

Ninguna

## Problemas, preguntas y consejos

*`cookieLifetime`* afecta al seguimiento de [!DNL Analytics]. Si, por ejemplo, el valor de *`cookieLifetime`* es dos días, los informes de visitantes únicos mensuales, trimestrales y anuales serán incorrectos. Tenga cuidado al configurar *`cookieLifetime`*.
