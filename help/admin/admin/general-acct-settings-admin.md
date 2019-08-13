---
description: Descripciones de los campos de configuración de la cuenta generales para grupos de informes en Administradores.
seo-description: Descripciones de los campos de Valores de cuenta generales para grupos de informes en Administradores.
seo-title: Configuración de la cuenta generales
solution: Analytics
title: Configuración de la cuenta generales
topic: Herramientas de administración
uuid: c 1 ab 5 c 34-2 c 41-4 d 12-a 706-0 e 760 dff 8 a 95
translation-type: tm+mt
source-git-commit: 01ac0011f2e47e6798a520df8ffe5d8393ac0c3c

---


# Configuración de la cuenta generales

Descripciones de los campos de configuración de la cuenta generales para grupos de informes en Administradores.

**[!UICONTROL Analytics]** &gt; **[!UICONTROL Administración]** &gt; **[!UICONTROL Grupos de informes]** &gt; **[!UICONTROL Editar configuración]** &gt; **[!UICONTROL General]** &gt; **[!UICONTROL Configuración general de cuenta]**

Estos valores de configuración contienen opciones de edición para la funcionalidad básica del grupo de informes como, por ejemplo, nombre y zona horaria.

<table id="table_5448A694DC0A48D2B20C7F1332509F6E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Opción </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Título del sitio</span> </td> 
   <td colname="col2"> <p>Identifica el sitio. Asigne a cada grupo de informes un título de sitio único. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Dirección URL base</span> </td> 
   <td colname="col2"> <p>Especifica el sitio web principal del grupo de informes. La URL básica no afecta al filtrado de referentes. En su lugar, utilice <a href="../../admin/admin/internal-url-filter-admin.md#concept_D6BB8358DB7643F0B13E5DC9B7607998" format="dita" scope="local"> filtros de URL internos</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Zona horaria</span> </td> 
   <td colname="col2"> <p>Determina la fecha y la hora asociadas con los datos del informe. </p> <p>Si se cambia la zona horaria de un grupo de informes activo, se creará un pico o un hueco en los datos del informe. Para minimizar el impacto, Adobe recomienda cambiar de zona horaria durante las horas de menor actividad; de este modo, se evita alterar los datos. </p> <p>Por ejemplo, si cambia la zona horaria del grupo de informes de Turquía a Portugal a las 3 de la tarde, la hora actual del grupo de informes pasará a ser la 1. Dado que los informes ya han recopilado los datos de la 1, en los informes aparecerá un pico de tráfico entre la 1 y las 3. </p> <p>Por otra parte, si cambia la zona horaria del grupo de informes de Portugal a España a las 3 de la tarde, la hora actual del grupo de informes pasará a ser las 4. En los informes no aparecerá ningún dato entre las 3 y las 4 de la tarde el día que se cambie la hora. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Nivel de conversión</span> </td> 
   <td colname="col2"> <p> Activa o desactiva las variables de comercio electrónico, como las eVars y las campañas. Utilice la opción <span class="uicontrol">Activado, sin carro de compras</span> para ocultar todos los informes de carro de compras si no tiene un carro de compras en el sitio. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Página predeterminada</span> </td> 
   <td colname="col2"> <p> Si el informe <span class="wintitle">Páginas más populares</span> contiene direcciones URL en lugar de nombres de páginas, esta configuración evita que varias URL representen a la misma página. For example, the URLs <span class="filepath"> https://mysite.com</span> and <span class="filepath"> https://mysite.com/index.html</span> are typically the same page. You can remove default filenames so that these two URLs would both show up as <span class="filepath"> https://mysite.com</span>. </p> <p>Si se deja en blanco, los siguientes nombres de archivo se eliminarán de las direcciones URL: <span class="filepath">index.htm</span>, <span class="filepath">index.html</span>, <span class="filepath">index.cgi</span>, <span class="filepath">index.asp</span>, <span class="filepath">default.htm</span>, <span class="filepath">default.html</span>, <span class="filepath">default.cgi</span>, <span class="filepath">default.asp</span>, <span class="filepath">home.htm</span>, <span class="filepath">home.html</span>, <span class="filepath">home.cgi</span> y <span class="filepath">home.asp</span>. </p> <p>Para no desactivar por completo la depuración de nombre de archivo, ingrese un valor que nunca esté presente en las direcciones URL. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><span class="wintitle"> Reemplazar el último octeto de direcciones IP por 0 </span> </td> 
   <td colname="col2"> <p>La eliminación del último octeto se realiza antes del filtrado de IP. Como tal, el último octeto se sustituye por un 0 y las reglas de exclusión de la IP se deben actualizar para coincidir con las direcciones de IP que tengan un cero al final. Un * coincidente debe corresponder a un 0. </p> <p>Si activa esta opción, la dirección IP se modifica antes de procesarse. Por ejemplo, si la dirección IP 134.123.567.780 se cambia a 134.123.567.0., los datos de segmentación geográfica no serán tan exactos como cuando se utiliza la dirección IP completa. Específicamente, la precisión de ciudad se verá más afectada que la precisión de país o región. Tanto las reglas de Bot como las reglas de VISTA se ven afectadas porque ninguna de las direcciones IP está disponible para estas. Además, esta opción afecta a todas las reglas de procesamiento basadas en IP, incluidas las reglas de canal de marketing y las reglas de procesamiento de grupo de informes. </p> <p>Nota: Esta configuración está habilitada por defecto para cualquier grupo de informes creado en el Centro de datos de Londres a partir de enero de 2019, pero solo si la configuración de dichos grupos de informes se copia de una plantilla incluida en Admin Console. Los grupos de informes cuya configuración esté duplicada desde otros grupos de informes heredarán toda la configuración del grupo de informes seleccionado. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Confusión de IP</span> </td> 
   <td colname="col2"> <p>Convierte las direcciones IP en cadenas irreconocibles, lo que esencialmente las elimina de los almacenes de datos de Adobe. Cuando la confusión de IP está activada, las direcciones IP originales se pierden de forma permanente. </p> <p>Nota: Las direcciones IP se confunden en cualquier lugar de Analytics, incluido el Data Warehouse. Sin embargo, la configuración de la IP en el destino se controla de forma independiente, por lo que no influye en el destino. </p> <p>Si la confusión de la IP está habilitada, la exclusión de la IP se produce antes de que la dirección IP se confunda, por lo que los clientes no necesitan cambiar nada cuando habilitan la confusión de la IP. </p> <p>Si activa <span class="uicontrol">Deshabilitado</span>, se respeta la dirección IP de los datos. </p> <p>La activación de la opción <span class="uicontrol">Proteger direcciones IP</span> cambia la IP a un valor hash (p. ej., 234abc6493872038). </p> <p>Si activa la opción <span class="uicontrol">Eliminar direcciones IP</span>, se sustituye la dirección IP por x.x.x.x en los datos después de la búsqueda geográfica. </p> <p>Nota: Esta configuración puede necesitar cambios en las reglas <a href="../../admin/admin/bot-removal/bot-rules.md#concept_A306689C65EB4D0F9AE65E3FD48ED5F7" format="dita" scope="local"> de bots personalizadas</a> o<a href="../../admin/admin/exclude-ip.md#concept_265A95A803F740629CAAAA7EB8BE81A4" format="dita" scope="local"> en las exclusiones de IP</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Almacenamiento del ID de transacción</span> </td> 
   <td colname="col2"> <p>Permite utilizar las fuentes de datos de <a href="https://marketing.adobe.com/resources/help/en_US/sc/datasources/index.html?f=c_Transaction_ID" format="https" scope="external">ID de la transacción</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><span class="wintitle"> Activar Ad Hoc Analysis</span> </td> 
   <td colname="col2"> <p>Indica si el grupo de informes en cuestión se muestra como un grupo de informes disponible en un Ad Hoc Analysis. Utilice esta configuración para limitar los grupos de informes que aparecerán como opción en el Ad Hoc Analysis. Por ejemplo, puede deshabilitar el Ad Hoc Analysis para grupos de informes de desarrollo e informes de QA. </p> </td> 
  </tr> 
  <tr> 
   <td><span class="wintitle"> Habilitar Data Warehouse</span> </td> 
   <td colname="col2"> <p>Permite habilitar la IU del Data Warehouse en <span class="uicontrol">Herramientas</span> &gt; <span class="uicontrol">Data Warehouse</span>. </p> </td> 
  </tr> 
 </tbody> 
</table>

