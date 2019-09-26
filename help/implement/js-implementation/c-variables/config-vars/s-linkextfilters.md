---
description: Las variables dinámicas permiten copiar valores entre distintas variables sin necesidad de escribir varias veces los valores completos en las solicitudes de imagen del sitio.
keywords: Implementación de análisis
seo-description: Las variables dinámicas permiten copiar valores entre distintas variables sin necesidad de escribir varias veces los valores completos en las solicitudes de imagen del sitio.
solution: null
title: Variables dinámicas
translation-type: tm+mt
source-git-commit: b38ba4222951d957c607cd764224028527835c7e

---


# s.linkExternalFilters

Si el sitio contiene muchos vínculos a sitios externos y no se desea realizar el seguimiento de todos los vínculos de salida, use para crear un informe de un subconjunto específico de vínculos de salida.

| Tamaño máximo | Parámetro depurador | Informes rellenados | Valor predeterminado |
|---|---|---|---|
| N.D. | N.D. | Rutas &gt; Entradas y salidas &gt; Vínculos de salida | "" |

La variable *`linkExternalFilters`* es una variable opcional utilizada junto con *`linkInternalFilters`* para determinar si un vínculo es de salida. Un vínculo de salida se define como un vínculo que conduce a un visitante fuera del sitio. El vínculo puede aparecer en el informe de vínculos de salida independientemente de si la ventana objetivo de un vínculo de salida es una ventana emergente o la ventana actual. Los vínculos de salida solo se rastrean si *`trackExternalLinks`* is set to 'true.' Los filtros de *`linkExternalFilters`* y *`linkInternalFilters`* no distinguen entre mayúsculas y minúsculas.

>[!NOTE]
>
>Si no desea usar *`linkExternalFilters`*, elimínelo o configúrelo en "".

La lista de filtros *`linkExternalFilters`* y *`linkInternalFilters`* se aplican al dominio y la ruta de cualquier vínculo de forma predeterminada. Si *`linkLeaveQueryString`* se establece en 'true', los filtros se aplican a toda la dirección URL (dominio, ruta y cadena de consulta). Estos filtros siempre se aplican a la ruta absoluta de la dirección URL, incluso si se utiliza una ruta relativa como el valor href.

Para la mayoría de las empresas, *`linkInternalFilters`* gives them enough control over exit links that they don't need *`linkExternalFilters`*. Using *`linkExternalFilters`* simply decreases the likelihood that an exit link is considered external. If *`linkExternalFilters`* has a value, then a link is considered only external if it does not match *`linkInternalFilters`* and does match *`linkExternalFilters`*.

El siguiente ejemplo ilustra cómo se utiliza esta variable. In this example, the URL of the page is `https://www.mysite.com/index.html`.

```js
s.trackExternalLinks=true 
s.linkInternalFilters="javascript:,mysite.com" 
s.linkExternalFilters="site1.com,site2.com,site3.com/partners" 
s.linkLeaveQueryString=false 
... 
<a href="https://www.mysite.com">Not an Exit Link</a> 
<a href="/careers/job_list.html">Not an Exit Link</a> 
<a href="https://www2.site3.com">Not an Exit Link</a> 
<a href="https://www.site1.com">Exit Link</a> 
<a href="https://www2.site3.com/partners/offer.asp">Exit Link</a> 
```

## Sintaxis y valores posibles

La sintaxis de la variable *`linkExternalFilters`* es una lista de caracteres ASCII separados por comas. No se permiten espacios.

```js
s.linkExternalFilters="site1.com[,site2.com[,site3.net[...]]]"
```

Se puede incluir cualquier parte de una dirección URL en *`linkExternalFilters`*, separada con comas.

## Ejemplos

```js
s.linkExternalFilters="partnersite.com,partnertwo.net/path/"
```

```js
s.linkExternalFilters=""
```

## Parámetros de configuración

Ninguno.

## Problemas, preguntas y consejos

* Using *`linkExternalFilters`* can result in fewer links on your site being exit links. No utilice esta variable en lugar de *`linkInternalFilters`* para obligar a los vínculos internos a convertirse en vínculos de salida.

* Si *`linkExternalFilters`* se debe aplicar a la cadena de consulta de un vínculo, asegúrese de que *`linkLeaveQueryString`* está configurada en 'true'. See [linkLeaveQueryString](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/config-var/s-account.html) before setting to `"true"`.

* To disable exit link tracking, set *`trackExternalLinks`* to `"false"`.
