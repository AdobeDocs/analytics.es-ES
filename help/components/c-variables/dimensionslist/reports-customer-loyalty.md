---
description: Lealtad del cliente revela los patrones de compra de los clientes.
seo-description: Lealtad del cliente revela los patrones de compra de los clientes.
seo-title: Lealtad del cliente
solution: Analytics
title: Lealtad del cliente
topic: 'Informes '
uuid: 7 dc 30 b 57-7 b 18-4228-a 6 ab -6 eb 66 b 3 d 9402
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Lealtad del cliente

Lealtad del cliente revela los patrones de compra de los clientes.

El informe muestra los patrones de compra de los clientes según cuatro categorías de lealtad:

* No es cliente
* Cliente nuevo
* Cliente que retorna
* Cliente fiel

Si bien en este informe se pueden ver métricas no relacionadas con compras (por ejemplo, eventos personalizados, eventos del carrito de compras, etc.), las categorías siempre se basan en la cantidad de pedidos hechos. Por ejemplo, un usuario puede agregar al informe un evento personalizado llamado Búsquedas internas. El elemento de línea [!UICONTROL Cliente que retorna] mostrará la cantidad de búsquedas internas realizadas por visitantes que ya hicieron dos compras, no la cantidad de visitantes que hicieron dos búsquedas internas.

**Procesamiento de lealtad del cliente**

En las tablas siguientes se define cómo procesan actualmente la lealtad del cliente Analysis Workspace, Reports &amp; Analytics, Ad Hoc Analysis y Data Warehouse:

<table id="table_E6A5CA96BE5C47F29F09688A4D41BC60"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> </th> 
   <th colname="col2" class="entry"> <p>Después del 19 de mayo de 2016 </p> </th> 
   <th colname="col3" class="entry"> <p>Entre el 21 de abril y el 19 de mayo de 2016 </p> <p>(no aplicable al Data Warehouse) </p> </th> 
   <th colname="col4" class="entry"> <p>Antes del 21 de abril de 2016 </p> </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>No es cliente </p> </td> 
   <td colname="col2"> <p>Visitantes que no han comprado nunca </p> </td> 
   <td colname="col3"> <p>Visitantes que han realizado 0 compras hasta el final de una visita. </p> </td> 
   <td colname="col4"> <p>No disponible. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Cliente nuevo </p> </td> 
   <td colname="col2"> <p>Visitantes que han realizado una sola compra </p> </td> 
   <td colname="col3"> <p>Visitantes que han realizado una compra hasta el final de una visita. </p> <p>(Si se realizó una compra, el estado del cliente se actualiza en la siguiente visita posterior a esa compra). </p> </td> 
   <td colname="col4"> <p>Visitantes que han realizado 0 compras hasta el final de una visita. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Cliente que retorna </p> </td> 
   <td colname="col2"> <p>Visitantes que han realizado dos compras </p> </td> 
   <td colname="col3"> <p>Visitantes que han realizado dos compras hasta el final de la visita en la que hicieron la segunda compra. </p> <p>(Si se realizó una compra, el estado del cliente se actualiza en la siguiente visita posterior a esa compra). </p> </td> 
   <td colname="col4"> <p>Visitantes que han realizado una compra hasta el final de la visita en la que hicieron esa compra. </p> <p>(Si se realizó una compra, el estado del cliente se actualiza en la siguiente visita posterior a esa compra). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Cliente fiel </p> </td> 
   <td colname="col2"> <p>Visitantes que han realizado tres compras o más </p> </td> 
   <td colname="col3"> <p>Visitantes que han realizado tres compras o más hasta el final de la visita en la que hicieron la última compra. </p> <p>(Si se realizó una compra, el estado del cliente se actualiza en la siguiente visita posterior a esa compra). </p> </td> 
   <td colname="col4"> <p>Visitantes que han realizado dos compras o más hasta el final de la visita en la que hicieron la última compra. </p> <p>(Si se realizó una compra, el estado del cliente se actualiza en la siguiente visita posterior a esa compra). </p> </td> 
  </tr> 
 </tbody> 
</table>

| Lealtad del cliente en la versión 14 (actual) |
|---|
| Cliente nuevo | Una visita y una compra |
| Cliente que retorna | Más de una visita y dos compras |
| Cliente fiel | Más de una visita y más de tres compras |

El estado de lealtad cambia inmediatamente después del evento de compra, dentro de la misma visita. Por ejemplo, un cliente nuevo (una compra) hace una compra y, a continuación, en la misma visita, se inscribe para recibir un boletín de noticias. El evento de inscripción en el boletín se considera una interacción con un cliente de retorno, porque el estado de lealtad de cliente del visitante cambió inmediatamente después de la compra.
