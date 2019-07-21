---
description: 'null'
seo-description: 'null'
seo-title: Flujo de trabajo del RGPD de Adobe Analytics
title: Flujo de trabajo del RGPD de Adobe Analytics
uuid: f 24 e 8 be 3-8 b 5 c -409 b-ad 6 b -770198 ae 2549
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Flujo de trabajo del RGPD de Adobe Analytics

Le damos la bienvenida al flujo de trabajo de preparación para el RGPD y Adobe Analytics. En este flujo de trabajo se describen los pasos que debe seguir a fin de preparar su implementación de Adobe Analytics para cumplir los derechos de acceso y eliminación del RGPD de sus interesados.

<table id="table_0E561F62247A4D01B6E7180560082DC9"> 
 <thead> 
  <tr> 
   <th colname="col2" class="entry"> Descripción de tarea </th> 
   <th colname="col3" class="entry"> Vínculos a instrucciones y más información </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col2"> <p><img placement="break"  src="assets/step1_icon.png" id="image_15849358972A4846A54FCB51997576D5" />Asegúrese de que todos sus grupos de informes que puedan contener datos relevantes en el marco del RGPD estén asignados a su organización de Experience Cloud (o IMS). </p> <p>Las solicitudes de RGPD se presentan mediante una organización de Experience Cloud y se aplicarán a todos los grupos de informes pertenecientes a dicha organización. Las solicitudes no se aplican a los grupos de informes que no estén asignados a la organización, aunque formen parte de su empresa de inicio de sesión. </p> </td> 
   <td colname="col3"> <p>Consulte <a href="https://marketing.adobe.com/resources/help/en_US/mcloud/report-suite-mapping.html" format="html" scope="external">Asignación de grupos de informes a una organización</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p><img placement="break"  src="assets/step2_icon.png" id="image_372B2C65DFAD46E39AE4D715313ABD0E"/> Establezca su política de retención de datos. </p> </td> 
   <td colname="col3"> <p>Debe haberse configurado una política de retención de datos para que Adobe pueda tratar las solicitudes de acceso o eliminación de datos del RGPD. </p> <p>Para obtener más información, consulte estas <a href="https://marketing.adobe.com/resources/help/en_US/reference/data-retention-client-table-faq.html" format="html" scope="external">Preguntas frecuentes de retención de datos de Analytics</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p><img placement="break"  src="assets/step3_icon.png" id="image_30DB956290CC4E64A7085B46364BE059" /> Familiarícese con las etiquetas DULE/GDPR, los ID de Adobe Analytics, los espacios de nombres y la expansión de ID. </p> </td> 
   <td colname="col3"> <p> Lea estos temas en este conjunto de documentación: 
     <ul id="ul_F6E94B9281D446DB8F1F859F6056543B"> 
      <li id="li_6389D094B4B04CA181E5F077BF8C0F8E"><a href="../../admin/c-data-governance/gdpr-labels.md#concept_F4061E29353446B5B0A7CF248D54E6F2" format="dita" scope="local"> Etiquetas del RGPD para variables de Analytics</a> </li> 
      <li id="li_CEEF2106E37845A49E0EA1225D5CFF14">Elemento de lista </li> 
      <li id="li_0B79CEBD074A4C68923EE9C9766D4B9D"><a href="../../admin/c-data-governance/gdpr-analytics-ids.md#concept_1BC4CA94B559481F8B08776DA100B23E" format="dita" scope="local"> Prácticas recomendadas de etiquetado</a> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p><img  src="assets/step4_icon.png" id="image_FE2039B8345248BCA303B44C10B68EA1" placement="break" /> Asigne etiquetas de identidad, confidencialidad y control de datos a cada variable de un grupo de informes. </p> <p>Nota: Recuerde que el etiquetado debe revisarse cada vez que se crea un nuevo grupo de informes o cuando se activa una nueva variable dentro de un grupo de informes existente. También es posible que necesite revisar el etiquetado cuando se activen nuevas integraciones de la solución, ya que pueden exponer nuevas variables que pueden requerir etiquetado. Una reimplementación de sus aplicaciones móviles o sitios web puede cambiar la forma en la que se utilizan las variables existentes, las cuales también pueden necesitar la actualización de las etiquetas. </p> </td> 
   <td colname="col3"> <p> Follow the instructions in <a href="../../admin/c-data-governance/gdpr-setup-reportsuite.md#concept_FAA948AD8CEA4BC38CB482EAF3648731" format="dita" scope="local"> Label Report Suite Data</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p><img placement="break"  src="assets/step5_icon.png" id="image_E9BEF83BF30F4528A030F23F71E5E5D8" /> Conéctese a la API de RGPD de Adobe y envíe solicitudes de acceso y eliminación. </p> </td> 
   <td colname="col3"> <p>Como cliente de Adobe Analytics, puede enviar solicitudes de RGPD individuales para acceder a datos de clientes y eliminarlos; para ello, debe llamar a la <a href="https://www.adobe.io/apis/cloudplatform/gdpr.html" format="html" scope="external">API de RGPD de Adobe Experience Cloud</a>. </p> <p>Puede enviar cualquier identificador de Analytics (como se describe en la sección <a href="../../admin/c-data-governance/gdpr-analytics-ids.md#concept_1BC4CA94B559481F8B08776DA100B23E" format="dita" scope="local">Prácticas recomendadas de etiquetado</a>) en las solicitudes, junto con sus respectivos ID de espacio de nombres (ID de fuentes de datos). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p><img placement="break"  src="assets/step6_icon.png" id="image_5CF03706FECD4F8BBAE0D0C19F98B8BB" /> Consulte y gestione la configuración del RGPD de su grupo de informes. </p> </td> 
   <td colname="col3"> <p>Follow the instructions in <a href="../../admin/c-data-governance/gdpr-view-settings.md#concept_7759BAD6F3174901A94116D189AEF80E" format="dita" scope="local"> View Report Suite's Data Governance Settings</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>
