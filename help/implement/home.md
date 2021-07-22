---
title: Implementación de Adobe Analytics
description: Implemente Adobe Analytics en su sitio, propiedad o aplicación.
exl-id: 2b629369-2d69-4dc6-861a-ff21a46d39e0
source-git-commit: 5368e808a862a3e320f5d079433db96ab79b45c8
workflow-type: tm+mt
source-wordcount: '361'
ht-degree: 83%

---

# Implementación de Adobe Analytics

![Banner](../../assets/doc_banner_implement.png)

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

* **Etiquetas Adobe Experience Platform**: Método estandarizado y recomendado para implementar Adobe Analytics. Coloque una etiqueta de cargador en cada página y utilice la interfaz de usuario de recopilación de datos para determinar cómo se define cada variable.
* **JavaScript heredado:** Método manual histórico para implementar Adobe Analytics. Describe las variables y la configuración utilizadas en una implementación, que pueden resultar útiles para las implementaciones de etiquetas que usan reglas con código personalizado.
* **SDK móvil**: Bibliotecas dedicadas para enviar fácilmente datos a Adobe desde aplicaciones móviles.

## Artículos de implementación de Analytics clave

* [Ocuparse de una implementación de Adobe Analytics existente](/help/implement/prepare/existing-implementation.md)
* [Adobe Debugger](validate/debugger.md)
* [Crear una propiedad de etiqueta en el Experience Platform](launch/create-analytics-property.md)
* [Actualizaciones de AppMeasurement](appmeasurement-updates.md)

## Más guías del usuario de Analytics

[Guías del usuario de Analytics](/help/landing/home.md)

## Recursos clave de Analytics

* [Contactar con el servicio de atención al cliente](https://helpx.adobe.com/es/contact/enterprise-support.ec.html)
* [Foro de Analytics](https://forums.adobe.com/community/experience-cloud/analytics-cloud/analytics)
* [Recursos de Adobe Analytics](https://forums.adobe.com/message/10660755)
* [Experience League](https://landing.adobe.com/experience-league/)
