---
description: Describe los pasos para permitir que la implementación de Adobe Analytics admita el acceso a la privacidad de datos de los usuarios y los derechos de eliminación de estos.
title: Flujo de trabajo de privacidad
uuid: f24e8be3-8b5c-409b-ad6b-770198ae2549
exl-id: c364b364-6d77-4b2c-88ab-65daf812f242
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '399'
ht-degree: 100%

---

# Flujo de trabajo de privacidad

En este flujo de trabajo se describen los pasos que debe seguir a fin de preparar su implementación de Adobe Analytics para cumplir los derechos de acceso y eliminación de privacidad de datos de sus interesados.

| Descripción de tarea | Vínculos a instrucciones y más información |
|--- |--- |
| **Paso 1**: Compruebe que todos sus grupos de informes que puedan contener datos relevantes en el marco de la privacidad de datos estén asignados a su organización de Experience Cloud (o IMS).  Las solicitudes de privacidad de datos se presentan mediante una organización de Experience Cloud y se aplicarán a todos los grupos de informes pertenecientes a dicha organización. Las solicitudes no se aplican a los grupos de informes que no estén asignados a la organización, aunque formen parte de su empresa de inicio de sesión. | Consulte [Asignación de grupos de informes a una organización](https://docs.adobe.com/content/help/es-ES/core-services/interface/about-core-services/report-suite-mapping.html). |
| **Paso 2**: Establezca su política de retención de datos. | Debe haberse configurado una política de retención de datos para que Adobe pueda tratar las solicitudes de acceso o eliminación de datos en la privacidad de datos.  Para obtener más información, consulte estas [Preguntas frecuentes de retención de datos de Analytics](/help/technotes/data-retention.md). |
| **Paso 3**: Familiarícese con las etiquetas DULE/Privacidad de datos, los ID de Adobe Analytics, los áreas de nombres y la expansión de ID. | Lea estos temas en este conjunto de documentación:<ul><li>[Etiquetas de privacidad de datos para variables de Analytics](/help/admin/c-data-governance/gdpr-labels.md)</li><li>[Prácticas recomendadas de etiquetado](/help/admin/c-data-governance/gdpr-analytics-ids.md)</li></ul> |
| **Paso 4**: Asigne etiquetas de identidad, confidencialidad y control de datos a cada variable de un grupo de informes.  Nota: Recuerde que el etiquetado debe revisarse cada vez que se crea un nuevo grupo de informes o cuando se activa una nueva variable dentro de un grupo de informes existente. También es posible que necesite revisar el etiquetado cuando se activen nuevas integraciones de la solución, ya que pueden exponer nuevas variables que pueden requerir etiquetado. Una reimplementación de sus aplicaciones móviles o sitios web puede cambiar la forma en la que se utilizan las variables existentes, las cuales también pueden necesitar la actualización de las etiquetas. | Sigue las instrucciones de [Etiquetado de datos de grupos de informes](/help/admin/c-data-governance/gdpr-setup-reportsuite.md). |
| **Paso 5**: Conéctese a la API de Privacidad de datos de Adobe y envíe solicitudes de acceso y eliminación. | Como cliente de Adobe Analytics, puede enviar solicitudes de privacidad de datos individuales para acceder a datos de clientes y eliminarlos; para ello, debe llamar a la [API de privacidad de datos de Adobe Experience Cloud](https://www.adobe.io/apis/experienceplatform/gdpr.html). Puede enviar cualquier identificador de Analytics (como se describe en la sección [Prácticas recomendadas de etiquetado](/help/admin/c-data-governance/gdpr-analytics-ids.md)) en las solicitudes, junto con sus respectivos ID de área de nombres (ID de fuentes de datos). |
| **Paso 6**: Consulte y gestione la configuración de la privacidad de datos de su grupo de informes. | Siga las instrucciones de [Ver configuración de control de datos de los grupos de informes](/help/admin/c-data-governance/gdpr-view-settings.md). |
