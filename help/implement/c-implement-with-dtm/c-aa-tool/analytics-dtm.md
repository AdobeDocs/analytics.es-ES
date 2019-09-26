---
description: Para implementar Adobe Analytics mediante la administración dinámica de etiquetas, cree la herramienta Adobe Analytics y configure el código de página de forma automática o manual. Para la mayoría de los usuarios, se recomienda seguir el método automático.
keywords: Analytics Implementation;implementation method;dynamic tag management;dtm;analytics tool;property;tool type;tool name;configuration method;analytics premium;evars;events
seo-description: Deploy Adobe Analytics using Dynamic Tag Management by creating the Adobe Analytics tool and configuring the page code either automatically or manually. Para la mayoría de los usuarios, se recomienda seguir el método automático.
seo-title: Agregar la herramienta Adobe Analytics
solution: Analytics
title: Agregar la herramienta Adobe Analytics
topic: Desarrollador e implementación
uuid: 1c54331e-de03-4f44-8002-a19723c585b0
translation-type: tm+mt
source-git-commit: 831ae375a90f021feddc6817a2602464be0d8414

---


# Agregar la herramienta Adobe Analytics

Deploy Adobe Analytics using Dynamic Tag Management by creating the Adobe Analytics tool and configuring the page code either automatically or manually. Para la mayoría de los usuarios, se recomienda seguir el método automático.

>[!NOTE]
>
>For improved visitor tracking, we strongly recommend that you enable [Identity Service](https://marketing.adobe.com/resources/help/en_US/mcvid/).

## Agregar una herramienta Adobe Analytics {#section_D5066B21581B4F7F811AD0027BF44EA5}

1. Click  **[!UICONTROL *`Web Property Name`*]** &gt; **[!UICONTROL Overview]** &gt; **[!UICONTROL Add a Tool]** &gt; **[!UICONTROL Adobe Analytics]** .

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
   <td colname="col2"> <p> <b>Automático</b> (recomendado): utiliza Dynamic Tag Management para gestionar la configuración. This method enables automatic synchronization of <span class="keyword"> Adobe Analytics</span> report suites via a <span class="keyword"> Experience Cloud</span> login or Web Services ID, and manages the [!DNL AppMeasurement] code. </p> <p>Una vez que las cuentas están conectadas, Dynamic Tag Management extrae los nombres e ID de los grupos de informes de <span class="keyword">Adobe Analytics</span> en la interfaz de configuración de la herramienta, lo que permite aumentar la velocidad de implementación de la herramienta con menos posibilidades de que se produzcan errores de usuarios. </p> <p> <p>Nota: Debe elegir la opción <span class="wintitle">Automático</span> si es cliente de <span class="keyword">Adobe Analytics Premium</span>. Consulte <a href="../../../implement/c-implement-with-dtm/c-aa-tool/analytics-dtm.md#section_AEAA44566B5A46D2922E17A11D7EA217" format="dita" scope="local">Habilitación de Adobe Analytics Premium</a>. </p> </p> <p>Rellene los campos específicos de la configuración automática: </p> 
    <ul id="ul_8D9797B01E444B9C85B862A9F96B447C"> 
     <li id="li_0AC84C1F37B24C658F2178E50ECCC4B0"> <p> <b>Experience Cloud</b>: (predeterminado) utiliza el inicio de sesión único de <span class="keyword">Experience Cloud</span>. Especifique su Experience Cloud ID y su contraseña. </p> </li> 
     <li id="li_6C80468835D04CC09F4AEC46D1300310"> <p><b>Servicios web</b>: especifique su nombre de usuario y secreto compartido de los servicios web. </p> <p>Shared secret credentials are located in <span class="uicontrol"> Admin </span> &gt; <span class="uicontrol"> Company Settings</span> &gt; <a href="https://docs.adobe.com/content/help/en/analytics/admin/company-settings/web-services-admin.html" format="html" scope="external"> Web Services</a>. </p> <p>Los desarrolladores pueden consultar <a href="https://marketing.adobe.com/developer/en_US/get-started/enterprise-api/c-get-web-service-access-to-the-enterprise-api" format="https" scope="external">Acceso a servicios web para la API empresarial</a> para obtener ayuda sobre la obtención de credenciales de los servicios web. </p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p> <b>Manual</b>: Administrar manualmente el código de [!DNL AppMeasurement]. Puede descargar el código de <span class="keyword">AppMeasurement</span> de <span class="keyword">Analytics</span> desde <span class="ignoretag"><span class="uicontrol">Herramientas de administración</span> &gt; <span class="uicontrol">Administrador de códigos</span></span>. </p> <p>Click <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/appmeasure_mjs.html" format="https" scope="external"> JavaScript (new)</a> for information about downloading the code locally to copy and paste in the <span class="wintitle"> Edit Code</span> field in <a href="../../../implement/c-implement-with-dtm/c-aa-tool/library-management.md#concept_24654766343B4E82A9416A112D2125FE" format="dita" scope="local"> Library Management</a>. </p> <p>Rellene los campos específicos de la configuración manual: </p> 
    <ul id="ul_CFB6CE78AEB743EF8B47BAAC42E2DB0A"> 
     <li id="li_5B7046CD95AB416F8C113B381A264D91"> <p><b>ID de la cuenta de producción:</b> (obligatorio) su cuenta de producción para la recopilación de datos. En Analytics, este es su ID para el grupo de informes. Dynamic Tag Management instala automáticamente la cuenta correcta en el entorno de producción y ensayo. </p> </li> 
     <li id="li_14E840FD79A0451BABEDD15DC0584768"> <p><b>ID de la cuenta de ensayo:</b> (obligatorio) se utiliza en el entorno de desarrollo o prueba. En Analytics, este es su ID para el grupo de informes. Una cuenta de ensayo permite separar los datos de prueba de los de producción. </p> </li> 
     <li id="li_69E6C6A41F5240E1ABE8ABE0B9D151FC"> <p><b>Servidor de seguimiento:</b> especifique la información de su servidor de seguimiento. </p> <p>Las variables <span class="wintitle">Servidor de seguimiento</span> y <span class="wintitle">Servidor de seguimiento SSL</span> se utilizan en la implementación de cookies personales para especificar el dominio en el cual se escribe la cookie y la solicitud de imagen. Para obtener más información, consulte el artículo <a href="https://helpx.adobe.com/analytics/kb/determining-data-center.html" format="https" scope="external">Rellenar correctamente las variables trackingServer y trackingServerSecure</a>.  </p> </li> 
     <li id="li_1A7271C68205428F8CA5548A96CACBEC"> <p><b>Servidor de seguimiento SSL:</b> especifique la información de su servidor de seguimiento SSL. </p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

1. Haga clic en **[!UICONTROL Crear herramienta]para crear la herramienta y mostrarla en el editor.**

   Las herramientas se muestran en la ficha [!UICONTROL Información general], bajo [!UICONTROL Herramientas instaladas].

1. (Condicional) Configure la herramienta según sus necesidades siguiendo las instrucciones de los vínculos [!UICONTROL General], [!UICONTROL Administración de biblioteca], [!UICONTROL Variables globales], [!UICONTROL Vistas de página y contenido], [!UICONTROL Seguimiento de vínculos], [!UICONTROL Referentes y campañas], [!UICONTROL Cookies] y [!UICONTROL Personalizar código de página]. 

See [Frequently Asked Questions About the Adobe Analytics Tool](../../../implement/faq.md#concept_00DF9AF14D30469BB986BF56A448806B) for additional information about this tool.

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
   <td colname="col2"> <p>Note: Enabling this setting changes a manually configured implementation to the automatic configuration method described in <span class="term"> Configuration Method</span>. </p> <p>Esta opción permite a Dynamic Tag Management recuperar automáticamente la configuración de la cuenta de <span class="keyword">Adobe Analytics</span>. </p> <p>Se utiliza el último código disponible de [!DNL AppMeasurement] y se muestran las notificaciones de actualización para su selección a medida que las nuevas versiones están disponibles. También puede revertir a versiones anteriores de [!DNL AppMeasurement] según sea necesario, por ejemplo por motivos de compatibilidad. Se muestran hasta cinco versiones anteriores. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Actualizar credenciales </p> </td> 
   <td colname="col2"> <p>Puede actualizar la API, por ejemplo, para actualizar los grupos de informes asociados a un usuario. </p> </td> 
  </tr> 
 </tbody> 
</table>

1. (Condicional) Configure la herramienta según sus necesidades siguiendo las instrucciones de los vínculos [!UICONTROL General], [!UICONTROL Administración de biblioteca], [!UICONTROL Variables globales], [!UICONTROL Vistas de página y contenido], [!UICONTROL Seguimiento de vínculos], [!UICONTROL Referentes y campañas], [!UICONTROL Cookies] y [!UICONTROL Personalizar código de página]. 
1. Haga clic en **[!UICONTROL Guardar cambios]**.
