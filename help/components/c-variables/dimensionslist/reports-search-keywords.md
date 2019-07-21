---
description: Muestra un desglose de palabras clave de búsqueda.
seo-description: Muestra un desglose de palabras clave de búsqueda.
seo-title: Palabras clave de búsqueda
solution: Analytics
title: Palabras clave de búsqueda
topic: 'Informes '
uuid: db 9 d 477 b-b 711-4 b 93-9 c 25-3 aebe 5 f 2 ace 6
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Palabras clave de búsqueda

Muestra un desglose de palabras clave de búsqueda.

**Palabras clave de búsqueda: Todas**: muestra un desglose de cada palabra clave de búsqueda que se ha utilizado para encontrar el sitio. Para ordenar esta lista según las vistas de las páginas o las palabras clave de búsqueda, haga clic en el título de la columna que se encuentra sobre la lista. Haga clic en la lupa situada al lado de la palabra clave de búsqueda para ver los resultados de búsqueda correspondientes al sitio.

**Palabras clave de búsqueda: Pagado**: muestra un desglose de cada palabra clave de búsqueda pagada que se utilizó para encontrar el sitio. Para ordenar esta lista según las vistas de las páginas o las palabras clave de búsqueda, haga clic en el título de la columna que se encuentra sobre la lista. Haga clic en la lupa situada al lado de la palabra clave de búsqueda para ver los resultados de búsqueda correspondientes al sitio.

**Palabras clave de búsqueda: Natural**: muestra un desglose de cada palabra clave de búsqueda natural que se utilizó para encontrar el sitio. Para ordenar esta lista según las vistas de las páginas o las palabras clave de búsqueda, haga clic en el título de la columna que se encuentra sobre la lista. Haga clic en la lupa situada al lado de la palabra clave de búsqueda para ver los resultados de búsqueda correspondientes al sitio.

>[!IMPORTANT]
>
>En la búsqueda paga y natural, los motores de búsqueda dejaron de proporcionar (en la mayoría de los casos) las palabras clave de búsqueda como parte del referente. En consecuencia, Adobe siempre clasifica el dominio Google (o Bing, o Yahoo) como búsqueda. A partir del formato y el contenido del referente (aun sin las palabras clave), Adobe puede determinar muchas veces cuándo se trata del resultado de una búsqueda, de modo que esta se cuenta con las palabras clave No disponible. [Más...](https://helpx.adobe.com/analytics/kb/keyword-unavailable.html)

## Asignación, caducidad y valores especiales {#section_4D8CE5E111DD48FBBDCF9B5A1F16E92E}

<table id="table_EC7423532C7E44DE97B7FC0321585A2B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> </th> 
   <th colname="col2" class="entry"> <p>Analysis Workspace </p> <p>Reports &amp; Analytics </p> </th> 
   <th colname="col3" class="entry"> Ad Hoc Analysis </th> 
   <th colname="col4" class="entry"> Data Warehouse </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Asignación de métricas </td> 
   <td colname="col2"> <p>Valor original (predeterminado) </p> <p> Se puede cambiar a lineal. </p> </td> 
   <td colname="col3"> Más reciente (se puede cambiar a lineal para que use la versión lineal de una métrica) </td> 
   <td colname="col4"> <p>Valor original (predeterminado) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Los valores caducan después de </td> 
   <td colname="col2"> Visita: se puede acortar pero no alargar </td> 
   <td colname="col3"> Visita </td> 
   <td colname="col4"> Visita </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Límites de valores </td> 
   <td colname="col2"> Sin límites (puede cambiar en próximas versiones) </td> 
   <td colname="col3"> Sin límites (puede cambiar en próximas versiones) </td> 
   <td colname="col4"> ninguno </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Valores especiales </td> 
   <td colname="col2"> <p>"Ninguno": totales de todo el sitio que no tienen una palabra clave durante la visita. </p> "Palabras clave no disponible" equivale a búsquedas en las que se han eliminado las palabras clave y no se envía a la recopilación de datos. Esto suele ocurrir cuando un cliente ha iniciado sesión en una cuenta de Google. Es válido tanto para búsqueda natural como de pago. </td> 
   <td colname="col3"> (Poco tráfico) representa valores que superan las primeras 500000 visitas y que no han recibido tráfico suficiente para aparecer en informes. </td> 
   <td colname="col4"> <p> "Vacío" (equivale a "Ninguno"): totales de todo el sitio que no tienen una palabra clave durante la visita. </p> <p>"Palabras clave no disponible" equivale a búsquedas en las que se han eliminado las palabras clave y no se envía a la recopilación de datos. Esto suele ocurrir cuando un cliente ha iniciado sesión en una cuenta de Google. Es válido tanto para búsqueda natural como de pago. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Historial de informes {#section_6C0FCEA9DAF04D97BA056E153B7E4628}

| Fecha | Cambiar |
|---|---|
| 16/1/2014 | El almacén de datos se ha actualizado para que coincida con la lógica usada por los Reports &amp; Analytics de marketing. Antes de esta fecha, las palabras clave de búsqueda no persistían durante la visita. |

