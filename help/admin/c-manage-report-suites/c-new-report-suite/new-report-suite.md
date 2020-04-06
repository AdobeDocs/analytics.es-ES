---
description: Puede crear un nuevo grupo de informes seleccionando como modelo una plantilla predefinida o utilizando uno de los grupos de informes existentes.
title: Descargar la configuración del grupo de informes
topic: Admin tools
uuid: 3508f684-11a3-4c8f-a233-bea6bafd57c0
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Descargar la configuración del grupo de informes

Puede crear un nuevo grupo de informes seleccionando como modelo una plantilla predefinida o utilizando uno de los grupos de informes existentes.

Descripción de los elementos utilizados al [crear un grupo de informes](/help/admin/c-manage-report-suites/c-new-report-suite/t-create-a-report-suite.md).

>[!NOTE] La [Documentación del grupo de informes virtuales](/help/components/vrs/c-workflow-vrs/vrs-create.md) le muestra cómo crear grupos de informes virtuales.

<table id="table_F739FBD8DB8D409E916F12F61C5953D0"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <span class="wintitle">ID del grupo de informes </span> </td> 
   <td colname="col2"> <p>Especifica un ID único que puede contener sólo caracteres alfanuméricos. Esta ID no se puede cambiar una vez creada. Adobe establece el prefijo de ID necesario y tampoco se puede cambiar. </p> <p>Al crear varios grupos de informes, asegúrese de que la convención de nombres que utilice garantice ID de grupos de informes únicos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Título del sitio</span> </td> 
   <td colname="col2">Identifica al grupo de informes en las <span class="wintitle">Herramientas de administración</span>. Este título también se utiliza en la lista desplegable <span class="wintitle">Grupo de informes</span> en el encabezado de grupo. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Zona horaria</span> </td> 
   <td colname="col2"> Programa eventos y datos de marca de hora. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Dirección URL base</span> </td> 
   <td colname="col2"> (Opcional) Define el dominio base para el grupo de informes. Esta URL funciona como un filtro de URL interno si no define explícitamente filtros de URL internas para el grupo de informes. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Página predeterminada</span> </td> 
   <td colname="col2"> <p>Reduce las repeticiones del valor <span class="wintitle">Página predeterminada</span> en las direcciones URL que encuentra (opcional). Si el informe <span class="wintitle">Páginas más populares</span> contiene direcciones URL en vez de nombres de páginas, esta opción evita que se registren varias URL para la misma página web. </p> <p>Por ejemplo, las direcciones URL <span class="filepath">http://misitio.com</span> y <span class="filepath">http://misitio.com/index.html</span> suelen corresponder a la misma página. Puede quitar los nombres de archivo prescindibles para que ambas URL aparezcan como <span class="filepath">http://misitio.com</span> en los informes. </p> <p>Si no se define este valor, Analytics quitará automáticamente los siguientes nombres de archivo de las direcciones URL: <span class="filepath">index.htm</span>, <span class="filepath">index.html</span>, <span class="filepath">index.cgi</span>, <span class="filepath">index.asp</span>, <span class="filepath">default.htm</span>, <span class="filepath">default.html</span>, <span class="filepath">default.cgi</span>, <span class="filepath">default.asp</span>, <span class="filepath">home.htm</span>, <span class="filepath">home.html</span>, <span class="filepath">home.cgi</span> y <span class="filepath">home.asp</span>. </p> <p>Para desactivar la eliminación de nombres de archivo, especifique un valor de Página predeterminada que nunca aparezca en las direcciones URL. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Fecha de lanzamiento </p> </td> 
   <td colname="col2">Informa a Adobe de la fecha en la que espera que este grupo de informes se active. Si su programa de implementación cambia, indique el cálculo de tráfico actualizado mediante la herramienta <span class="wintitle"> Tráfico previsto permanente</span> en <a href="/help/admin/c-traffic-management/traffic-management.md"> Administración del tráfico</a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Vistas de la página estimadas por día</span> </td> 
   <td colname="col2"> Identifica la cantidad estimada de vistas de página que espera que admita este grupo de informes en un día. Los grandes volúmenes de tráfico requieren un proceso de aprobación más largo. Para evitar retrasos en el procesamiento, utilice esta estimación con la mayor precisión posible. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Moneda base</span> </td> 
   <td colname="col2"> <p>Especifica la moneda predeterminada utilizada para almacenar todos los datos monetarios. El sistema de informes de Analytics convierte las transacciones en otras monedas a la divisa base, utilizando la tasa de conversión actual en el momento en que recibe los datos. </p> <p> Los informes de Analytics usan la variable Variable <span class="varname">currencyCode</span> de JavaScript para identificar la divisa de una determinada transacción. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Deshabilitar compatibilidad con caracteres de byte múltiple </span> </td> 
   <td colname="col2"> <p>Deshabilita la compatibilidad con caracteres multibyte para el grupo de informes. Si se desactiva la compatibilidad con caracteres multibyte, el sistema supone que los datos están en formato ISO-8859-1. Las páginas web deben especificar su conjunto de caracteres en la variable Variable <span class="varname">charSet</span> de JavaScript. </p> <p>La compatibilidad con caracteres multibyte almacena caracteres en el grupo de informes mediante UTF-8. Una vez recibidos, el sistema convierte los datos del conjunto de caracteres de la página web al conjunto de caracteres UTF-8, de modo que puede utilizar cualquier idioma en los informes de marketing. </p> <p>Póngase en contacto con el administrador de cuentas o con el servicio de atención al cliente para cambiar la compatibilidad de caracteres multibyte para un grupo de informes existente. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Activar los Ad Hoc Analysis en este grupo</span> </td> 
   <td colname="col2"> Permite ver este grupo de informes al realizar Ad Hoc Analysis. </td> 
  </tr> 
 </tbody> 
</table>

