---
description: La interfaz de usuario de Adobe Mobile Services combina datos de las aplicaciones móviles de sus grupos de informes de Adobe Analytics con la posibilidad de enviar notificaciones push y generar mensajes en las aplicaciones.
title: Compatibilidad con VRS en Mobile Services
feature: VRS
exl-id: 3082333a-514d-45c6-9432-da32bd27a2eb
source-git-commit: 7a47d837eeae65f2e98123aca78029bfeb7ffe9d
workflow-type: tm+mt
source-wordcount: '219'
ht-degree: 100%

---

# Compatibilidad con VRS en Mobile Services

La interfaz de usuario de Adobe Mobile Services combina datos de las aplicaciones móviles de sus grupos de informes de Adobe Analytics con la posibilidad de enviar notificaciones push y generar mensajes en las aplicaciones.

## Compatibilidad con VRS en Mobile Services {#topic_1D0BABFA64EF42DE9C09B7AA37CACEC5}

La interfaz de usuario de Adobe Mobile Services combina datos de las aplicaciones móviles de sus grupos de informes de Adobe Analytics con la posibilidad de enviar notificaciones push y generar mensajes en las aplicaciones.

Adobe Mobile Services admite grupos de informes virtuales. Sin embargo, si desea crear un grupo de informes virtuales con varias aplicaciones y tiene pensando crear una actividad de mensajería, debe especificar el ID de aplicación individual como parámetro. Si va a crear un mensaje push, el ID de aplicación tiene que ser uno de los parámetros del segmentos que use. Si va a crear un mensaje en la aplicación, el ID de aplicación tiene que ser uno de los parámetros de las características que establezca para el mensaje. Si no hace esto, el mensaje se enviará/activará en todos los usuarios y en todas las aplicaciones que cumplan los criterios del segmento o activador.

Si desea más detalles, consulte [Grupos de informes virtuales](https://experienceleague.adobe.com/docs/mobile-services/using/manage-apps-ug/c-mob-vrs.html?lang=es) en la documentación de Adobe Mobile Services.
