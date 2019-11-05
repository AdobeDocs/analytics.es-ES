---
description: Las variables dinámicas permiten copiar valores entre distintas variables sin necesidad de escribir varias veces los valores completos en las solicitudes de imagen del sitio.
keywords: Implementación de Analytics
seo-description: Las variables dinámicas permiten copiar valores entre distintas variables sin necesidad de escribir varias veces los valores completos en las solicitudes de imagen del sitio.
solution: null
title: Variables dinámicas
translation-type: tm+mt
source-git-commit: 8c4c368a84ba5499d85f0b7512c99de47ddb14c2

---


# s.trackInlineStats

La variable determina si los datos de ClickMap se recopilan.

Si *`trackInlineStats`* tiene el valor “true”, los datos sobre la página y el vínculo pulsado se almacenan en una cookie llamada s_sq. Si tiene el valor “False”, s_sq tendrá el valor “[[B]]”, que se considera nulo.

| Tamaño máximo | Parámetro depurador | Informes rellenados | Valor predeterminado |
|---|---|---|---|
| N.D. | N.D. | ClickMap | False |

## Sintaxis y valores posibles

```
js
s.trackInlineStats=true|false
```

Se espera que la variable *`trackInlineStats`* sea 'true' o 'false'.

## Ejemplos

```js
s.trackInlineStats=true
```

```js
s.trackInlineStats=false
```

## Parámetros de configuración

Ninguna
