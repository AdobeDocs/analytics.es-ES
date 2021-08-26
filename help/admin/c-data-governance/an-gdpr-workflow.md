---
description: Describe los pasos para permitir que la implementación de Adobe Analytics admita el acceso a la privacidad de datos de los usuarios y los derechos de eliminación de estos.
title: Flujo de trabajo de privacidad
uuid: f24e8be3-8b5c-409b-ad6b-770198ae2549
exl-id: c364b364-6d77-4b2c-88ab-65daf812f242
source-git-commit: 7cb2489c2deaf8e75c71589895314067a010caf8
workflow-type: tm+mt
source-wordcount: '279'
ht-degree: 58%

---

# Flujo de trabajo de privacidad

En este flujo de trabajo se describen los pasos que debe seguir a fin de preparar su implementación de Adobe Analytics para cumplir los derechos de acceso y eliminación de privacidad de datos de sus interesados.

1. **Establezca su política de retención de datos.** Se requiere una política de retención de datos para que el Adobe pueda atender las solicitudes de acceso o eliminación de datos de la privacidad de datos.  Para obtener más información, consulte las [Preguntas frecuentes sobre la retención de datos](/help/technotes/data-retention.md).
1. **Familiarícese con las etiquetas DULE/Privacidad de datos, los ID de Adobe Analytics, los áreas de nombres y la expansión de ID.** Consulte Etiquetas  [de privacidad de datos para ](/help/admin/c-data-governance/gdpr-labels.md) variables de Analytics y Prácticas recomendadas  [de etiquetado](/help/admin/c-data-governance/gdpr-analytics-ids.md).
1. **Asigne etiquetas de identidad, confidencialidad y control de datos a cada variable de un grupo de informes.** El etiquetado debe revisarse cada vez que se crea un nuevo grupo de informes o cuando se activa una nueva variable dentro de un grupo de informes existente. Revise también el etiquetado cuando se activen nuevas integraciones de soluciones, ya que pueden exponer nuevas variables que pueden requerir etiquetado. Una nueva implementación de sus aplicaciones móviles o sitios web puede cambiar la forma en que se utilizan las variables existentes, lo que también puede requerir actualizaciones de las etiquetas. Consulte [Etiquetado de datos de grupos de informes](/help/admin/c-data-governance/gdpr-setup-reportsuite.md).
1. **Conéctese a la API de Privacidad de datos de Adobe y envíe solicitudes de acceso y eliminación.** Como cliente de Adobe Analytics, puede enviar solicitudes de privacidad de datos individuales para acceder a datos de clientes y eliminarlos; para ello, debe llamar a la [API de privacidad de datos de Adobe Experience Cloud](https://www.adobe.io/apis/experienceplatform/gdpr.html). Puede enviar cualquier identificador de Analytics (como se describe en la sección [Prácticas recomendadas de etiquetado](/help/admin/c-data-governance/gdpr-analytics-ids.md)) en las solicitudes, junto con sus respectivos ID de área de nombres (ID de fuentes de datos).
1. **Consulte y gestione la configuración de la privacidad de datos de su grupo de informes.** Consulte  [Ver la configuración de control de datos del grupo de informes](/help/admin/c-data-governance/gdpr-view-settings.md).
