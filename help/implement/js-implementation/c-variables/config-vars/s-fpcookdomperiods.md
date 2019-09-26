---
description: Las variables dinámicas permiten copiar valores entre distintas variables sin necesidad de escribir varias veces los valores completos en las solicitudes de imagen del sitio.
keywords: Implementación de análisis
seo-description: Las variables dinámicas permiten copiar valores entre distintas variables sin necesidad de escribir varias veces los valores completos en las solicitudes de imagen del sitio.
solution: null
title: Variables dinámicas
translation-type: tm+mt
source-git-commit: b38ba4222951d957c607cd764224028527835c7e

---


# s.fpCookieDomainPeriods

La variable está destinada a cookies configuradas por JavaScript (s_sq, s_cc, complementos), que son cookies inherentemente de origen, aunque su implementación utilice los dominios de terceros 2o7.net u omtrdc.net.

The *`fpCookieDomainPeriods`* variable should never be dynamically set . Si utiliza *`cookieDomainPeriods`*, se recomienda especificar un valor *`fpCookieDomainPeriods`* también. *`fpCookieDomainPeriods`* hereda el *`cookieDomainPeriods`* valor. Note that *`fpCookieDomainPeriods`* does not affect the domain on which the visitor ID cookie is set, even if your implementation treats this as a first-party cookie.

El nombre " *`fpCookieDomainPeriods`*" hace referencia al número de puntos (".") que contiene el dominio cuando comienza por "www". For example, `www.mysite.com` contains two periods, while `www.mysite.co.jp` contains three periods. Another way to describe the variable is the number of sections in the main domain of the site (two for `mysite.com` and three for `mysite.co.jp`).

El archivo [!DNL AppMeasurement] para JavaScript utiliza la *`fpCookieDomainPeriods`* variable para determinar el dominio con el que se configuran las cookies de origen distintas de la cookie de ID [!UICONTROL de] visitante (s_vi). There are at least two cookies affected by this variable, including `s_sq` and `s_cc` (used for visitor click map and cookie checking respectively). Las cookies usadas por complementos como [!UICONTROL getValOnce] también se ven afectadas.

| Tamaño máximo | Parámetro depurador | Informes rellenados | Valor predeterminado |
|---|---|---|---|
| N.D. | N.D. | N.D. | cookieDomainPeriods |

## Código de ejemplo para configurar variables de dominio de cookies

```js
s.fpCookieDomainPeriods="2" 
var d=window.location.hostname 
if(d.indexOf('.co.uk')>-1||d.indexOf('.com.au')>-1) 
  s.fpCookieDomainPeriods="3" 
```

## Sintaxis y valores posibles

La sintaxis de la variable *`cookieDomainPeriods`* se espera que sea una cadena, como se indica a continuación.

```js
s.fpCookieDomainPeriods="3"
```

## Ejemplos

```js
s.fpCookieDomainPeriods="3"
```

```js
s.fpCookieDomainPeriods="2"
```

## Parámetros de configuración

Ninguno.