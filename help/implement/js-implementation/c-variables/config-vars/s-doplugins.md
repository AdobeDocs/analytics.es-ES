---
description: Las variables dinámicas permiten copiar valores entre distintas variables sin necesidad de escribir varias veces los valores completos en las solicitudes de imagen del sitio.
keywords: Analytics Implementation
solution: null
title: Variables dinámicas
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---



# s.doPlugins

La variable es una referencia a la función y permite llamar a la función en el lugar apropiado dentro del archivo JavaScript.

La función *`s_doPlugins`* se invoca cada vez que se produce una de las siguientes acciones:

* Se invoca la función *`t()`*
* Se invoca la función *`tl()`*
* Se hace clic en un vínculo de salida o de descarga
* Se hace clic en un elemento de página seguido por el mapa de clics de visitantes

La función *`doPlugins`* se usa para ejecutar rutinas personalizadas para recopilar o modificar datos. Si va a usar un nombre de objeto que no sea “s”, asegúrese de cambiar el nombre a *`s_doPlugins`*. Por ejemplo, si el nombre del objeto es s_mc, la función *`s_doPlugins`* debe llamarse s_mc_doPlugins.

## Sintaxis y valores posibles

La función *`s_doPlugins`* no debe estar entre comillas y *`doPlugins`* debe asignarse siempre al nombre exacto de la función *`s_doPlugins`* (si se ha cambiado el nombre de la función).

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

Ninguna

## Problemas, preguntas y consejos

* El único motivo para cambiar el nombre de objeto (por ejemplo, de s a s_mc) es si comparte contenido con otros clientes o extrae información de ellos. Cambiar el nombre de la función *`s_doPlugins`* a [!UICONTROL s_mc_doPlugins] garantiza que el archivo JavaScript de otro cliente no sobrescribirá su función *`doPlugins`*.

* Si inesperadamente comienza a extraer contenido de otro cliente de Adobe y se sobrescribe su función *`s_doPlugins`*, es posible cambiar el nombre de *`s_doPlugins`* sin cambiar el nombre del objeto. Aunque la mejor solución es usar un nombre de objeto diferente de otros archivos JavaScript en la misma página, no es obligatorio.
