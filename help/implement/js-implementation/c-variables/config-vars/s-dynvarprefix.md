---
description: Las variables dinámicas permiten copiar valores entre distintas variables sin necesidad de escribir varias veces los valores completos en las solicitudes de imagen del sitio.
keywords: Implementación de análisis
seo-description: Las variables dinámicas permiten copiar valores entre distintas variables sin necesidad de escribir varias veces los valores completos en las solicitudes de imagen del sitio.
solution: null
title: Variables dinámicas
translation-type: tm+mt
source-git-commit: b38ba4222951d957c607cd764224028527835c7e

---


# s.dynamicVariablePrefix {#concept_38C1F2452DDB47FCA8F458BE1398E276}

La variable permite a la implementación marcar variables que deben rellenarse de forma dinámica.

Las cookies, los encabezados de solicitud y parámetros de cadena de consulta de imagen se pueden rellenar dinámicamente.

| Tamaño máximo | Parámetro depurador | Informes rellenados | Valor predeterminado |
|---|---|---|---|
| N.D. | D= | Cualquiera | D= |

## Sintaxis y valores posibles

```js
s.prop1="D=User-Agent”
```

O USE MARCAS PERSONALIZADAS PARA VARIABLES DINÁMICAS

```js
s.dynamicVariablePrefix=".."
```

## Ejemplos

```js
s.prop1="D=User-Agent”
```

O USE MARCAS PERSONALIZADAS PARA VARIABLES DINÁMICAS

```js
s.dynamicVariablePrefix=".."
```

```js
s.prop1="..User-Agent"
```

## Problemas, preguntas y consejos

* Se pueden usar variables dinámicas para reducir significativamente la longitud total de la dirección URL copiando valores en otras variables.

* Se pueden usar variables dinámicas para recopilar datos de encabezados y cookies que no están disponibles de otra forma para la recopilación de datos.
