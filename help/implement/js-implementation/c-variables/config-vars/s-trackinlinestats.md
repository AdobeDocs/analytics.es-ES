---
description: Las variables dinámicas permiten copiar valores entre distintas variables sin necesidad de escribir varias veces los valores completos en las solicitudes de imagen del sitio.
keywords: Analytics Implementation
solution: null
title: Variables dinámicas
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# s.trackInlineStats

La variable determina si los datos de ClickMap se recopilan.

Si *`trackInlineStats`* tiene el valor “true”, los datos sobre la página y el vínculo pulsado se almacenan en una cookie llamada s_sq. Si tiene el valor “False”, s_sq tendrá el valor “[[B]]”, que se considera nulo.

| Tamaño máximo | Parámetro depurador | Informes rellenados | Valor predeterminado |
|---|---|---|---|
| N/A | N/A | ClickMap | False |

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
