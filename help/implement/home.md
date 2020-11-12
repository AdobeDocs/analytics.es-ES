---
title: Implementación de Adobe Analytics
description: Implemente Adobe Analytics en su sitio, propiedad o aplicación.
translation-type: tm+mt
source-git-commit: 34ccd89d0ac4223af87b36a48e778fb678d5cd59
workflow-type: tm+mt
source-wordcount: '390'
ht-degree: 97%

---


# Implementación de Adobe Analytics

![Banner](../../assets/doc_banner_implement.png)

Adobe requiere código en su sitio o aplicación para enviar datos a los servidores de recopilación de datos de Adobe. Los pasos siguientes indican cómo funciona una implementación típica.

1. Cuando un visitante llega a su sitio, se realiza una solicitud al servidor web.
2. El servidor web del sitio envía la información de código de página, y se muestra la página en el explorador.
3. Se carga la página, y se ejecuta el código JavaScript de Analytics.
El código JavaScript envía una solicitud de imagen a los servidores de recopilación de datos de Adobe. Los datos de página definidos en la implementación se envían como parte de una cadena de consulta en esta solicitud de imagen.

4. Adobe devuelve una imagen en píxeles transparente.
5. Los servidores de Adobe almacenan los datos recopilados en un *grupo de informes*.
6. Los datos de grupos de informes rellenan los informes a los que se puede tener acceso en un explorador web.

   La ejecución de código JavaScript ocurre rápidamente y no afecta visiblemente a los tiempos de carga de una página. Este método permite contabilizar páginas que se mostraron cuando un visitante hizo clic en **[!UICONTROL Recarga]** o **[!UICONTROL Atrás]** para alcanzar una página, porque el JavaScript se ejecuta incluso cuando se recupera la página de la memoria caché.

Adobe Analytics requiere código en el sitio web, la aplicación móvil u otra aplicación para enviar datos a los servidores de recopilación de datos. Hay varios métodos para implementar este código, según la plataforma y las necesidades de la organización.

* **Adobe Experience Platform Launch:** Método estandarizado y recomendado para implementar Adobe Analytics. Coloque una etiqueta de carga en cada página y utilice la interfaz de Launch para determinar cómo se define cada variable.
* **Dynamic Tag Management:** El predecesor a Launch. DTM utiliza una interfaz similar para implementar Analytics, pero ya no se actualiza y no es tan flexible. Adobe recomienda utilizar Launch para implementar Adobe Analytics.
* **JavaScript heredado:** Método manual histórico para implementar Adobe Analytics. Esquema de las variables y configuraciones utilizadas en una implementación, que pueden ser útiles para implementaciones de Launch utilizando reglas con código personalizado.
* **SDK móvil**: Bibliotecas dedicadas para enviar fácilmente datos a Adobe desde aplicaciones móviles.

## Artículos de implementación de Analytics clave

* [Se encarga de una implementación de Adobe Analytics existente](/help/implement/prepare/existing-implementation.md)
* [Adobe Debugger](validate/debugger.md)
* [Creación de una propiedad en Experience Platform Launch](launch/create-analytics-property.md)
* [Actualizaciones de AppMeasurement](appmeasurement-updates.md)

## Más guías del usuario de Analytics

[Guías del usuario de Analytics](/help/landing/home.md)

## Recursos clave de Analytics

* [Contactar con el servicio de atención al cliente](https://helpx.adobe.com/es/contact/enterprise-support.ec.html)
* [Foro de Analytics](https://forums.adobe.com/community/experience-cloud/analytics-cloud/analytics)
* [Recursos de Adobe Analytics](https://forums.adobe.com/message/10660755)
* [Experience League](https://landing.adobe.com/experience-league/)
