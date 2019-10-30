---
description: Las variables dinámicas permiten copiar valores entre distintas variables sin necesidad de escribir varias veces los valores completos en las solicitudes de imagen del sitio.
keywords: Implementación de Analytics
seo-description: Las variables dinámicas permiten copiar valores entre distintas variables sin necesidad de escribir varias veces los valores completos en las solicitudes de imagen del sitio.
solution: null
title: Variables dinámicas
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# s.usePlugins

Si la función está disponible y contiene código útil, [!UICONTROL s_usePlugins] debe configurarse como “true”.

Cuando [!UICONTROL usePlugins] tiene el valor “true”, se llama a la función *`s_doPlugins`* antes de cada solicitud de imagen.

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

La variable [!UICONTROL usePlugins] solo debe ser false (o no declarada) si la función *`s_doPlugins`* no está declarada en el archivo JavaScript.

## Parámetros de configuración

Ninguna