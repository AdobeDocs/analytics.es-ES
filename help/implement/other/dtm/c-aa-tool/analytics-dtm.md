---
description: Implemente Adobe Analytics mediante el uso de Dynamic Tag Management. Para ello, debe crear la herramienta Adobe Analytics y configurar el código de página de forma automática o manual. Para la mayoría de los usuarios, se recomienda seguir el método automático.
keywords: Analytics Implementation;implementation method;dynamic tag management;dtm;analytics tool;property;tool type;tool name;configuration method;analytics premium;evars;events
title: Agregar la herramienta Adobe Analytics
topic: Developer and implementation
uuid: 1c54331e-de03-4f44-8002-a19723c585b0
translation-type: ht
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: ht
source-wordcount: '750'
ht-degree: 100%

---


# Agregar la herramienta Adobe Analytics

Implemente Adobe Analytics mediante el uso de Dynamic Tag Management. Para ello, debe crear la herramienta Adobe Analytics y configurar el código de página de forma automática o manual. Para la mayoría de los usuarios, se recomienda seguir el método automático.

>[!NOTE]
>
>Para mejorar el seguimiento de visitantes, recomendamos que habilite el [Servicio de identidad](https://docs.adobe.com/content/help/es-ES/id-service/using/home.html).

## Agregar una herramienta Adobe Analytics {#section_D5066B21581B4F7F811AD0027BF44EA5}

1. Haga clic en **[!UICONTROL *`Web Property Name`*]** > **[!UICONTROL  Información general ]** > **[!UICONTROL  Agregar una herramienta ]** > **[!UICONTROL  Adobe Analytics ]**.

   ![](assets/dtm-add-analytics-tool.png)

1. Rellene los campos:

<table id="table_1CFB53FE72E74CCB8CAA5D4E3873D286"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Tipo de herramienta </p> </td> 
   <td colname="col2">Tipo de herramienta, como <span class="keyword">Adobe Analytics</span>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Nombre de la herramienta </p> </td> 
   <td colname="col2">Un nombre descriptivo para esta herramienta. Este nombre se muestra en la ficha <span class="wintitle">Información general</span> en <span class="wintitle">Herramientas instaladas</span>. </td> 
  </tr> 
  <tr> 
   <td colname="col1" morerows="1"> <p>Método de configuración </p> </td> 
   <td colname="col2"> <p> <b>Automático</b> (recomendado): utiliza Dynamic Tag Management para gestionar la configuración. Este método permite la sincronización automática de los grupos de informes de <span class="keyword">Adobe Analytics</span> mediante el inicio de sesión en <span class="keyword">Experience Cloud</span> o el ID de servicios web, a la vez que gestiona el código de AppMeasurement. </p> <p>Una vez que las cuentas están conectadas, Dynamic Tag Management extrae los nombres e ID de los grupos de informes de <span class="keyword">Adobe Analytics</span> en la interfaz de configuración de la herramienta, lo que permite aumentar la velocidad de implementación de la herramienta con menos posibilidades de que se produzcan errores de usuarios. </p> <p> <p>Nota: Debe elegir la opción <span class="wintitle">Automático</span> si es cliente de <span class="keyword">Adobe Analytics Premium</span>. </p> </p> <p>Rellene los campos específicos de la configuración automática: </p> 
    <ul id="ul_8D9797B01E444B9C85B862A9F96B447C"> 
     <li id="li_0AC84C1F37B24C658F2178E50ECCC4B0"> <p> <b>Experience Cloud</b>: (predeterminado) utiliza el inicio de sesión único de <span class="keyword">Experience Cloud</span>. Especifique su Experience Cloud ID y su contraseña. </p> </li> 
     <li id="li_6C80468835D04CC09F4AEC46D1300310"> <p><b>Servicios web</b>: especifique su nombre de usuario y secreto compartido de los servicios web. </p> <p>Las credenciales de secreto compartido se encuentran en <span class="uicontrol">Administración</span> &gt; <span class="uicontrol">Configuración de la empresa</span> &gt; <a href="https://docs.adobe.com/content/help/es-ES/analytics/admin/company-settings/web-services-admin.html">Servicios web</a>. </p> <p>Los desarrolladores pueden consultar <a href="https://marketing.adobe.com/developer/en_US/get-started/enterprise-api/c-get-web-service-access-to-the-enterprise-api">Acceso a servicios web para la API empresarial</a> para obtener ayuda sobre la obtención de credenciales de los servicios web. </p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p> <b>Manual</b>: administra de forma manual el código de AppMeasurement. Puede descargar el código de <span class="keyword">AppMeasurement</span> de <span class="keyword">Analytics</span> desde <span class="ignoretag"><span class="uicontrol"> Herramientas de administración</span> &gt; <span class="uicontrol">Administrador de códigos</span></span>. </p> <p>Haga clic en <a href="https://docs.adobe.com/content/help/es-ES/analytics/implementation/js/migrate-from-hcode.html">JavaScript (nuevo)</a> para obtener información sobre cómo descargar el código localmente para copiarlo y pegarlo en el campo <span class="wintitle">Editar código</span> en <a href="/help/implement/other/dtm/c-aa-tool/library-management.md">Administración de bibliotecas</a>. </p> <p>Rellene los campos específicos de la configuración manual: </p> 
    <ul id="ul_CFB6CE78AEB743EF8B47BAAC42E2DB0A"> 
     <li id="li_5B7046CD95AB416F8C113B381A264D91"> <p><b>ID de la cuenta de producción:</b> (obligatorio) su cuenta de producción para la recopilación de datos. En Analytics, este es su ID para el grupo de informes. Dynamic Tag Management instala automáticamente la cuenta correcta en el entorno de producción y ensayo. </p> </li> 
     <li id="li_14E840FD79A0451BABEDD15DC0584768"> <p><b>ID de la cuenta de ensayo:</b> (obligatorio) se utiliza en el entorno de desarrollo o prueba. En Analytics, este es su ID para el grupo de informes. Una cuenta de ensayo mantiene los datos de prueba separados de la producción. </p> </li> 
     <li id="li_69E6C6A41F5240E1ABE8ABE0B9D151FC"> <p><b>Servidor de seguimiento:</b> especifique la información de su servidor de seguimiento </p> <p>Las variables <span class="wintitle">Servidor de seguimiento</span> y <span class="wintitle">Servidor de seguimiento SSL</span> se utilizan en la implementación de cookies personales para especificar el dominio en el cual se escribe la cookie y la solicitud de imagen. Para obtener más información, consulte el artículo <a href="https://helpx.adobe.com/es/analytics/kb/determining-data-center.html">Rellenar correctamente las variables trackingServer y trackingServerSecure</a>. </p> </li> 
     <li id="li_1A7271C68205428F8CA5548A96CACBEC"> <p><b>Servidor de seguimiento SSL:</b> especifique la información de su servidor de seguimiento SSL. </p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

1. Haga clic en **[!UICONTROL Crear herramienta]** para crear la herramienta y mostrarla en el editor.

   Las herramientas se muestran en la ficha [!UICONTROL Información general], bajo [!UICONTROL Herramientas instaladas].

1. (Condicional) Configure la herramienta según sus necesidades siguiendo las instrucciones de los vínculos [!UICONTROL General], [!UICONTROL Administración de biblioteca], [!UICONTROL Variables globales], [!UICONTROL Vistas de página y contenido], [!UICONTROL Seguimiento de vínculos], [!UICONTROL Referentes y campañas], [!UICONTROL Cookies] y [!UICONTROL Personalizar código de página].

Consulte [Preguntas más frecuentes sobre la herramienta Adobe Analytics](/help/implement/faq.md) para obtener más información al respecto.

## Editar una herramienta Adobe Analytics existente {#section_148B16AF429B4949B06238D90635B726}

Puede editar una herramienta Adobe Analytics existente para modificar sus ajustes de configuración.

1. Haga clic en el icono ![](assets/settings_gear.png) situado junto a una herramienta instalada en la ficha [!UICONTROL Información general].
1. Edite los campos como desee.

   En la tabla siguiente se incluyen solo los elementos que no están disponibles al crear una herramienta Analytics, según lo descrito anteriormente. No obstante, puede modificar cualquier elemento de la página, según se describe en ambas tablas.

<table id="table_2B60CD109CFF4839AB7F91D61125EDFF"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Habilitar la configuración automática </p> </td> 
   <td colname="col2"> <p>Nota: Al habilitar esta configuración, se cambia una implementación configurada manualmente al método de configuración automática descrito en <span class="term">Método de configuración</span>. </p> <p>Esta opción permite a Dynamic Tag Management recuperar automáticamente la configuración de la cuenta de <span class="keyword">Adobe Analytics</span>. </p> <p>Se utiliza el código de AppMeasurement más reciente disponible y se muestran las notificaciones de actualización para su selección cuando hay nuevas versiones disponibles. También puede revertir a las versiones de AppMeasurement anteriores según sea necesario como, por ejemplo, por motivos de compatibilidad. Se muestran hasta cinco versiones anteriores. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Actualizar credenciales </p> </td> 
   <td colname="col2"> <p>Puede actualizar la API, por ejemplo, para actualizar los grupos de informes asociados a un usuario. </p> </td> 
  </tr> 
 </tbody> 
</table>

1. (Condicional) Configure la herramienta según sus necesidades siguiendo las instrucciones de los vínculos [!UICONTROL General], [!UICONTROL Administración de biblioteca], [!UICONTROL Variables globales], [!UICONTROL Vistas de página y contenido], [!UICONTROL Seguimiento de vínculos], [!UICONTROL Referentes y campañas], [!UICONTROL Cookies] y [!UICONTROL Personalizar código de página].
1. Haga clic en **[!UICONTROL Guardar cambios]**.
