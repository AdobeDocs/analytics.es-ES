---
description: Clasifica las páginas del sitio según la cantidad de tráfico que reciben. Cuando para tomar decisiones de negocios se necesita conocer datos cuantitativos de las páginas, este informe permite obtenerlos, mediante la adición de la métrica correcta.
seo-description: Clasifica las páginas del sitio según la cantidad de tráfico que reciben. Cuando para tomar decisiones de negocios se necesita conocer datos cuantitativos de las páginas, este informe permite obtenerlos, mediante la adición de la métrica correcta.
seo-title: Páginas
solution: Analytics
title: Páginas
topic: 'Informes '
uuid: 6435 e 262-e 734-4 c 15-af 5 b -173799 d 5 cc 43
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Páginas

Clasifica las páginas del sitio según la cantidad de tráfico que reciben. Cuando para tomar decisiones de negocios se necesita conocer datos cuantitativos de las páginas, este informe permite obtenerlos, mediante la adición de la métrica correcta.

## Asignación, caducidad y valores especiales {#section_4D8CE5E111DD48FBBDCF9B5A1F16E92E}

Observe que, en Reports &amp; Analytics, las métricas sobre el informe de las páginas utilizan una asignación lineal. Por ejemplo, los ingresos se dividen entre todas las páginas vistas antes de un evento de compra. Esto puede causar confusión para algunas métricas en la que espere que se produzcan solo en una página, como una adición al carro de compras.

<table id="table_EC7423532C7E44DE97B7FC0321585A2B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> </th> 
   <th colname="col2" class="entry">Informes y <p>análisis </p> </th> 
   <th colname="col3" class="entry"> Ad Hoc Analysis </th> 
   <th colname="col4" class="entry"> Data Warehouse </th> 
   <th colname="col5" class="entry"> Analysis Workspace </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Asignación de métricas </td> 
   <td colname="col2"> Lineal </td> 
   <td colname="col3"> La asignación es específica a cada una de las dimensiones. El valor predeterminado es Último toque, aunque la dimensión 'pagename' es una excepción. Si aplica un evento personalizado a 'pagename', será la asignación de visita exacta. </td> 
   <td colname="col4"> <p>Los valores se establecen en la misma vista de página </p> </td> 
   <td colname="col5"> <p>Los valores se establecen en la misma vista de página </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Los valores caducan después de </td> 
   <td colname="col2"> Vista de la página </td> 
   <td colname="col3"> Vista de la página </td> 
   <td colname="col4"> Vista de la página </td> 
   <td colname="col5"> Vista de la página </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Límites de valores </td> 
   <td colname="col2"> <p>Primeras 500000 visitas únicas por mes + nuevos valores con tráfico </p> </td> 
   <td colname="col3"> <p>Primeras 500000 visitas únicas por mes + nuevos valores con tráfico </p> </td> 
   <td colname="col4"> Ninguno </td> 
   <td colname="col5"> <p>Primeras 500000 visitas únicas por mes + nuevos valores con tráfico </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Valores especiales </td> 
   <td colname="col2"> <p>(Poco tráfico) representa valores que superan las primeras 500000 visitas y que no han recibido tráfico suficiente para aparecer en informes. </p> </td> 
   <td colname="col3"> <p>(Poco tráfico) representa valores que superan las primeras 500000 visitas y que no han recibido tráfico suficiente para aparecer en informes. </p> </td> 
   <td colname="col4"> Ninguno </td> 
   <td colname="col5"> <p>(Poco tráfico) representa valores que superan las primeras 500000 visitas y que no han recibido tráfico suficiente para aparecer en informes. </p> </td> 
  </tr> 
 </tbody> 
</table>

En Reports &amp; Analytics, si aplica cualquier evento personalizado como métrica en un informe Páginas, se aplicará la asignación lineal.

Esto significa que, incluso aunque el evento se haya enviado con una llamada s.tl(), obtendrá la asignación lineal de cualquier llamada s.t() anterior. Ejemplo:

| Nombre de la página | Page_event | Eventos |
|---|---|---|
| Página 1 | **s.t()** |  |
| Página 1 | s.tl() | Evento 1 |
| Página 1 | s.tl() | Evento 1 |
| Página 1 | s.tl() | Evento 1 |
| Página 2 | **s.t()** |  |
| Página 2 | **s.t()** |  |
| Página 2 | s.tl() | Evento 1 |

Para este escenario, solo obtendremos la siguiente asignación en el informe Páginas:

| Páginas | Vistas de página | Evento 1 |
|---|---|---|
| Página 1 | 1 | 1+1+1+1/3 = 3,33 |
| Página 2 | 2 | 2/3 = 0,67 |

Incluso aunque el evento se envíe en una llamada s.tl, la página que se ve antes del evento que se ha enviado, llamada s.t(), obtendrá un crédito parcial.

## Notas {#section_47B0F4746D4847AC9E8697127063F4D0}

* Si no hay ningún nombre de página, se usa la dirección URL.
* Si tiene una visita sin nombre de página, dirección URL de página ni lista de eventos (sin ningún evento de comercio), se excluirá la visita.
* En el desglose por páginas se muestran todas las páginas en las que ha persistido un valor.

