---
title: Conflictos de hash
description: Describe lo que es un conflicto de hash y cómo se puede manifestar.
exl-id: 693d5c03-4afa-4890-be4f-7dc58a1df553
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '443'
ht-degree: 100%

---

# Conflictos de hash

Adobe considera los valores de prop y de eVar como cadenas, incluso si el valor es un número. Algunas veces estas cadenas tienen cientos de caracteres, otras veces son cortas. Para ahorrar espacio, mejorar el rendimiento y hacer que todo tenga un tamaño uniforme, las cadenas no se usan directamente en el procesamiento. En cambio, se computa un hash de 32 bits o 64 bits para cada valor. Todos los informes se ejecutan en estos valores con hash, donde cada hash se reemplaza por el texto original. Los hash mejoran notablemente el rendimiento de los informes de Analytics.

Para la mayoría de los campos, la cadena primero se convierte a minúscula (reduciendo el número de valores únicos). Se colocan hashes en los valores todos los meses (la primera vez que son vistos cada mes). De un mes a otro, existe una pequeña posibilidad de que dos valores de variables únicos tengan hashes con el mismo valor. Esto se conoce como *conflicto de hash*.

Los conflictos de hash pueden manifestarse en los informes de la siguiente manera:

* Si está viendo la tendencia de un valor y observa un pico durante un mes, posiblemente a otros valores para esa variable se les colocaron hash con el mismo valor que ve.
* Lo mismo ocurre para segmentos para un valor específico.

## Ejemplo de conflictos de hash

La probabilidad de los conflictos de hash aumentan con la cantidad de valores únicos en una dimensión. Por ejemplo, uno de los valores que llega tarde en el mes podría obtener el mismo valor de hash que un valor más temprano en el mes. El siguiente ejemplo puede ayudar a explicar cómo esto puede hacer que los resultados de los segmentos cambien. Supongamos que eVar62 recibe &quot;valor 100&quot; el 18 de febrero. Analytics mantendrá una tabla similar a la siguiente:

<table id="table_6A49D1D5932E485DB2083154897E5074"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Valor de cadena eVar62 </th> 
   <th colname="col2" class="entry"> Hash </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> Valor 99 </p> </td> 
   <td colname="col2"> <p> 111 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b> Valor 100</b> </p> </td> 
   <td colname="col2"> <p> <b> 123</b> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Valor 101 </p> </td> 
   <td colname="col2"> <p> 222 </p> </td> 
  </tr> 
 </tbody> 
</table>

Si genera un segmento que busca visitas donde eVar62=&quot;valor 500&quot;, Analytics determina si &quot;valor 500&quot; contiene un hash. Como &quot;valor 500&quot; no existe, Analytics devuelve cero visitas. Luego, el 23 de febrero, eVar62 recibe &quot;valor 500&quot;, y el hash correspondiente también es 123. La tabla será similar a la siguiente:

<table id="table_5FCF0BCDA5E740CCA266A822D9084C49"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Valor de cadena eVar62 </th> 
   <th colname="col2" class="entry"> Hash </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> Valor 99 </p> </td> 
   <td colname="col2"> <p> 111 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b> Valor 100</b> </p> </td> 
   <td colname="col2"> <p> <b> 123</b> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Valor 101 </p> </td> 
   <td colname="col2"> <p> 222 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b> Valor 500</b> </p> </td> 
   <td colname="col2"> <p> <b> 123</b> </p> </td> 
  </tr> 
 </tbody> 
</table>

Cuando el mismo segmento se ejecuta nuevamente, busca el hash de &quot;valor 500&quot;, encuentra 123, y el informe devuelve todas las visitas que contienen hash 123. Ahora, las visitas que ocurrieron el 18 de febrero estarán incluidas en los resultados.

Esta situación puede crear problemas al usar Analytics. Adobe continúa investigando maneras de reducir las posibilidades de que ocurran estos conflictos de hash en el futuro. Algunas sugerencias para evitar esta situación son: encontrar maneras de propagar los valores únicos entre variables, eliminar valores innecesarios con reglas de procesamiento o, por el contrario, reducir el número de valores por variable.
