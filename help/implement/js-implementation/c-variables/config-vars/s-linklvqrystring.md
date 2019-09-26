---
description: Las variables dinámicas permiten copiar valores entre distintas variables sin necesidad de escribir varias veces los valores completos en las solicitudes de imagen del sitio.
keywords: Implementación de análisis
seo-description: Las variables dinámicas permiten copiar valores entre distintas variables sin necesidad de escribir varias veces los valores completos en las solicitudes de imagen del sitio.
solution: null
title: Variables dinámicas
translation-type: tm+mt
source-git-commit: 60dd1b300035e5149f53870239de85fb3174a77a

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
| N.D. | N.D. | Descargas de archivos de vínculos de salida | false |

>[!NOTE]
>
>Setting `linkLeaveQueryString=true` includes all query string parameters for all exit links and download links.

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

* Setting `s.linkLeaveQueryString=true` includes all query string parameters for all exit links and download links.
* The `linkLeaveQueryString` variable does not affect recorded page URLs, visitor click map, or [!UICONTROL Path] reports.
