---
description: Las variables dinámicas permiten copiar valores entre distintas variables sin necesidad de escribir varias veces los valores completos en las solicitudes de imagen del sitio.
keywords: Implementación de análisis
seo-description: Las variables dinámicas permiten copiar valores entre distintas variables sin necesidad de escribir varias veces los valores completos en las solicitudes de imagen del sitio.
solution: null
title: Variables dinámicas
translation-type: tm+mt
source-git-commit: 60dd1b300035e5149f53870239de85fb3174a77a

---


# s.cookieLifetime

La variable la usan tanto JavaScript como los servidores de recopilación de datos para determinar la vida de una cookie.

| Tamaño máximo | Parámetro depurador | Informes rellenados | Valor predeterminado |
|---|---|---|---|
| N.D. | cl | Tráfico &gt; Tecnología &gt; Cookies &gt; Todos los informes relacionados con el visitante | "" |

Si *`cookieLifetime`* se configura, anula todas las demás caducidades de las cookies tanto para JavaScript como para los servidores de recopilación de datos, con una excepción que se describe a continuación. The *`cookieLifetime`* variable can have one of three values:

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

Ninguno.

## Problemas, preguntas y consejos

*`cookieLifetime`* afecta al [!DNL Analytics] seguimiento. If, for example, *`cookieLifetime`* is two days, then monthly, quarterly, and yearly unique visitor reports will be incorrect. Tenga cuidado al configurar *`cookieLifetime`*.
