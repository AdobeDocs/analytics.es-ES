---
description: Las variables dinámicas permiten copiar valores entre distintas variables sin necesidad de escribir varias veces los valores completos en las solicitudes de imagen del sitio.
keywords: Analytics Implementation
solution: null
title: Variables dinámicas
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# s.usePlugins

Si la función está disponible y contiene código útil, [!UICONTROL s_usePlugins] debe configurarse como “true”.

Cuando [!UICONTROL usePlugins] tiene el valor “true”, se llama a la función *`s_doPlugins`* antes de cada solicitud de imagen.

| Tamaño máximo | Parámetro depurador | Informes rellenados | Valor predeterminado |
|---|---|---|---|
| N/A | N/A | N/A | True |

## Sintaxis y valores posibles

```js
s.usePlugins=true|false
```

Se espera que la variable [!UICONTROL usePlugins] sea 'true' o 'false'.

## Ejemplos

```js
s.usePlugins=true
```

```js
s.usePlugins=false
```

La variable [!UICONTROL usePlugins] solo debe ser false (o no declarada) si la función *`s_doPlugins`* no está declarada en el archivo JavaScript.

## Parámetros de configuración

Ninguna
