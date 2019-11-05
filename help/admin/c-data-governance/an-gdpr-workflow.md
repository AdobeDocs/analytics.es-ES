---
description: 'null'
seo-description: 'null'
seo-title: Flujo de trabajo de privacidad de datos de Adobe Analytics
title: Flujo de trabajo de privacidad de datos de Adobe Analytics
uuid: f24e8be3-8b5c-409b-ad6b-770198ae2549
translation-type: tm+mt
source-git-commit: 8c4c368a84ba5499d85f0b7512c99de47ddb14c2

---


# Flujo de trabajo de privacidad de datos de Adobe Analytics

Le damos la bienvenida al flujo de trabajo de preparación para la privacidad de datos y Adobe Analytics. En este flujo de trabajo se describen los pasos que debe seguir a fin de preparar su implementación de Adobe Analytics para cumplir los derechos de acceso y eliminación de privacidad de datos de sus interesados.

<!--
<table id="table_0E561F62247A4D01B6E7180560082DC9"> 
 <thead> 
  <tr> 
   <th colname="col2" class="entry"> Task Description </th> 
   <th colname="col3" class="entry"> Links to Instructions and More Information </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col2"> <p><img placement="break"  src="assets/step1_icon.png" id="image_15849358972A4846A54FCB51997576D5" /> Ensure that any of your report suites that might contain Data Privacy-relevant data are mapped to your Experience Cloud (or IMS) organization. </p> <p>Data Privacy requests are submitted using an Experience Cloud Organization and will be applied to all report suites claimed by that Organization. Requests will not apply to report suites not mapped to that Organization, even if they are part of your login company. </p> </td> 
   <td colname="col3"> <p>Refer to <a href="https://marketing.adobe.com/resources/help/en_US/mcloud/report-suite-mapping.html"> Map report suites to an organization</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p><img placement="break"  src="assets/step2_icon.png" id="image_372B2C65DFAD46E39AE4D715313ABD0E"/> Set your data retention policy. </p> </td> 
   <td colname="col3"> <p>A data retention policy needs to be in place in order for Adobe to service Data Privacy data access/delete requests. </p> <p>For more information, see this <a href="https://marketing.adobe.com/resources/help/en_US/reference/data-retention-client-table-faq.html"> Analytics Data Retention FAQ</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p><img placement="break"  src="assets/step3_icon.png" id="image_30DB956290CC4E64A7085B46364BE059" /> Familiarize yourself with DULE/Data Privacy labels, Adobe Analytics IDs, namespaces, and ID expansion. </p> </td> 
   <td colname="col3"> <p> Read these topics in this documentation set: 
     <ul> 
      <li><a href="/help/admin/c-data-governance/gdpr-labels.md"> Data Privacy Labels for Analytics Variables</a> </li> 
      <li><a href="/help/admin/c-data-governance/gdpr-analytics-ids.md"> Labeling Best Practices</a>--> </li>
    &lt;/ul&gt; &lt;/p&gt; &lt;/td&gt;
</tr> 
  <tr> 
   <td colname="col2"> <p><img  src="assets/step4_icon.png" id="image_FE2039B8345248BCA303B44C10B68EA1" placement="break" /> Asigne etiquetas de identidad, confidencialidad y control de datos a cada variable de un grupo de informes. </p> <p>Nota: Recuerde que el etiquetado debe revisarse cada vez que se crea un nuevo grupo de informes o cuando se activa una nueva variable dentro de un grupo de informes existente. También es posible que necesite revisar el etiquetado cuando se activen nuevas integraciones de la solución, ya que pueden exponer nuevas variables que pueden requerir etiquetado. Una reimplementación de sus aplicaciones móviles o sitios web puede cambiar la forma en la que se utilizan las variables existentes, las cuales también pueden necesitar la actualización de las etiquetas. </p> </td> 
   <td colname="col3"> <p> Sigue las instrucciones de <a href="/help/admin/c-data-governance/gdpr-setup-reportsuite.md"> Etiquetado de datos de grupos de informes</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p><img placement="break"  src="assets/step5_icon.png" id="image_E9BEF83BF30F4528A030F23F71E5E5D8" /> Conéctese a la API de Privacidad de datos de Adobe y envíe solicitudes de acceso y eliminación. </p> </td> 
   <td colname="col3"> <p>Como cliente de Adobe Analytics, puede enviar solicitudes de privacidad de datos individuales para acceder a datos de clientes y eliminarlos; para ello, debe llamar a la <a href="https://www.adobe.io/apis/cloudplatform/gdpr.html">API de privacidad de datos de Adobe Experience Cloud</a>. </p> <p>Puede enviar cualquier identificador de Analytics (como se describe en la sección <a href="/help/admin/c-data-governance/gdpr-analytics-ids.md">Prácticas recomendadas de etiquetado</a>) en las solicitudes, junto con sus respectivos ID de área de nombres (ID de fuentes de datos). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p><img placement="break"  src="assets/step6_icon.png" id="image_5CF03706FECD4F8BBAE0D0C19F98B8BB" /> Consulte y gestione la configuración de la privacidad de datos de su grupo de informes. </p> </td> 
   <td colname="col3"> <p>Siga las instrucciones de <a href="/help/admin/c-data-governance/gdpr-view-settings.md"> Ver configuración de control de datos de los grupos de informes</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>
--&gt;

| Descripción de tarea | Vínculos a instrucciones y más información |
|--- |--- |
| **Paso 1**: Compruebe que todos sus grupos de informes que puedan contener datos relevantes en el marco de la privacidad de datos estén asignados a su organización de Experience Cloud (o IMS).  Las solicitudes de privacidad de datos se presentan mediante una organización de Experience Cloud y se aplicarán a todos los grupos de informes pertenecientes a dicha organización. Las solicitudes no se aplican a los grupos de informes que no estén asignados a la organización, aunque formen parte de su empresa de inicio de sesión. | Consulte [Asignación de grupos de informes a una organización.](https://docs.adobe.com/content/help/en/core-services/interface/about-core-services/report-suite-mapping.html) |
| **Paso 2**: Configure la directiva de retención de datos. | Debe haberse configurado una política de retención de datos para que Adobe pueda tratar las solicitudes de acceso o eliminación de datos en la privacidad de datos.  Para obtener más información, consulte estas [Preguntas frecuentes de retención de datos de Analytics.](/help/technotes/data-retention.md) |
| **Paso 3**: Familiarícese con las etiquetas DULE/Privacidad de datos, los ID de Adobe Analytics, los áreas de nombres y la expansión de ID. | Lea estos temas en este conjunto de documentación:<ul><li>[Etiquetas de privacidad de datos para variables de Analytics](/help/admin/c-data-governance/gdpr-labels.md)</li><li>[Prácticas recomendadas de etiquetado](/help/admin/c-data-governance/gdpr-analytics-ids.md)</li></ul> |
| **Paso 4**: Asigne etiquetas de identidad, confidencialidad y control de datos a cada variable de un grupo de informes.  Nota: Recuerde que el etiquetado debe revisarse cada vez que se crea un nuevo grupo de informes o cuando se activa una nueva variable dentro de un grupo de informes existente. También es posible que necesite revisar el etiquetado cuando se activen nuevas integraciones de la solución, ya que pueden exponer nuevas variables que pueden requerir etiquetado. Una reimplementación de sus aplicaciones móviles o sitios web puede cambiar la forma en la que se utilizan las variables existentes, las cuales también pueden necesitar la actualización de las etiquetas. | Sigue las instrucciones de [Etiquetado de datos de grupos de informes.](/help/admin/c-data-governance/gdpr-setup-reportsuite.md) |
| **Paso 5**: Conéctese a la API de Privacidad de datos de Adobe y envíe solicitudes de acceso y eliminación. | Como cliente de Adobe Analytics, puede enviar solicitudes de privacidad de datos individuales para acceder a datos de clientes y eliminarlos; para ello, debe llamar a la [API de privacidad de datos de Adobe Experience Cloud.](https://www.adobe.io/apis/experienceplatform/gdpr.html) Puede enviar cualquier identificador de Analytics (como se describe en la sección [Prácticas recomendadas de etiquetado](/help/admin/c-data-governance/gdpr-analytics-ids.md)) en las solicitudes, junto con sus respectivos ID de área de nombres (ID de fuentes de datos). |
| **Paso 6**: Consulte y gestione la configuración de la privacidad de datos de su grupo de informes. | Siga las instrucciones de [Ver configuración de control de datos de los grupos de informes.](/help/admin/c-data-governance/gdpr-view-settings.md) |
