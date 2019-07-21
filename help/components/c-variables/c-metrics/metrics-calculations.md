---
description: Las métricas se calculan usando métodos estándar, de asignación, de participación, reciente y lineal. Cada método calcula los valores de forma diferente basándose en fórmulas.
seo-description: Las métricas se calculan usando métodos estándar, de asignación, de participación, reciente y lineal. Cada método calcula los valores de forma diferente basándose en fórmulas.
seo-title: Cálculos de métricas
solution: Analytics
title: Cálculos de métricas
topic: Métricas
uuid: 2 af 58 f 1 e -12 c 5-4828-ae 39-c 9 aeaef 6 b 705
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Cálculos de métricas

Las métricas se calculan usando métodos estándar, de asignación, de participación, reciente y lineal. Cada método calcula los valores de forma diferente basándose en fórmulas.

<table id="table_6F81A12174D84124B7FD81FBBEDF18A2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Cálculo de métricas </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Original </td> 
   <td colname="col2"> <p>Se concede crédito total al primer valor de variable asociado con el evento de éxito. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Reciente </td> 
   <td colname="col2"> <p>Se concede crédito total al último valor de variable asociado con el evento de éxito. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Lineal </td> 
   <td colname="col2"> <p>Si se selecciona la asignación lineal, los eventos de éxito se dividen de manera uniforme entre todos los valores de variable que aparecen en la visita. En el caso de eventos numéricos y de moneda, como <span class="term"> Ingresos</span>, se divide la cantidad monetaria. For counter events such as <span class="term"> Orders</span>, a fraction of the event is awarded to each variable value in the visit. Estas fracciones de los informes se suman y redondean hasta el entero más próximo que aparece en los informes. </p> <p>Por ejemplo, si en una visita se accede a cuatro páginas antes de un evento de éxito, cada página recibe crédito para el 25% del evento. Si, en la misma visita, <span class="varname"> la campaña</span> tenía dos valores, cada valor de campaña recibía el 50% del crédito por el evento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Participación </td> 
   <td colname="col2"> <p>Asigna crédito total a todos los valores de variable que contribuyen a un evento de éxito en una visita. Este cálculo también se puede aplicar a varias sesiones de visitantes, si se utilizan métricas de participación entre visitas. </p> <p>Consulte <a href="../../../components/c-variables/c-metrics/metrics-participation.md#concept_8E6B39106A244CB49E055150B291B477" format="dita" scope="local"> Participación</a> para obtener más información. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Ejemplo: cálculo de métrica {#section_4CE01DA35108418D9909823A7ECC4B45}

Imaginemos que un sitio incluye una búsqueda interna de la que se está realizando un seguimiento con una variable de conversión (eVar). El visitante realiza varias búsquedas internas antes de realizar una compra de 100 $:

*`Pet`* &gt; *`Feline`* &gt; *`Cat`* &gt; *`Kitten`* &gt; compra de 100 $

En los informes, la asignación de crédito sería la siguiente:

<table id="table_91A7244E77854838A8392B49366FB445"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Valor de eVar </th> 
   <th colname="col2" class="entry"> Primero </th> 
   <th colname="col3" class="entry"> Último </th> 
   <th colname="col4" class="entry"> Lineal </th> 
   <th colname="col5" class="entry"> Participación </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Mascota </p> </td> 
   <td colname="col2"> <p>100 $ </p> </td> 
   <td colname="col3"> <p>0 $ </p> </td> 
   <td colname="col4"> <p>25 $ </p> </td> 
   <td colname="col5"> <p>100 $ </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Felino </p> </td> 
   <td colname="col2"> <p>0 $ </p> </td> 
   <td colname="col3"> <p>0 $ </p> </td> 
   <td colname="col4"> <p>25 $ </p> </td> 
   <td colname="col5"> <p>100 $ </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Gato </p> </td> 
   <td colname="col2"> <p>0 $ </p> </td> 
   <td colname="col3"> <p>0 $ </p> </td> 
   <td colname="col4"> <p>25 $ </p> </td> 
   <td colname="col5"> <p>100 $ </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Gatito </p> </td> 
   <td colname="col2"> <p>0 $ </p> </td> 
   <td colname="col3"> <p>100 $ </p> </td> 
   <td colname="col4"> <p>25 $ </p> </td> 
   <td colname="col5"> <p>100 $ </p> </td> 
  </tr> 
 </tbody> 
</table>

