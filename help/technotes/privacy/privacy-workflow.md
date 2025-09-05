---
description: Describe los pasos para permitir que la implementación de Adobe Analytics admita el acceso a la privacidad de datos de los usuarios y los derechos de eliminación de estos.
title: Flujo de trabajo de privacidad
feature: Data Governance
role: Admin
exl-id: c364b364-6d77-4b2c-88ab-65daf812f242
source-git-commit: 325a42c080290509309e90c9127138800d5ac496
workflow-type: tm+mt
source-wordcount: '319'
ht-degree: 100%

---

# Flujo de trabajo de privacidad

En este flujo de trabajo se describen los pasos que debe seguir a fin de preparar su implementación de Adobe Analytics para cumplir los derechos de acceso y eliminación de privacidad de datos de sus interesados.

1. Comience con la página de [Información general de Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=es) en Adobe Experience Platform para obtener una idea de las preguntas que debe hacer antes de etiquetar los datos de Analytics.
1. **Establezca su política de retención de datos.** Se requiere una política de retención de datos para que Adobe pueda atender las solicitudes de acceso o eliminación de datos de la privacidad de datos.  Para obtener más información, consulte las [Preguntas más frecuentes sobre la retención de datos](/help/technotes/data-retention.md). Para utilizar la API de los servicios de privacidad, debe asegurarse de establecer el período de retención de datos en Adobe Analytics.
1. **Aprenda sobre las etiquetas de privacidad de datos, los ID de Adobe Analytics y los espacios de nombres.** Consulte [Etiquetas de privacidad de datos para variables de Analytics](/help/admin/tools/privacy-labeling/labels.md) y [Prácticas recomendadas de etiquetado](/help/admin/tools/privacy-labeling/best-practices.md).
1. **Asigne etiquetas de identidad, confidencialidad y gobernanza de datos a cada variable de un grupo de informes.** El etiquetado debe revisarse cada vez que se crea un nuevo grupo de informes o cuando se habilita una nueva variable dentro de un grupo de informes existente. También es posible que necesite revisar el etiquetado cuando se habiliten nuevas integraciones de la solución, ya que pueden exponer nuevas variables que pueden requerir etiquetado. Una reimplementación de sus aplicaciones móviles o sitios web puede cambiar la forma en la que se utilizan las variables existentes, las cuales también pueden necesitar la actualización de las etiquetas. Consulte [Etiquetado de datos de grupos de informes](/help/admin/tools/privacy-labeling/namespaces.md).
1. **Conéctese a la API de Privacidad de datos de Adobe y envíe solicitudes de acceso y eliminación.** Como cliente de Adobe Analytics, puede enviar solicitudes de privacidad de datos individuales para acceder a datos de clientes y eliminarlos; para ello, debe llamar a la [API de servicio de privacidad de Adobe Experience](https://experienceleague.adobe.com/docs/experience-platform/privacy/api/overview.html?lang=es). Puede enviar cualquier identificador de Analytics (como se describe en la sección [Prácticas recomendadas de etiquetado](/help/admin/tools/privacy-labeling/best-practices.md)) en las solicitudes, junto con sus respectivos ID de área de nombres (ID de fuentes de datos).
1. **Consulte y gestione la configuración de la privacidad de datos de su grupo de informes.** Consulte [Ver la configuración de gobernanza de datos del grupo de informes](/help/admin/tools/privacy-labeling/view-settings.md).
