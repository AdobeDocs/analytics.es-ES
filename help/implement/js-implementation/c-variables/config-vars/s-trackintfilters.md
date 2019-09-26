---
description: Las variables dinámicas permiten copiar valores entre distintas variables sin necesidad de escribir varias veces los valores completos en las solicitudes de imagen del sitio.
keywords: Implementación de análisis
seo-description: Las variables dinámicas permiten copiar valores entre distintas variables sin necesidad de escribir varias veces los valores completos en las solicitudes de imagen del sitio.
solution: null
title: Variables dinámicas
translation-type: tm+mt
source-git-commit: 60dd1b300035e5149f53870239de85fb3174a77a

---



# s.linkInternalFilters

La variable se usa para determinar qué vínculos del sitio son vínculos de salida.

Es una lista de filtros separados por coma que representan los vínculos que son parte del sitio.

| Tamaño máximo | Parámetro depurador | Informes rellenados | Valor predeterminado |
|---|---|---|---|
| N.D. | N.D. | Rutas &gt; Entradas y salidas &gt; Vínculos de salida |  |

>[!NOTE]
>
>Anteriormente, habíamos sugerido configurar linkInternalFilters en javascript:. Sin embargo, el resultado era que todos los dominios se consideraban externos, incluido el dominio actual en el que reside la etiqueta. Si desea que algunos dominios se consideren internos, puede agregarlos como se muestra en los ejemplos siguientes.

The *`linkInternalFilters`* variable is used to determine whether a link is an exit link, which is defined as any link that takes a visitor away from your site. El vínculo puede aparecer en el informe de vínculos de salida independientemente de si la ventana objetivo de un vínculo de salida es una ventana emergente o la ventana actual. Solo se realiza el seguimiento de los vínculos de salida si es *`trackExternalLinks`* está configurada como `"true"`. (Consulte [Seguimiento de vínculos](https://marketing.adobe.com/resources/help/en_US/dtm/link_tracking.html) en la documentación de Dynamic Tag Management para obtener información sobre cómo administra DTM los vínculos de salida). Los filtros de *`linkInternalFilters`* no distinguen entre mayúsculas y minúsculas.

The list of filters in  applies to the domain and path of any link by default. *`linkInternalFilters`* If *`linkLeaveQueryString`* is set to `"true"`, then the filters apply to the entire URL (domain, path, and query string). Los filtros siempre se aplican a la ruta absoluta de la dirección URL, incluso si se utiliza una ruta relativa como el valor href.

Asegúrese de que todos los dominios del sitio (y de los socios que usen su archivo JavaScript) estén incluidos en  *`linkInternalFilters`*. Si no todos los dominios están incluidos en la lista, todos los vínculos de esos dominios y hacia esos dominios se considerarán vínculos de salida, lo que aumenta las llamadas al servidor enviadas. If you would like multiple domains or companies to use a single [!DNL AppMeasurement] for JavaScript file, you may consider populating *`linkInternalFilters`* on the page, overriding the value specified in the JavaScript file. Si tiene dominios personales que se redireccionan inmediatamente al dominio principal, no es necesario incluir dichos dominios personales en la lista.

El siguiente ejemplo ilustra cómo se utiliza esta variable. In this example, the URL of the page is `https://www.mysite.com/index.html`.

```js
s.trackExternalLinks=true 
s.linkInternalFilters="mysite.com" 
s.linkExternalFilters="" 
s.linkLeaveQueryString=false 
... 
<a href="https://www.mysite.com">Not an Exit Link</a> 
<a href="/careers/job_list.html">Not an Exit Link</a> 
<a href="https://www2.site3.com">Exit Link</a> 
<a href="https://www2.site1.com/partners/">Exit Link</a> 
```

## Sintaxis y valores posibles

La sintaxis de la variable *`linkInternalFilters`* es una lista de caracteres ASCII separados por comas. No se permiten espacios.

```js
s.linkInternalFilters="site1.com[,site2.com[,site3.net[...]]]"
```

## Ejemplos

```js
s.linkInternalFilters="mysite.com"
```

```js
s.linkInternalFilters="mysite.com,mysite.net,vanity1.com"
```

## Parámetros de configuración

Ninguno.

## Problemas, preguntas y consejos

* Include all domains that the [!DNL AppMeasurement] for JavaScript file may be served under in the filter list.
* Compruebe periódicamente el informe [!UICONTROL Rutas] &gt; [!UICONTROL Entradas y salidas] &gt; [!UICONTROL Vínculos de salida] para asegurarse de que ninguna de las entradas del informe son incorrectas.

* Revise periódicamente los contratos con los socios para determinar si contienen restricciones sobre el seguimiento de vínculos. Por ejemplo, quizás tenga prohibido realizar el seguimiento de vínculos que aparecen en los anuncios en pantalla de los socios. Filtre los vínculos de los socios agregando su dominio a  *`linkInternalFilters`*:

```js
s.linkInternalFilters="mysite.com,mysite.net,mypartner.net/adclick"
```
