---
title: Implementación de Adobe Analytics
description: Implemente Adobe Analytics en su sitio, propiedad o aplicación.
feature: Implementation Basics
exl-id: 2b629369-2d69-4dc6-861a-ff21a46d39e0
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '430'
ht-degree: 79%

---

# Implementación de Adobe Analytics

![Banner](../../assets/doc_banner_implement.png)

A continuación, se muestra un vídeo introductorio de Adobe Analytics:

>[!VIDEO](https://video.tv.adobe.com/v/27429/?quality=12)

Adobe requiere código en su sitio o aplicación para enviar datos a los servidores de recopilación de datos de Adobe. Los pasos siguientes indican cómo funciona una implementación típica.

1. Cuando un visitante llega a su sitio, se realiza una solicitud al servidor web.
2. El servidor web del sitio envía la información de código de página, y se muestra la página en el explorador.
3. Se carga la página, y se ejecuta el código JavaScript de Analytics.
El código JavaScript envía una solicitud de imagen a los servidores de recopilación de datos de Adobe. Los datos de página definidos en la implementación se envían como parte de una cadena de consulta en esta solicitud de imagen.

4. Adobe devuelve una imagen en píxeles transparente.
5. Los servidores de Adobe almacenan los datos recopilados en uno o más *grupos de informes*.
6. Los datos de grupos de informes rellenan los informes a los que se puede tener acceso en un explorador web.

   La ejecución de código JavaScript ocurre rápidamente y no afecta visiblemente a los tiempos de carga de una página. Este método permite contabilizar páginas que se mostraron cuando un visitante hizo clic en **[!UICONTROL Recarga]** o **[!UICONTROL Atrás]** para alcanzar una página, porque el JavaScript se ejecuta incluso cuando se recupera la página de la memoria caché.

Adobe Analytics requiere código en el sitio web, la aplicación móvil u otra aplicación para enviar datos a los servidores de recopilación de datos. Hay varios métodos para implementar este código, según la plataforma y las necesidades de la organización.

* **SDK web**: Método estandarizado y recomendado para implementar Adobe Analytics. Instale la extensión del SDK web en la recopilación de datos de Adobe Experience Platform, utilice una etiqueta loader en cada página y envíe datos a Adobe Experience Platform Edge en un formato conveniente para su organización. Experience Edge reenvía datos entrantes a Adobe Analytics en el formato correcto.
* **Extensión de Adobe Analytics**: Instale la extensión de Adobe Analytics en la recopilación de datos de Adobe Experience Platform. Coloque una etiqueta de cargador en cada página y utilice la extensión de Analytics para determinar cómo se define cada variable.
* **JavaScript heredado:** Método manual histórico para implementar Adobe Analytics. Esquema de las variables y configuraciones utilizadas en una implementación, que pueden ser útiles para implementaciones de etiquetas utilizando reglas con código personalizado.
* **SDK móvil**: Bibliotecas dedicadas para enviar fácilmente datos a Adobe desde aplicaciones móviles.

## Artículos de implementación de Analytics clave

* [Ocuparse de una implementación de Adobe Analytics existente](/help/implement/prepare/existing-implementation.md)
* [Adobe Debugger](validate/debugger.md)
* [Creación de una propiedad de etiquetas en Experience Platform](launch/create-analytics-property.md)
* [Actualizaciones de AppMeasurement](appmeasurement-updates.md)

## Más guías del usuario de Analytics

[Guías del usuario de Analytics](https://experienceleague.adobe.com/docs/analytics.html?lang=es)

## Recursos clave de Analytics

* [Contactar con el servicio de atención al cliente](https://experienceleague.adobe.com/?support-solution=Analytics&amp;lang=es#support)
* [Foro de Analytics](https://forums.adobe.com/community/experience-cloud/analytics-cloud/analytics)
* [Recursos de Adobe Analytics](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-discussions/adobe-analytics-resources/m-p/276666?profile.language=es)
* [Experience League](https://experienceleague.adobe.com/?lang=es#home)
