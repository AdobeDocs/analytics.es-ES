---
description: Los derechos de las métricas calculadas difieren entre los usuarios a nivel de administrador y los usuarios no administradores.
seo-description: Los derechos de las métricas calculadas difieren entre los usuarios a nivel de administrador y los usuarios no administradores.
seo-title: Derechos basados en la función de métricas calculadas
title: Derechos basados en la función de métricas calculadas
uuid: 7 c 14 d 32 d -370 c -4 afa -8 f 80-5 bbd 8 fc 12 ec 7
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Métricas calculadas: derechos basados en roles

Los derechos de las métricas calculadas difieren entre los usuarios a nivel de administrador y los usuarios no administradores.

<table id="table_13F72FD90C964B86BD4B51E6F51ED292"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> </th> 
   <th colname="col02" class="entry"> Crear  </th> 
   <th colname="col2" class="entry"> Compartir </th> 
   <th colname="col3" class="entry"> Ver/Administrar </th> 
   <th colname="col4" class="entry"> Aprobar </th> 
   <th colname="col5" class="entry"> Aplicar </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Usuarios de nivel de administrador</b> </td> 
   <td colname="col02"> Los administradores pueden crear métricas calculadas y <a href="https://marketing.adobe.com/resources/help/en_US/reference/groups.html" format="https" scope="external">grupos</a> para limitar los derechos de los usuarios en la creación de métricas calculadas. </td> 
   <td colname="col2"> Pueden compartir con toda la empresa, con grupos de usuarios y con usuarios individuales. </td> 
   <td colname="col3"> <span class="keyword"> [! Informes y análisis de UICONTROL] </span>: Puede ver, editar, eliminar, etc. sus propias métricas calculadas y las de otros usuarios. <p> <span class="keyword"> Ad Hoc Analysis</span> y <span class="keyword">Report Builder</span>: pueden ver, editar, eliminar, etc. sus propias métricas calculadas y las que se han compartido con ellos. </p> </td> 
   <td colname="col4"> Pueden aprobar métricas calculadas como canónicas. </td> 
   <td colname="col5"> Pueden aplicar cualquier métrica calculada en toda la organización. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Usuarios que no son administradores</b> </td> 
   <td colname="col02"> De forma predeterminada, los usuarios pueden crear métricas calculadas. Sin embargo, los administradores pueden limitar estos derechos. </td> 
   <td colname="col2"> Pueden compartir únicamente con usuarios individuales. </td> 
   <td colname="col3"> Pueden ver, editar, eliminar, etc. solo sus propias métricas calculadas. <p>Los usuarios no administradores deben tener acceso a todos los eventos del componente para poder ver una métrica compartida (los permisos de la Admin Console siguen en vigor). </p> <p>Si un tablero o informe programado se comparte con un usuario no administrador y no se ha compartido la métrica con él, el informe se ejecutará con la métrica aplicada (siempre que tenga los permisos para ver los eventos). Sin embargo, no podrán ver la definición ni editar la métrica. </p> </td> 
   <td colname="col4"> Solo pueden consumir métricas calculadas aprobadas; no pueden marcar como aprobado. </td> 
   <td colname="col5"> Pueden aplicar sus propias métricas calculadas y segmentos que se han compartido con ellos. </td> 
  </tr> 
 </tbody> 
</table>

