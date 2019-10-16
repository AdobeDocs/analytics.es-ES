---
description: 'null'
seo-description: 'null'
seo-title: Flujo de trabajo de privacidad de datos de Adobe Analytics
title: Flujo de trabajo de privacidad de datos de Adobe Analytics
uuid: f24e8be3-8b5c-409b-ad6b-770198ae2549
translation-type: tm+mt
source-git-commit: 45e3330adb562ec795d287ae1c1fa6b03a2b2a31

---


# Flujo de trabajo de privacidad de datos de Adobe Analytics

Bienvenido a Adobe Analytics y a la preparación para la privacidad de datos. Este flujo de trabajo describe los pasos que debe seguir para que la implementación de Adobe Analytics esté lista para admitir el acceso a la privacidad de datos de los usuarios y los derechos de eliminación de los mismos.

<table id="table_0E561F62247A4D01B6E7180560082DC9"> 
 <thead> 
  <tr> 
   <th colname="col2" class="entry"> Descripción de tarea </th> 
   <th colname="col3" class="entry"> Vínculos a instrucciones y más información </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col2"> <p><img placement="break"  src="assets/step1_icon.png" id="image_15849358972A4846A54FCB51997576D5" /> Asegúrese de que todos los grupos de informes que puedan contener datos relevantes para la privacidad de datos estén asignados a su organización de Experience Cloud (o IMS). </p> <p>Las solicitudes de privacidad de datos se envían mediante una organización de Experience Cloud y se aplican a todos los grupos de informes reclamados por esa organización. Las solicitudes no se aplican a los grupos de informes que no estén asignados a la organización, aunque formen parte de su empresa de inicio de sesión. </p> </td> 
   <td colname="col3"> <p>Consulte <a href="https://marketing.adobe.com/resources/help/en_US/mcloud/report-suite-mapping.html" format="html" scope="external">Asignación de grupos de informes a una organización</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p><img placement="break"  src="assets/step2_icon.png" id="image_372B2C65DFAD46E39AE4D715313ABD0E"/> Establezca su política de retención de datos. </p> </td> 
   <td colname="col3"> <p>Es necesario establecer una política de retención de datos para que Adobe pueda atender las solicitudes de acceso o eliminación de datos de privacidad de datos. </p> <p>Para obtener más información, consulte estas <a href="https://marketing.adobe.com/resources/help/en_US/reference/data-retention-client-table-faq.html" format="html" scope="external">Preguntas frecuentes de retención de datos de Analytics</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p><img placement="break"  src="assets/step3_icon.png" id="image_30DB956290CC4E64A7085B46364BE059" /> Familiarícese con las etiquetas DULE/Data Privacy, los ID de Adobe Analytics, los espacios de nombres y la expansión de ID. </p> </td> 
   <td colname="col3"> <p> Lea estos temas en este conjunto de documentación: 
     <ul id="ul_F6E94B9281D446DB8F1F859F6056543B"> 
      <li id="li_6389D094B4B04CA181E5F077BF8C0F8E"><!--<a href="/help/admin/c-data-governance/gdpr-labels.md#concept_F4061E29353446B5B0A7CF248D54E6F2" format="dita" scope="local"> Data Privacy Labels for Analytics Variables</a>--> </li> 
      <li id="li_CEEF2106E37845A49E0EA1225D5CFF14">Elemento de lista </li> 
      <li id="li_0B79CEBD074A4C68923EE9C9766D4B9D"><!--<a href="/help/admin/c-data-governance/gdpr-analytics-ids.md#concept_1BC4CA94B559481F8B08776DA100B23E" format="dita" scope="local"> Labeling Best Practices</a>--> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p><img  src="assets/step4_icon.png" id="image_FE2039B8345248BCA303B44C10B68EA1" placement="break" /> Asigne etiquetas de identidad, confidencialidad y control de datos a cada variable de un grupo de informes. </p> <p>Nota: Recuerde que el etiquetado debe revisarse cada vez que se crea un nuevo grupo de informes o cuando se activa una nueva variable dentro de un grupo de informes existente. También es posible que necesite revisar el etiquetado cuando se activen nuevas integraciones de la solución, ya que pueden exponer nuevas variables que pueden requerir etiquetado. Una reimplementación de sus aplicaciones móviles o sitios web puede cambiar la forma en la que se utilizan las variables existentes, las cuales también pueden necesitar la actualización de las etiquetas. </p> </td> 
   <td colname="col3"> <p> Siga las instrucciones de <!--<a href="/help/admin/c-data-governance/gdpr-setup-reportsuite.md#concept_FAA948AD8CEA4BC38CB482EAF3648731" format="dita" scope="local"> Label Report Suite Data</a>-->. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p><img placement="break"  src="assets/step5_icon.png" id="image_E9BEF83BF30F4528A030F23F71E5E5D8" /> Conéctese a la API de privacidad de datos de Adobe y envíe solicitudes de acceso y eliminación. </p> </td> 
   <td colname="col3"> <p>As an Adobe Analytics customer, you can submit individual Data Privacy requests to access and delete customer data, by calling the <a href="https://www.adobe.io/apis/cloudplatform/gdpr.html" format="html" scope="external"> Adobe Experience Cloud Data Privacy API</a>. </p> <p>You can submit any Analytics identifiers (as described in the section <!--<a href="/help/admin/c-data-governance/gdpr-analytics-ids.md#concept_1BC4CA94B559481F8B08776DA100B23E" format="dita" scope="local"> Labeling Best Practices</a>-->) in the requests along with their respective namespace IDs (data source IDs). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p><img placement="break"  src="assets/step6_icon.png" id="image_5CF03706FECD4F8BBAE0D0C19F98B8BB" /> Ver y administrar la configuración de privacidad de datos del grupo de informes. </p> </td> 
   <td colname="col3"> <p>Siga las instrucciones de <!--<a href="/help/admin/c-data-governance/gdpr-view-settings.md#concept_7759BAD6F3174901A94116D189AEF80E" format="dita" scope="local"> View Report Suite's Data Governance Settings</a>-->. </p> </td> 
  </tr> 
 </tbody> 
</table>

| Descripción de tarea | Vínculos a instrucciones y más información |
|--- |--- |
| **Paso 1**: Asegúrese de que todos los grupos de informes que puedan contener datos relevantes para la privacidad de datos estén asignados a su organización de Experience Cloud (o IMS).  Las solicitudes de privacidad de datos se envían mediante una organización de Experience Cloud y se aplican a todos los grupos de informes reclamados por esa organización. Las solicitudes no se aplican a los grupos de informes que no estén asignados a la organización, aunque formen parte de su empresa de inicio de sesión. | Consulte [Asignación de grupos de informes a una organización.](https://docs.adobe.com/content/help/en/core-services/interface/about-core-services/report-suite-mapping.html) |
| **Paso 2**: Establezca su política de retención de datos. | Es necesario establecer una política de retención de datos para que Adobe pueda atender las solicitudes de acceso o eliminación de datos de privacidad de datos.  Para obtener más información, consulte estas [Preguntas frecuentes de retención de datos de Analytics.](/help/technotes/data-retention.md) |
| **Paso 3**: Familiarícese con las etiquetas DULE/Data Privacy, los ID de Adobe Analytics, los espacios de nombres y la expansión de ID. | Lea estos temas en este conjunto de documentación:<ul><li>[Etiquetas de privacidad de datos para variables de Analytics](/help/admin/c-data-governance/gdpr-labels.md)</li><li>[Prácticas recomendadas de etiquetado](/help/admin/c-data-governance/gdpr-analytics-ids.md#concept_1BC4CA94B559481F8B08776DA100B23E)</li></ul> |
| **Paso 4**: Asigne etiquetas de identidad, confidencialidad y control de datos a cada variable de un grupo de informes.  Nota: Recuerde que el etiquetado debe revisarse cada vez que se crea un nuevo grupo de informes o cuando se activa una nueva variable dentro de un grupo de informes existente. También es posible que necesite revisar el etiquetado cuando se activen nuevas integraciones de la solución, ya que pueden exponer nuevas variables que pueden requerir etiquetado. Una reimplementación de sus aplicaciones móviles o sitios web puede cambiar la forma en la que se utilizan las variables existentes, las cuales también pueden necesitar la actualización de las etiquetas. | Sigue las instrucciones de [ Etiquetado de datos de grupos de informes.](/help/admin/c-data-governance/gdpr-setup-reportsuite.md#concept_FAA948AD8CEA4BC38CB482EAF3648731) |
| **Paso 5**: Conéctese a la API de privacidad de datos de Adobe y envíe solicitudes de acceso y eliminación. | As an Adobe Analytics customer, you can submit individual Data Privacy requests to access and delete customer data, by calling the [Adobe Experience Cloud Data Privacy API.](https://www.adobe.io/apis/experienceplatform/gdpr.html) Puede enviar cualquier identificador de Analytics (como se describe en la sección [Prácticas recomendadas de etiquetado](/help/admin/c-data-governance/gdpr-analytics-ids.md#concept_1BC4CA94B559481F8B08776DA100B23E)) en las solicitudes, junto con sus respectivos ID de área de nombres (ID de fuentes de datos). |
| **Paso 6**: Ver y administrar la configuración de privacidad de datos del grupo de informes. | Siga las instrucciones de [ Ver configuración de control de datos de los grupos de informes.](/help/admin/c-data-governance/gdpr-view-settings.md) |
