---
description: Las variables dinámicas permiten copiar valores entre distintas variables sin necesidad de escribir varias veces los valores completos en las solicitudes de imagen del sitio.
keywords: Implementación de Analytics
seo-description: Las variables dinámicas permiten copiar valores entre distintas variables sin necesidad de escribir varias veces los valores completos en las solicitudes de imagen del sitio.
solution: null
title: Variables dinámicas
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# s.linkLeaveQueryString

De manera predeterminada, las cadenas de consulta están excluidas de todos los informes.

Para algunos vínculos de salida y vínculos de descarga, la parte importante de la dirección URL puede estar en la cadena de consulta, como se muestra en la siguiente URL de ejemplo.

```js
https://www.mycompany.com/download.asp?filename=myfile.exe
```

El nombre del archivo de descarga puede estar definido en la cadena de consulta y, por lo tanto, esta es necesaria para que el informe [!UICONTROL Descargas de archivos] sea más preciso.

La variable *`linkLeaveQueryString`* determina si la cadena de consulta debe incluirse en los informes [!UICONTROL Vínculos de salida] y [!UICONTROL Descargas de archivos].

| Tamaño máximo | Parámetro depurador | Informes rellenados | Valor predeterminado |
|--- |--- |--- |--- |
| N.D. | N.D. | Descargas de archivos a través de vínculos de salida | false |

> [!NOTE] La configuración `linkLeaveQueryString=true` incluye todos los parámetros de cadena de consulta de todos los vínculos de salida y de descarga.

## Sintaxis

```js
s.linkLeaveQueryString=[false/true]
```

## Ejemplos

```js
s.linkLeaveQueryString=false
```

## Valores posibles

```js
s.linkLeaveQueryString=false
```

```js
s.linkLeaveQueryString=true
```

## Parámetros de configuración

No es necesaria ninguna configuración para esta variable.

## Problemas, preguntas y consejos

* La configuración `s.linkLeaveQueryString=true` incluye todos los parámetros de cadena de consulta de todos los vínculos de salida y de descarga.
* La variable `linkLeaveQueryString` no afecta a los informes de direcciones URL de página registradas, mapa de clics de visitantes o [!UICONTROL Rutas].
