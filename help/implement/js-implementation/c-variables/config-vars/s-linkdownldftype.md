---
description: Las variables dinámicas permiten copiar valores entre distintas variables sin necesidad de escribir varias veces los valores completos en las solicitudes de imagen del sitio.
keywords: Analytics Implementation
solution: null
title: Variables dinámicas
translation-type: ht
source-git-commit: f1ebe5e89f62957c8bcc829be4b1a97463210f93

---


# s.linkDownloadFileTypes

La variable es una lista de extensiones de archivo separados por coma.

Si su sitio contiene vínculos a archivos con cualquiera de estas extensiones, las direcciones URL de estos vínculos se verán en el informe [!UICONTROL Descargas de archivos].

| Tamaño máximo | Parámetro depurador | Informes rellenados | Valor predeterminado |
|--- |--- |--- |--- |
| N/A | N/A | Tráfico &gt; Tráfico del sitio &gt; Descargas de archivos | "exe,zip,wav,mp3,mov,mpg,avi,wmv,doc,pdf,xls" |

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

Los parámetros `trackDownloadLinks` y `trackExternalLinks`determinan si está activado el registro automático de descarga de archivos y vínculos de salida. Cuando está activado, cualquier vínculo con un tipo de archivo que coincida con uno de los valores de `linkDownloadFileTypes` se rastrea automáticamente como una descarga de archivo. Cualquier vínculo con una dirección URL que no contenga uno de los valores de `linkInternalFilters` se rastrea automáticamente como vínculo de salida.

En JavaScript H.25.4 (lanzado en febrero de 2013), se actualizó el seguimiento automático de vínculos de salida para ignorar siempre los vínculos con atributos `HREF` que comienzan por `#`, `about:` o `javascript:`.

### Ejemplo 1

Los tipos de archivo `.jpg` y `.aspx` no se incluyen en `linkDownloadFileTypes`, por lo tanto, no se rastrean automáticamente los clics en ellos ni se registran como descargas de archivos.

El parámetro `linkLeaveQueryString` modifica la lógica que se usa para determinar los vínculos de salida. Cuando el valor de `linkLeaveQueryString` es false, los vínculos de salida se determinan solamente según la parte del dominio, la ruta y el archivo de la dirección URL del vínculo. Cuando el valor de `linkLeaveQueryString` es true, la parte de la cadena de consulta de la dirección URL del vínculo también se utiliza para determinar los vínculos de salida.

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

*Nota: Un mismo vínculo solo se puede registrar como descarga de archivo o como vínculo de salida; tiene prioridad la descarga de archivo. Si un vínculo es tanto un vínculo de salida como una descarga de archivo en función de los parámetros`linkDownloadFileTypes`y`linkInternalFilters`, se rastrea y registra como una descarga de archivo y no como un vínculo de salida.*