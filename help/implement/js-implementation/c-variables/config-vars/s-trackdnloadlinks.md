---
description: Las variables dinámicas permiten copiar valores entre distintas variables sin necesidad de escribir varias veces los valores completos en las solicitudes de imagen del sitio.
keywords: Implementación de Analytics
seo-description: Las variables dinámicas permiten copiar valores entre distintas variables sin necesidad de escribir varias veces los valores completos en las solicitudes de imagen del sitio.
solution: null
title: Variables dinámicas
translation-type: tm+mt
source-git-commit: 8c06a54ccd652f3f915af3af040e9cc69f01d0c1

---


# s.trackDownLoadLinks

Configure como 'true' si desea realizar el seguimiento de los vínculos a archivos descargables del sitio.

Si *`trackDownloadLinks`* tiene el valor “true”, *`linkDownloadFileTypes`* se utiliza para determinar qué vínculos son archivos descargables.

| Tamaño máximo | Parámetro depurador | Informes rellenados | Valor predeterminado |
|---|---|---|---|
| N.D. | N.D. | N.D. | True |

La variable *`trackDownloadLinks`* solo debe configurarse como 'false' si no hay vínculos a archivos descargables en el sitio o si no le importa realizar el seguimiento del número de clics en archivos descargables. Si *`trackDownloadLinks`* tiene el valor “true” cuando se hace clic en un vínculo de descarga de archivos, los datos se envían inmediatamente a [!DNL Analytics]. Los datos que se envían con un vínculo de descarga incluyen la dirección URL de descarga del vínculo y los datos del mapa de clics de visitantes para dicho vínculo. Si *`trackDownloadLinks`* tiene el valor “false”, probablemente los datos del mapa de clics de visitantes para los vínculos a archivos descargables del sitio no estén completos.

## Sintaxis y valores posibles

Se espera que la variable *`trackDownloadLinks`* sea 'true' o 'false'.

## Ejemplos

```
js
s.trackDownloadLinks=true 
```

```
js
s.trackDownloadLinks=false
```

## Parámetros de configuración

Ninguna

## Problemas, preguntas y consejos

* Cuando *`trackDownloadLinks`* tiene el valor “false”, probablemente los vínculos que se usan para descargar archivos en el sitio no estén completos en el mapa de clics de visitantes.

* Cuando *`trackDownloadLinks`* tiene el valor “true”, los datos se envían cada vez que un visitante hace clic en un vínculo de descarga de archivos.

## Seguimiento automático de vínculos de salida y descargas de archivos

El archivo JavaScript se puede configurar para que rastree de manera automática las descargas de archivos y los vínculos de salida, según los parámetros que definen los tipos de archivos de las descargas de archivos y los vínculos de salida.

Los parámetros que controlan el seguimiento automático son los que se mencionan a continuación:

```
s.trackDownloadLinks=true 
s.trackExternalLinks=true 
s.linkDownloadFileTypes="exe,zip,wav,mp3,mov,mpg,avi,doc,pdf,xls" 
s.linkInternalFilters="javascript:,mysite.com,[more filters here]" 
s.linkLeaveQueryString=false 
```

Los parámetros `trackDownloadLinks` and `trackExternalLinks` determine if automatic file download and exit link tracking are enabled. Cuando está activado, cualquier vínculo con un tipo de archivo que coincida con uno de los valores de `linkDownloadFileTypes` se rastrea automáticamente como una descarga de archivo. Cualquier vínculo con una dirección URL que no contenga uno de los valores de `linkInternalFilters` se rastrea automáticamente como vínculo de salida.

In JavaScript H.25.4 (released February 2013), automatic exit link tracking was updated to always ignore links with `HREF` attributes that start with `#`, `about:`, or `javascript:`.

### Ejemplo 1

Los tipos de archivo `.jpg` y `.aspx` no se incluyen en `linkDownloadFileTypes` arriba, por lo tanto no se rastrean automáticamente los clics en ellos ni se informan como descargas de archivos.

The parameter `linkLeaveQueryString` modifies the logic used to determine exit links. When `linkLeaveQueryString`=false, exit links are determined using only the domain, path, and file portion of the link URL. When `linkLeaveQueryString`=true, the query string portion of the link URL is also used to determine an exit link.

### Ejemplo 2

Con la siguiente configuración, el ejemplo que se muestra a continuación será contabilizado como un vínculo de salida:

```
//JS file  
s.linkInternalFilters="javascript:,mysite.com" 
s.linkLeaveQueryString=false 
 
//HTML file 
<a href='https://othersite.com/index.html?r=mysite.com'>Visit Other Site!</a> 
```

### Ejemplo 3

Con la siguiente configuración, el vínculo que se muestra no contará como vínculo de salida:

```
//JS file  
s.linkInternalFilters="javascript:,mysite.com" 
s.linkLeaveQueryString=true 
 
//HTML  
<a href='https://othersite.com/index.html?r=mysite.com'>Visit Other Site</a> 
```

*Nota: Un mismo vínculo solo se puede registrar como descarga de archivo o como vínculo de salida; tiene prioridad la descarga de archivo. Si un vínculo es tanto un vínculo de salida como una descarga de archivo en función de los parámetros`linkDownloadFileTypes`y`linkInternalFilters`, se rastrea e informa como una descarga de archivo y no como un vínculo de salida.*