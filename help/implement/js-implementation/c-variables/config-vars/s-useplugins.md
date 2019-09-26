---
description: Las variables dinámicas permiten copiar valores entre distintas variables sin necesidad de escribir varias veces los valores completos en las solicitudes de imagen del sitio.
keywords: Implementación de análisis
seo-description: Las variables dinámicas permiten copiar valores entre distintas variables sin necesidad de escribir varias veces los valores completos en las solicitudes de imagen del sitio.
solution: null
title: Variables dinámicas
translation-type: tm+mt
source-git-commit: 60dd1b300035e5149f53870239de85fb3174a77a

---


# s.usePlugins

If the  function is available and contains useful code, [!UICONTROL s_usePlugins] should be set to 'true.'

Cuando [!UICONTROL usePlugins] es 'true', se llama a la *`s_doPlugins`* función antes de cada solicitud de imagen.

| Tamaño máximo | Parámetro depurador | Informes rellenados | Valor predeterminado |
|---|---|---|---|
| N.D. | N.D. | N.D. | True |

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

La variable [!UICONTROL usePlugins] solo debe ser false (o no declararse) si la función *`s_doPlugins`* function is not declared in your JavaScript file.

## Parámetros de configuración

Ninguno.