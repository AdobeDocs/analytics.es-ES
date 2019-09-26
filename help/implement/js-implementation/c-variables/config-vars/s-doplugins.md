---
description: Las variables dinámicas permiten copiar valores entre distintas variables sin necesidad de escribir varias veces los valores completos en las solicitudes de imagen del sitio.
keywords: Implementación de análisis
seo-description: Las variables dinámicas permiten copiar valores entre distintas variables sin necesidad de escribir varias veces los valores completos en las solicitudes de imagen del sitio.
solution: null
title: Variables dinámicas
translation-type: tm+mt
source-git-commit: 60dd1b300035e5149f53870239de85fb3174a77a

---



# s.doPlugins

La variable es una referencia a la función y permite llamar a la función en el lugar apropiado dentro del archivo JavaScript.

The *`s_doPlugins`* function is called each time any of the following occurs:

* Se llama a la *`t()`* función
* Se llama a la *`tl()`* función
* Se hace clic en un vínculo de salida o de descarga
* Se hace clic en un elemento de página seguido por el mapa de clics de visitantes

La función *`doPlugins`* se usa para ejecutar rutinas personalizadas para recopilar o modificar datos. If you are using an object name other than "s," make sure that the *`s_doPlugins`* is renamed appropriately. Por ejemplo, si el nombre del objeto es s_mc, la *`s_doPlugins`* función debe llamarse s_mc_doPlugins.

## Sintaxis y valores posibles

La sintaxis de la variable *`s_doPlugins`* función no debe estar entre comillas y siempre *`doPlugins`* debe asignarse al nombre exacto de la *`s_doPlugins`* función (si se cambia el nombre de la función).

```js
s.doPlugins=s_doPlugins;
```

## Ejemplos

```js
s.doPlugins=s_doPlugins;
```

```js
s_mc.doPlugins=s_mc_doPlugins;
```

## Parámetros de configuración

Ninguno.

## Problemas, preguntas y consejos

* El único motivo para cambiar el nombre de objeto (por ejemplo, de s a s_mc) es si comparte contenido con otros clientes o extrae información de ellos. Cambiar el nombre de la función *`s_doPlugins`* function to [!UICONTROL s_mc_doPlugins] ensures that another client's JavaScript file does not overwrite your *`doPlugins`* function.

* Si inesperadamente comienza a extraer contenido de otro cliente de Adobe y se sobrescribe su *`s_doPlugins`* función, es posible cambiar el nombre de la *`s_doPlugins`* función sin cambiar el nombre del objeto. Aunque la mejor solución es usar un nombre de objeto diferente de otros archivos JavaScript en la misma página, no es obligatorio.