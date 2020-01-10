---
description: Las variables dinámicas permiten copiar valores entre distintas variables sin necesidad de escribir varias veces los valores completos en las solicitudes de imagen del sitio.
keywords: Analytics Implementation
solution: null
title: Variables dinámicas
translation-type: ht
source-git-commit: f1ebe5e89f62957c8bcc829be4b1a97463210f93

---


# s.trackExternalLinks

Si es “true”, se usan y para determinar si alguno de los vínculos en los que se hizo clic es un vínculo de salida.

| Tamaño máximo | Parámetro depurador | Informes rellenados | Valor predeterminado |
|---|---|---|---|
| N/A | N/A | N/A | True |

La variable *`trackExternalLinks`* solo debe configurarse como 'false' si no hay vínculos de salida en el sitio o si no le importa realizar el seguimiento del número de clics en esos vínculos de salida. Un vínculo de salida es cualquier vínculo que conduce al visitante fuera del sitio. Si *`trackExternalLinks`* Tiene el valor “true”, los datos de seguimiento se envían inmediatamente al hacer clic en un vínculo de salida. Los datos que se envían con un vínculo de salida incluyen la dirección URL, el nombre y los datos del mapa de clics de visitantes para dicho vínculo. Si *`trackExternalLinks`* tiene el valor “False”, probablemente los datos del mapa de clics de visitantes para los vínculos de salida no estén completos.

## Sintaxis y valores posibles

Se espera que la variable *`trackExternalLinks`* sea 'true' o 'false'.

```
js
s.trackExternalLinks=true|false
```

## Ejemplos

```
js
s.trackExternalLinks=true 
```

```
js
s.trackExternalLinks=false
```

## Parámetros de configuración

Ninguna

## Problemas, preguntas y consejos

* Cuando *`trackExternalLinks`* tiene el valor es “False”, probablemente los vínculos que conducen al usuario fuera del sitio no estén completos en el mapa de clics de visitantes.

* Cuando *`trackExternalLinks`* tiene el valor “True”, se envían datos cada vez que un visitante hace clic en un vínculo de salida (antes de que se cargue el destino del vínculo).

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