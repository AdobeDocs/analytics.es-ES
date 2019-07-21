---
description: Describe lo que es un conflicto de hash y cómo se puede manifestar.
keywords: Implementación de Analytics; hash; colisión; prop; evar; hash
seo-description: Describe lo que es un conflicto de hash y cómo se puede manifestar.
seo-title: Conflictos de hash
solution: Analytics
title: Conflictos de hash
topic: Desarrollador e implementación
uuid: 7 dfd 6 e 64-4 a 62-4087-bc 28-fb 867 ec 2 b 1 b 6
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Conflictos de hash

Describe lo que es un conflicto de hash y cómo se puede manifestar.

De forma predeterminada, Adobe considera los valores de prop y de eVar como cadenas, incluso si el valor es un número. Algunas veces estas cadenas tienen cientos de caracteres, otras veces son cortas. Para ahorrar espacio, mejorar el rendimiento y hacer que todo tenga un tamaño uniforme, las cadenas no se usan directamente en las tablas de procesamiento. En cambio, se computa un hash de 32 bits o 64 bits para cada valor. Todos los informes se ejecutan por esos valores con hash hasta que se presentan los datos, donde cada hash se reemplaza con el texto original. Sin esta compresión, se tardaría varios minutos en ejecutar los informes.

Para la mayoría de los campos, la cadena primero se convierte a minúscula (reduciendo el número de valores únicos). Se colocan hashes en los valores todos los meses (la primera vez que son vistos cada mes). De un mes a otro, existe una pequeña posibilidad de que dos valores de variables únicos tengan hashes con el mismo valor de hash. Esto se conoce como *conflicto de hash*.

Los conflictos de hash pueden manifestarse en los informes de la siguiente manera:

* Si está viendo la tendencia de un valor y observa un pico durante un mes, posiblemente a otros valores para esa variable se les colocaron hash con el mismo valor que ve.
* Lo mismo ocurre para segmentos para un valor específico.

<p class="head"> <b>Ejemplo de conflictos de hash</b> </p>

La probabilidad de los conflictos de hash aumentan con la cantidad de valores únicos en una dimensión (eVar). Por ejemplo, uno de los valores que llega tarde en el mes podría obtener el mismo valor de hash que un valor más temprano en el mes. El siguiente ejemplo puede ayudar a explicar cómo esto puede hacer que los resultados de los segmentos cambien. Supongamos que eVar62 recibe "valor 100" el 18 de febrero. Analytics mantendrá una tabla similar a la siguiente:

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

Si genera un segmento que busca visitas donde eVar62="valor 500", Analytics determina si "valor 500" contiene un hash. Como "valor 500" no existe, Analytics devuelve cero visitas. Luego, el 23 de febrero, eVar62 recibe "valor 500", y el hash correspondiente también es 123. La tabla será similar a la siguiente:

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

Cuando el mismo segmento se ejecuta nuevamente, busca el hash de "valor 500", encuentra 123, y el informe devuelve todas las visitas que contienen hash 123. Ahora, las visitas que ocurrieron el 18 de febrero estarán incluidas en los resultados.

Esta situación puede crear problemas al usar Analytics. Adobe continúa investigando maneras de reducir las posibilidades de que ocurran estos conflictos de hash en el futuro. Algunas sugerencias para evitar esta situación son: encontrar maneras de propagar los valores únicos entre variables, eliminar valores innecesarios con reglas de procesamiento o, por el contrario, reducir el número de valores por variable.
