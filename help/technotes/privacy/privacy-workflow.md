---
description: Describe los pasos para permitir que la implementación de Adobe Analytics admita el acceso a la privacidad de datos de los usuarios y los derechos de eliminación de estos.
title: Flujo de trabajo de privacidad
feature: Data Governance
role: Admin
exl-id: c364b364-6d77-4b2c-88ab-65daf812f242
TQID: 'https://experienceleague.adobe.com/n0zqbcuPD2lvtgYNtdQx5VsBl-FrmzfqU-z2iIn83hg'
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: eb9732ab-8232-4b21-bc4c-89de86dbe4d7id: fd307ce7-56f5-4ee3-af68-a7833ff6e85eid: b8734a57-d5fb-44a8-8ee1-65225cecaeae
subfeature_v2: id: b99602d0-836e-4dbb-979f-c0dec53f883c
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c7d04a2c-412a-4c9d-9d7a-4456eaa5adebid: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 333
ht-degree: 59%

---

# Flujo de trabajo de privacidad

En este flujo de trabajo se describen los pasos que debe seguir a fin de preparar su implementación de Adobe Analytics para cumplir los derechos de acceso y eliminación de privacidad de datos de sus interesados.

1. Comience con la página de [Información general de Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=es) en Adobe Experience Platform para obtener una idea de las preguntas que debe hacer antes de etiquetar los datos de Analytics.
1. **Establezca su política de retención de datos.** Se requiere una política de retención de datos para que Adobe pueda tratar las solicitudes de acceso o eliminación de datos de la privacidad de datos.  Para obtener más información, consulte las [Preguntas más frecuentes sobre la retención de datos](/help/technotes/data-retention.md). Para utilizar la API de los servicios de privacidad, debe asegurarse de establecer el período de retención de datos en Adobe Analytics.
1. **Familiarícese con las etiquetas de privacidad de datos, los Adobe Analytics ID y los áreas de nombres.** Consulte [Etiquetas de privacidad de datos para variables de Analytics](/help/admin/tools/privacy-labeling/labels.md) y [Prácticas recomendadas de etiquetado](/help/admin/tools/privacy-labeling/best-practices.md).
1. **Asigne etiquetas de identidad, confidencialidad y control de datos a cada variable de un grupo de informes.** El etiquetado debe revisarse cada vez que se crea un nuevo grupo de informes o cuando se activa una nueva variable dentro de un grupo de informes existente. También es posible que necesite revisar el etiquetado cuando se habiliten nuevas integraciones de la solución, ya que pueden exponer nuevas variables que pueden requerir etiquetado. Una reimplementación de sus aplicaciones móviles o sitios web puede cambiar la forma en la que se utilizan las variables existentes, las cuales también pueden necesitar la actualización de las etiquetas. Consulte [Etiquetado de datos de grupos de informes](/help/admin/tools/privacy-labeling/namespaces.md).
1. **Conéctese a la API de privacidad de datos de Adobe y envíe solicitudes de acceso y eliminación.** Como cliente de Adobe Analytics, puede enviar solicitudes de privacidad de datos individuales para acceder a datos de clientes y eliminarlos; para ello, debe llamar a la [API de Adobe Experience Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/api/overview.html?lang=es). Puede enviar cualquier identificador de Analytics (como se describe en la sección [Prácticas recomendadas de etiquetado](/help/admin/tools/privacy-labeling/best-practices.md)) en las solicitudes, junto con sus respectivos ID de espacio de nombres (ID de fuentes de datos).
1. **Consulta y administra la configuración de la privacidad de datos de tu grupo de informes.** Consulte [Ver la configuración de control de datos del grupo de informes](/help/admin/tools/privacy-labeling/view-settings.md).
