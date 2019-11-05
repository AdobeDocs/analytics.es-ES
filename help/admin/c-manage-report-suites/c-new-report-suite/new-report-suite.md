---
description: Puede crear un nuevo grupo de informes seleccionando como modelo una plantilla predefinida o utilizando uno de los grupos de informes existentes.
seo-description: Puede crear un nuevo grupo de informes seleccionando como modelo una plantilla predefinida o utilizando uno de los grupos de informes existentes.
seo-title: Descargar la configuración del grupo de informes
solution: Analytics
title: Descargar la configuración del grupo de informes
topic: Herramientas de administración
uuid: 3508f684-11a3-4c8f-a233-bea6bafd57c0
translation-type: tm+mt
source-git-commit: 57fe1f6d613b9f54a5191ac8684d36bccfebf4e5

---


# Descargar la configuración del grupo de informes

Puede crear un nuevo grupo de informes seleccionando como modelo una plantilla predefinida o utilizando uno de los grupos de informes existentes.

Descripción de los elementos utilizados al [crear un grupo de informes](/help/admin/c-manage-report-suites/c-new-report-suite/t-create-a-report-suite.md).

> [!NOTE] La documentación [del grupo de informes](/help/components/vrs/c-workflow-vrs/vrs-create.md) virtuales muestra cómo crear grupos de informes virtuales.

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
   <td colname="col2"> <p>Especifica un ID único que contiene solamente caracteres alfanuméricos. La ID no se puede cambiar una vez creada. Adobe establece el prefijo de ID necesario, que no se puede cambiar tampoco. </p> <p>Cuando cree varios grupos de informes, asegúrese de que la convención de nomenclatura garantice ID de grupo de informes únicos. </p> </td> 
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
   <td colname="col2"> Define el dominio básico del grupo de informes (opcional). Esta URL funciona como filtro interno de URL si no se definen de forma explícita filtros internos de URL para el grupo de informes. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Página predeterminada</span> </td> 
   <td colname="col2"> <p>Reduce las repeticiones del valor <span class="wintitle">Página predeterminada</span> en las direcciones URL que encuentra (opcional). Si el informe <span class="wintitle">Páginas más populares</span> contiene direcciones URL en vez de nombres de páginas, esta opción evita que se registren varias URL para la misma página web. </p> <p>For example, the URLs<span class="filepath"> https://mysite.com</span> and <span class="filepath"> https://mysite.com/index.html</span> are typically the same page. You can remove extraneous filenames so that both these URLs show up as <span class="filepath"> https://mysite.com</span> in your reports. </p> <p>Si no se define este valor, Analytics quitará automáticamente los siguientes nombres de archivo de las direcciones URL: <span class="filepath">index.htm</span>, <span class="filepath">index.html</span>, <span class="filepath">index.cgi</span>, <span class="filepath">index.asp</span>, <span class="filepath">default.htm</span>, <span class="filepath">default.html</span>, <span class="filepath">default.cgi</span>, <span class="filepath">default.asp</span>, <span class="filepath">home.htm</span>, <span class="filepath">home.html</span>, <span class="filepath">home.cgi</span> y <span class="filepath">home.asp</span>. </p> <p>Para desactivar la depuración de nombres de archivos, especifique un valor de Página predeterminada que no aparezca nunca en las URL. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Fecha de lanzamiento </p> </td> 
   <td colname="col2">Informa a Adobe de la fecha en la que se espera que se active este grupo de informes. If your deployment schedule changes, provide an updated traffic estimate using the <span class="wintitle"> Permanent Expected Traffic</span> tool in <a href="/help/admin/c-traffic-management/traffic-management.md"> Traffic Management</a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Vistas de la página estimadas por día</span> </td> 
   <td colname="col2"> Indica la cantidad estimada de vistas de página que se espera que admita este grupo de informes cada día. Los volúmenes grandes de tráfico requieren un proceso de aprobación más largo. Para evitar que se retrase el procesamiento, indique una estimación lo más precisa que sea posible. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Moneda base</span> </td> 
   <td colname="col2"> <p>Especifica la divisa predeterminada que se usará para almacenar todos los datos monetarios. Analytics convierte las transacciones en otras monedas a la moneda base mediante la tasa de conversión vigente en el momento de recibir los datos. </p> <p> Los informes de Analytics usan la variable <span class="varname"> currencyCode</span> JavaScript variable to identify the currency of a given transaction. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Deshabilitar compatibilidad con caracteres de byte múltiple </span> </td> 
   <td colname="col2"> <p>Desactiva la compatibilidad con caracteres multibyte en el grupo de informes. Si se desactiva la compatibilidad con caracteres multibyte, el sistema supondrá que los datos están en formato ISO-8859-1. Las páginas web deben especificar su conjunto de caracteres en la variable Variable <span class="varname"> charSet</span> JavaScript. </p> <p>La compatibilidad con caracteres multibyte almacena los caracteres del grupo de informes en UTF-8. El sistema, al recibir los datos del conjunto de caracteres de la página web, los convierte al conjunto de caracteres UTF-8, para que pueda utilizar cualquier idioma en los informes de marketing. </p> <p>Para cambiar la compatibilidad de caracteres multibyte en un grupo de informes existente, el usuario debe ponerse en contacto con el Administrador de cuentas o Atención al cliente. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Activar los Ad Hoc Analysis en este grupo</span> </td> 
   <td colname="col2"> Permite ver este grupo de informes al realizar Ad Hoc Analysis. </td> 
  </tr> 
 </tbody> 
</table>

