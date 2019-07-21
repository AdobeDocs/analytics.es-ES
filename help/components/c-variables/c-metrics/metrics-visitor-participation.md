---
description: La serie de métricas de participación de visitantes permite ver la participación a lo largo de varias sesiones de visita en canales de marketing, campañas, ingresos, etc. Por ejemplo, el crédito por compras e ingresos se puede atribuir en forma retroactiva a otros puntos de contacto promocionales previos a la visita en la que se realizó el pedido. Ad Hoc Analysis proporciona datos de la participación de los visitantes en diversas visitas.
seo-description: La serie de métricas de participación de visitantes permite ver la participación a lo largo de varias sesiones de visita en canales de marketing, campañas, ingresos, etc. Por ejemplo, el crédito por compras e ingresos se puede atribuir en forma retroactiva a otros puntos de contacto promocionales previos a la visita en la que se realizó el pedido. Ad Hoc Analysis proporciona datos de la participación de los visitantes en diversas visitas.
seo-title: 'Participación de visitantes: Ad Hoc Analysis'
solution: Analytics
title: 'Participación de visitantes: Ad Hoc Analysis'
topic: Métricas
uuid: 567 d 627 c-a 2 a 8-4 fbf-b 3 fd-abb 1341 e 57 a 0
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Participación de visitantes: Ad Hoc Analysis

La serie de métricas de participación de visitantes permite ver la participación a lo largo de varias sesiones de visita en canales de marketing, campañas, ingresos, etc. Por ejemplo, el crédito por compras e ingresos se puede atribuir en forma retroactiva a otros puntos de contacto promocionales previos a la visita en la que se realizó el pedido. Ad Hoc Analysis proporciona datos de la participación de los visitantes en diversas visitas.

**Ingresos (Participación)**: distribuye el crédito por la conversión entre todas las páginas en una visita única que condujo a la conversión, hasta la página de conversión.

**Ingresos (Participación de visitante)**: distribuye el crédito entre todas las páginas y todas las visitas, según el intervalo de tiempo que se indique.

**Ejemplo: participación en ingresos en todas las visitas**

Un cliente visita el sitio dos veces. El evento de conversión ocurre en la segunda visita, en la página D, y produce 60 $ de ingresos:

![](assets/VisitorPaticipation.png)

Al generarse el informe, la asignación de crédito por la conversión es así:

* **Ingresos**: se asigna a la página.
* **Ingresos (Participación)**: se asigna a la segunda visita.
* **Ingresos (Participación de visitante)**: se asigna a ambas visitas.

<table id="table_91A7244E77854838A8392B49366FB445"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Página </th> 
   <th colname="col2" class="entry"> Ingresos </th> 
   <th colname="col3" class="entry"> Ingresos (Participación) </th> 
   <th colname="col4" class="entry"> Ingresos (Participación de visitante) </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>A </p> </td> 
   <td colname="col2"> <p>0 </p> </td> 
   <td colname="col3"> <p>60 $ </p> </td> 
   <td colname="col4"> <p>60 $ </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>B </p> </td> 
   <td colname="col2"> <p>0 </p> </td> 
   <td colname="col3"> <p>60 $ </p> </td> 
   <td colname="col4"> <p>60 $ </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>C </p> </td> 
   <td colname="col2"> <p>0 </p> </td> 
   <td colname="col3"> <p>0 </p> </td> 
   <td colname="col4"> <p>60 $ </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>D </p> </td> 
   <td colname="col2"> <p>60 $ </p> </td> 
   <td colname="col3"> <p>60 $ </p> </td> 
   <td colname="col4"> <p>60 $ </p> </td> 
  </tr> 
 </tbody> 
</table>

