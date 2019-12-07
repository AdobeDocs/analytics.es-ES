---
description: Las métricas se calculan usando métodos estándar, de asignación, de participación, reciente y lineal. Cada método calcula los valores de forma diferente basándose en fórmulas.
title: Cálculos de métricas
topic: Metrics
uuid: 2af58f1e-12c5-4828-ae39-c9aeaef6b705
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

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
   <td colname="col2"> <p>Si se selecciona la asignación lineal, los eventos de éxito se dividen de manera uniforme entre todos los valores de variable que aparecen en la visita. En el caso de eventos numéricos y de moneda, como  <span class="term"> Ingresos</span>, se divide la cantidad monetaria. Para eventos de contador como <span class="term"> Pedidos</span>, se asigna una fracción del evento a cada valor de variable en la visita. Estas fracciones de los informes se suman y redondean hasta el entero más próximo que aparece en los informes. </p> <p>Por ejemplo, si en una visita se accede a cuatro páginas antes de un evento de éxito, cada página recibe crédito para el 25% del evento. Si, en la misma visita,  <span class="varname"> campaña</span> tiene dos valores. Cada valor de campaña recibirá el 50% del crédito por el evento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Participación </td> 
   <td colname="col2"> <p>Asigna crédito total a todos los valores de variable que contribuyen a un evento de éxito en una visita. Este cálculo también se puede aplicar a varias sesiones de visitantes, si se utilizan métricas de participación entre visitas. </p> <p>Consulte <a href="/help/components/c-variables/c-metrics/metrics-participation.md"  > Participación</a> para obtener más información. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Ejemplo: cálculo de métrica {#section_4CE01DA35108418D9909823A7ECC4B45}

Imaginemos que un sitio incluye una búsqueda interna de la que se está realizando un seguimiento con una variable de conversión (eVar). El visitante realiza varias búsquedas internas antes de realizar una compra de 100 $:

*`Pet`* &gt; *`Feline`* &gt; *`Cat`* &gt; *`Kitten`* &gt; compra de 100$

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
   <td colname="col3"> <p>0 USD </p> </td> 
   <td colname="col4"> <p>$25 </p> </td> 
   <td colname="col5"> <p>100 $ </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Felino </p> </td> 
   <td colname="col2"> <p>0 USD </p> </td> 
   <td colname="col3"> <p>0 USD </p> </td> 
   <td colname="col4"> <p>$25 </p> </td> 
   <td colname="col5"> <p>100 $ </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Gato </p> </td> 
   <td colname="col2"> <p>0 USD </p> </td> 
   <td colname="col3"> <p>0 USD </p> </td> 
   <td colname="col4"> <p>$25 </p> </td> 
   <td colname="col5"> <p>100 $ </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Gatito </p> </td> 
   <td colname="col2"> <p>0 USD </p> </td> 
   <td colname="col3"> <p>100 $ </p> </td> 
   <td colname="col4"> <p>$25 </p> </td> 
   <td colname="col5"> <p>100 $ </p> </td> 
  </tr> 
 </tbody> 
</table>

