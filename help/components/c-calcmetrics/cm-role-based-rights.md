---
description: Los derechos de las métricas calculadas difieren entre los usuarios a nivel de administrador y los usuarios no administradores.
title: 'Métricas calculadas:  derechos basados en funciones'
uuid: 7c14d32d-370c-4afa-8f80-5bbd8fc12ec7
exl-id: 018d9ef5-5a6f-4ebc-a241-c1291ba6b561
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: tm+mt
source-wordcount: '254'
ht-degree: 96%

---

# Derechos de las métricas calculadas basados en funciones

Los derechos de las métricas calculadas difieren entre los usuarios a nivel de administrador y los usuarios no administradores.

<table id="table_13F72FD90C964B86BD4B51E6F51ED292"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> </th> 
   <th colname="col02" class="entry"> Crear </th> 
   <th colname="col2" class="entry"> Compartir </th> 
   <th colname="col3" class="entry"> Ver/Administrar </th> 
   <th colname="col4" class="entry"> Aprobar </th> 
   <th colname="col5" class="entry"> Aplicar </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Usuarios de nivel de administrador</b> </td> 
   <td colname="col02"> Los administradores pueden crear métricas calculadas y <a href="https://experienceleague.adobe.com/docs/analytics/admin/user-product-management/user-groups/groups.html"  >grupos</a> para limitar los derechos de los usuarios en la creación de métricas calculadas. </td> 
   <td colname="col2"> Pueden compartir con toda la empresa, con grupos de usuarios y con usuarios individuales. </td> 
   <td colname="col3"> <span class="keyword">Reports &amp; Analytics</span>: pueden ver, editar, eliminar, etc. sus propias métricas calculadas y las de otros usuarios. <p> <span class="keyword">Report Builder</span>: pueden ver, editar, eliminar, etc. sus propias métricas calculadas y las que se han compartido con ellos. </p> </td> 
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
