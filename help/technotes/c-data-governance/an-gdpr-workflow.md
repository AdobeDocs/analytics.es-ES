---
description: Describe los pasos para permitir que la implementación de Adobe Analytics admita el acceso a la privacidad de datos de los usuarios y los derechos de eliminación de estos.
title: Flujo de trabajo de privacidad
feature: Privacy
exl-id: c364b364-6d77-4b2c-88ab-65daf812f242
source-git-commit: 1ca7040156f7f2105a9625f921de3d90b4175056
workflow-type: tm+mt
source-wordcount: '357'
ht-degree: 83%

---

# Flujo de trabajo de privacidad

En este flujo de trabajo se describen los pasos que debe seguir a fin de preparar su implementación de Adobe Analytics para cumplir los derechos de acceso y eliminación de privacidad de datos de sus interesados.

1. Comience con el [Información general del Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=es) en Adobe Experience Platform para obtener una idea de las preguntas que debe hacer antes de etiquetar los datos de Analytics.
1. **Establezca su política de retención de datos.** Se requiere una política de retención de datos para que Adobe pueda atender las solicitudes de acceso o eliminación de datos de la privacidad de datos.  Para obtener más información, consulte las [Preguntas más frecuentes sobre la retención de datos](/help/technotes/data-retention.md). Para utilizar la API de Privacy Service, debe asegurarse de que el periodo de retención de datos se establece en Adobe Analytics.
1. **Familiarícese con las etiquetas de privacidad de datos, los ID de Adobe Analytics, los áreas de nombres y la expansión de ID.** Consulte [Etiquetas de privacidad de datos para variables de Analytics](/help/technotes/c-data-governance/data-labeling/gdpr-labels.md) y [Prácticas recomendadas de etiquetado](/help/technotes/c-data-governance/data-labeling/gdpr-analytics-ids.md).
1. **Familiarícese con las etiquetas DULE/Privacidad de datos, los ID de Adobe Analytics, los áreas de nombres y la expansión de ID.** Consulte [Etiquetas de privacidad de datos para variables de Analytics](/help/technotes/c-data-governance/data-labeling/gdpr-labels.md) y [Prácticas recomendadas de etiquetado](/help/technotes/c-data-governance/data-labeling/gdpr-analytics-ids.md).
1. **Asigne etiquetas de identidad, confidencialidad y control de datos a cada variable de un grupo de informes.** El etiquetado debe revisarse cada vez que se crea un nuevo grupo de informes o cuando se activa una nueva variable dentro de un grupo de informes existente. También es posible que necesite revisar el etiquetado cuando se activen nuevas integraciones de la solución, ya que pueden exponer nuevas variables que pueden requerir etiquetado. Una reimplementación de sus aplicaciones móviles o sitios web puede cambiar la forma en la que se utilizan las variables existentes, las cuales también pueden necesitar la actualización de las etiquetas. Consulte [Etiquetado de datos de grupos de informes](/help/technotes/c-data-governance/data-labeling/gdpr-namespaces.md).
1. **Conéctese a la API de Privacidad de datos de Adobe y envíe solicitudes de acceso y eliminación.** Como cliente de Adobe Analytics, puede enviar solicitudes de privacidad de datos individuales para acceder a datos de clientes y eliminarlos; para ello, debe llamar a la [API de servicio de privacidad de Adobe Experience](https://experienceleague.adobe.com/docs/experience-platform/privacy/api/overview.html?lang=es). Puede enviar cualquier identificador de Analytics (como se describe en la sección [Prácticas recomendadas de etiquetado](/help/technotes/c-data-governance/data-labeling/gdpr-analytics-ids.md)) en las solicitudes, junto con sus respectivos ID de área de nombres (ID de fuentes de datos).
1. **Consulte y gestione la configuración de la privacidad de datos de su grupo de informes.** Consulte [Ver la configuración de control de datos del grupo de informes](/help/technotes/c-data-governance/data-labeling/gdpr-view-settings.md).
