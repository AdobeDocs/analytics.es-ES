---
description: La interfaz de usuario de Adobe Mobile Services combina datos de las aplicaciones móviles de sus grupos de informes de Adobe Analytics con la posibilidad de enviar notificaciones push y generar mensajes en las aplicaciones.
seo-description: La interfaz de usuario de Adobe Mobile Services combina datos de las aplicaciones móviles de sus grupos de informes de Adobe Analytics con la posibilidad de enviar notificaciones push y generar mensajes en las aplicaciones.
seo-title: Compatibilidad con VRS en Mobile Services
title: Compatibilidad con VRS en Mobile Services
uuid: 1 b 11279 e-d 0 d 8-48 c 5-a 5 b 5-8020 d 5 ed 39 da
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Compatibilidad con VRS en Mobile Services

La interfaz de usuario de Adobe Mobile Services combina datos de las aplicaciones móviles de sus grupos de informes de Adobe Analytics con la posibilidad de enviar notificaciones push y generar mensajes en las aplicaciones.

## VRS support in Mobile Services {#topic_1D0BABFA64EF42DE9C09B7AA37CACEC5}

La interfaz de usuario de Adobe Mobile Services combina datos de las aplicaciones móviles de sus grupos de informes de Adobe Analytics con la posibilidad de enviar notificaciones push y generar mensajes en las aplicaciones.

Adobe Mobile Services admite grupos de informes virtuales. Sin embargo, si desea crear un grupo de informes virtuales con varias aplicaciones y tiene pensando crear una actividad de mensajería, debe especificar el ID de aplicación individual como parámetro. Si va a crear un mensaje push, el ID de aplicación tiene que ser uno de los parámetros del segmentos que use. Si va a crear un mensaje en la aplicación, el ID de aplicación tiene que ser uno de los parámetros de las características que establezca para el mensaje. Si no hace esto, el mensaje se enviará/activará en todos los usuarios y en todas las aplicaciones que cumplan los criterios del segmento o activador.

Si desea más detalles, consulte [Grupos de informes virtuales](https://marketing.adobe.com/resources/help/en_US/mobile/c_mob_vrs.html) en la documentación de Adobe Mobile Services.
