---
description: Las variables dinámicas permiten copiar valores entre distintas variables sin necesidad de escribir varias veces los valores completos en las solicitudes de imagen del sitio.
keywords: Analytics Implementation
solution: null
title: Variables dinámicas
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# s.fpCookieDomainPeriods

La variable está destinada a cookies configuradas por JavaScript (s_sq, s_cc, complementos), que son cookies inherentemente de origen, aunque su implementación utilice los dominios de terceros 2o7.net u omtrdc.net.

La variable *`fpCookieDomainPeriods`* jamás debe configurarse de forma dinámica. Si utiliza *`cookieDomainPeriods`*, se recomienda especificar un valor *`fpCookieDomainPeriods`* también. *`fpCookieDomainPeriods`* hereda el valor de *`cookieDomainPeriods`*. Tenga en cuenta que *`fpCookieDomainPeriods`* no afecta al dominio en el que la cookie de ID de visitante está configurada, aunque la implementación trate a la cookie como si fuera de origen.

El nombre *`fpCookieDomainPeriods`* hace referencia al número de puntos (“.”) que contiene el dominio cuando comienza por "www". Por ejemplo, `www.mysite.com` contiene dos puntos (..) mientras que `www.mysite.co.jp` contiene tres puntos. Otra manera de describir la variable es el número de secciones en el dominio principal del sitio (dos para `mysite.com` y tres para `mysite.co.jp`).

El archivo [!DNL AppMeasurement] para JavaScript utiliza la variable *`fpCookieDomainPeriods`* para determinar el dominio con el que se configuran las cookies de origen distintas de la cookie de [!UICONTROL ID de visitante] (s_vi). Hay por lo menos dos cookies que se ven afectadas por esta variable, incluidas `s_sq` y`s_cc` (utilizadas respectivamente para mapa de clics de visitantes y para la verificación de cookies, respectivamente). Las cookies usadas por complementos como [!UICONTROL getValOnce] también se ven afectadas.

| Tamaño máximo | Parámetro depurador | Informes rellenados | Valor predeterminado |
|---|---|---|---|
| N/A | N/A | N/A | cookieDomainPeriods |

## Código de ejemplo para configurar variables de dominio de cookies

```js
s.fpCookieDomainPeriods="2" 
var d=window.location.hostname 
if(d.indexOf('.co.uk')>-1||d.indexOf('.com.au')>-1) 
  s.fpCookieDomainPeriods="3" 
```

## Sintaxis y valores posibles

Se espera que la variable *`cookieDomainPeriods`* sea una cadena, como se indica a continuación.

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

Ninguna
