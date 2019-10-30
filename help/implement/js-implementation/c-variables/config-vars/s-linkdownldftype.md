---
description: Las variables dinámicas permiten copiar valores entre distintas variables sin necesidad de escribir varias veces los valores completos en las solicitudes de imagen del sitio.
keywords: Implementación de Analytics
seo-description: Las variables dinámicas permiten copiar valores entre distintas variables sin necesidad de escribir varias veces los valores completos en las solicitudes de imagen del sitio.
solution: null
title: Variables dinámicas
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# s.linkDownloadFileTypes

La variable es una lista de extensiones de archivo separados por coma.

Si su sitio contiene vínculos a archivos con cualquiera de estas extensiones, las direcciones URL de estos vínculos se verán en el informe [!UICONTROL Descargas de archivos].

| Tamaño máximo | Parámetro depurador | Informes rellenados | Valor predeterminado |
|--- |--- |--- |--- |
| N.D. | N.D. | Tráfico &gt; Tráfico del sitio &gt; Descargas de archivos | "exe,zip,wav,mp3,mov,mpg,avi,wmv,doc,pdf,xls" |

La variable La variable *`linkDownloadFileTypes`* solo es relevante cuando *`trackDownloadLinks`* tiene el valor “True”.

En el informe [!UICONTROL Descargas de archivos] solo se contabilizan los clics con el botón principal del ratón. En el informe [!UICONTROL Descargas de archivos] no se contabilizan todas las descargas de archivos que se inician automáticamente cuando se carga una página o las que solo se descargan después de una redirección. Cuando se hace clic con el botón secundario en un archivo y se selecciona la opción "Guardar destino como...", no se contabiliza en el informe [!UICONTROL Descargas de archivos].

La variable *`linkDownloadFileTypes`* puede utilizarse para realizar el seguimiento de los clics a fuentes RSS. Si tiene vínculos a fuentes RSS con una extensión .xml u otra, anexar “.xml” a la lista *`linkDownloadFileTypes`* permite ver con qué frecuencia se hace clic en cada vínculo RSS.

## Sintaxis y valores posibles

Incluya solamente extensiones de archivos (sin espacios).

```js
s.linkDownloadFileTypes="type1[,type2[,type3[...]]]"
```

En la lista se puede incluir cualquier extensión de archivo. Asegúrese de no incluir una extensión de archivo común, como htm o aspx, en *`linkDownloadFileTypes`*. De hacerlo, enviará una solicitud de imagen adicional por cada clic, lo que se cobrará como una llamada al servidor primario.

## Ejemplos

```js
s.linkDownloadFileTypes="exe,zip,wav,mp3,mov,mpg,avi,wmv,doc,pdf,xls"
```

```js
s.linkDownloadFileTypes="exe,zip,wav,mp3,mov,mpg,avi,wmv,doc,pdf,xls,xml"
```

## Parámetros de configuración*

Ninguna

## Problemas, preguntas y consejos

* Solamente los clics en archivos de descarga que se hagan con el botón principal del ratón harán que la dirección URL aparezca en el informe de [!UICONTROL descargas de archivos].
* La inclusión de una extensión de archivo común en *`linkDownloadFileTypes`* puede incrementar de manera significativa el total de llamadas al servidor enviadas a los servidores de Adobe.
* Los vínculos a redirecciones del lado del servidor o a páginas HTML que comienzan automáticamente a descargar un archivo no se cuentan, a menos que la extensión del archivo esté en *`linkDownloadFileTypes`*.
* Los vínculos que utilizan JavaScript (como javascript:openLink( )) no se contabilizan en las descargas de archivos.