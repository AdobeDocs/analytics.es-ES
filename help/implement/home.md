---
title: Implementación de Adobe Analytics
description: Implemente Adobe Analytics en su sitio, propiedad o aplicación.
feature: Implementation Basics
exl-id: 2b629369-2d69-4dc6-861a-ff21a46d39e0
source-git-commit: d2c291f7db465034ffadc4a2c1caf9639caf2a1d
workflow-type: tm+mt
source-wordcount: '409'
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
4. El código JavaScript envía una solicitud de imagen de 1x1 píxeles a los servidores de recopilación de datos de Adobe. Los datos de página definidos en la implementación se envían como parte de una cadena de consulta en esta solicitud de imagen.
5. Los servidores de recopilación de datos de Adobe devuelven la imagen solicitada.
6. Los servidores de Adobe analizan y almacenan los datos recopilados en un grupo de informes.
7. Los datos de grupos de informes rellenan los informes a los que se puede tener acceso en un explorador web.


Adobe ofrece varios métodos para implementar este código, según la plataforma y las necesidades de la organización.

* **Extensión de SDK web**: Método actual, estandarizado y recomendado para implementar Adobe Analytics. Instale la extensión del SDK web en la recopilación de datos de Adobe Experience Platform, utilice una etiqueta de carga en cada página y envíe datos a Adobe Experience Platform Edge en un formato conveniente para su organización. Experience Edge reenvía datos entrantes a Adobe Analytics en el formato correcto.
* **SDK web**: Puede cargar manualmente las bibliotecas del SDK web en su sitio si no desea utilizar etiquetas. Haga referencia a la biblioteca del SDK web en cada página y envíe las llamadas de seguimiento deseadas a Adobe Experience Edge.
* **Extensión de Adobe Analytics**: instale la extensión de Adobe Analytics en la recopilación de datos de Adobe Experience Platform. Coloque una etiqueta de carga en cada página y utilice la extensión de Analytics para determinar cómo se define cada variable.
* **JavaScript heredado:** método manual histórico para implementar Adobe Analytics. Esquema de las variables y configuraciones utilizadas en una implementación, que puede ser útil para implementaciones que utilizan reglas con código personalizado.
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
* [Experience League](https://experienceleague.adobe.com/?lang=es#dashboard/learning)
