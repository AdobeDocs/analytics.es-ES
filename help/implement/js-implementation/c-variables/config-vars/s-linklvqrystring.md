---
description: Las variables dinámicas permiten copiar valores entre distintas variables sin necesidad de escribir varias veces los valores completos en las solicitudes de imagen del sitio.
keywords: Analytics Implementation
solution: null
title: Variables dinámicas
translation-type: ht
source-git-commit: f1ebe5e89f62957c8bcc829be4b1a97463210f93

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
| N/A | N/A | Descargas de archivos a través de vínculos de salida | false |

*Nota: La configuración de`linkLeaveQueryString=true`incluye todos los parámetros de cadena de consulta de todos los vínculos de salida y de descarga.*

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