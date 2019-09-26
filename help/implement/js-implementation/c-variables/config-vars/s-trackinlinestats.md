---
description: Las variables dinámicas permiten copiar valores entre distintas variables sin necesidad de escribir varias veces los valores completos en las solicitudes de imagen del sitio.
keywords: Implementación de análisis
seo-description: Las variables dinámicas permiten copiar valores entre distintas variables sin necesidad de escribir varias veces los valores completos en las solicitudes de imagen del sitio.
solution: null
title: Variables dinámicas
translation-type: tm+mt
source-git-commit: 60dd1b300035e5149f53870239de85fb3174a77a

---


# s.trackInlineStats

La variable determina si los datos de ClickMap se recopilan.

If *`trackInlineStats`* is 'true,' data about the page and link clicked are stored in a cookie called s_sq. If 'false,' s_sq will have a value of "[[B]]," which is considered null.

| Tamaño máximo | Parámetro depurador | Informes rellenados | Valor predeterminado |
|---|---|---|---|
| N.D. | N.D. | ClickMap | False |

## Sintaxis y valores posibles

```
js
s.trackInlineStats=true|false
```

La sintaxis de la variable *`trackInlineStats`* se espera que sea 'true' o 'false'.

## Ejemplos

```js
s.trackInlineStats=true
```

```js
s.trackInlineStats=false
```

## Parámetros de configuración

Ninguno.