---
description: Descubra cómo migrar las reglas de procesamiento de Mobile Services a Adobe Analytics
title: Migración de reglas de procesamiento de Mobile Services a Adobe Analytics
translation-type: tm+mt
source-git-commit: d6601640d06f65dd1ddd09cb9bde0267df20eec3
workflow-type: tm+mt
source-wordcount: '686'
ht-degree: 6%

---


# Migración de reglas de procesamiento de Mobile Services a Adobe Analytics

Este documento le proporciona instrucciones sobre cómo migrar cualquier regla de procesamiento adicional (más allá de las métricas del ciclo vital) que haya creado en la interfaz de usuario de Mobile Services a Adobe Analytics.

Las reglas de procesamiento se utilizan para mover valores desde variables de datos de contexto a props y eVars. Por ejemplo, puede colocar el valor de una variable de datos de contexto &quot;término de búsqueda&quot; en el valor de un eVar de variable de comercio y sobrescribir ese valor en cada visita. Sin reglas de procesamiento, las variables de datos de contexto no tienen sentido y no rellenan ningún informe en Analytics.

Este documento también muestra cómo realizar sistemas de informes de uso móvil en Analysis Workspace.

## Migrar reglas de procesamiento

Si está aprovechando Mobile Services para la funcionalidad gratuita, como reglas de procesamiento y funciones de sistema de informes de uso, puede pasar sin problemas a la interfaz de usuario de Analytics (IU de reglas de procesamiento o Analysis Workspace) para realizar estas funciones. Para las métricas del ciclo vital o las reglas configuradas en la interfaz de usuario de las reglas de procesamiento de AA, no es necesario realizar ninguna migración. Las métricas del ciclo vital son métricas &quot;listas para usar&quot; que se recopilan automáticamente cuando el SDK de Mobile se implementa por primera vez en la aplicación.

Sin embargo, si configura reglas de procesamiento adicionales en la interfaz de usuario de Mobile Services (más allá de las métricas del ciclo vital), debe migrarlas para poder editarlas o eliminarlas en Analytics después de perder el acceso a Mobile Services.

1. Log in to `experience.adobe.com` and go to Mobile Services.
1. Haga clic en el icono de engranaje de una aplicación móvil cuyas asignaciones de variables de contexto desee migrar a Adobe Analytics.
1. Haga clic en el elemento de menú **[!UICONTROL Administrar variables y métricas]** y, a continuación, haga clic en la ficha Variables **** personalizadas. Aquí puede ver qué asignaciones de variables de contexto (datos de contexto) se han agregado a la configuración. Anote estas configuraciones (o tome una captura de pantalla). Ejemplo:

   ![Variable de contexto](assets/context-var.png)

1. En Experience Cloud, cambie a Adobe Analytics y asegúrese de que está en el mismo grupo de informes móviles que estaba viendo en Mobile Services.
1. Vaya a **[!UICONTROL Administración]** > Grupos **[!UICONTROL de informes]** > **[!UICONTROL Editar configuración]** > **[!UICONTROL General]** > Reglas **[!UICONTROL de procesamiento]**.
1. Haga clic en **[!UICONTROL Agregar regla]**.
1. Ignore las condiciones y continúe agregando las mismas variables de contexto que existen en Mobile Services.

   ![Regla de procesamiento](assets/proc-rule.png)

1. Haga clic en **[!UICONTROL Guardar]**.

## Sistema de informes de uso móvil en Analysis Workspace

Además de las métricas y dimensiones móviles (si el grupo de informes está habilitado para Mobile Services), Analysis Workspace contiene varias plantillas de proyecto de Mobile que pueden facilitar la análisis:

* **[!UICONTROL Mensajería]**: Se centra en el rendimiento de la mensajería en la aplicación y push.
* **[!UICONTROL Ubicación]**: Incluye un mapa que muestra los datos de ubicación.
* **[!UICONTROL Métricas]** clave: Mantenga un pulso sobre las métricas clave de la aplicación.
* **[!UICONTROL Uso]** de la aplicación: ¿Cuántos usuarios de la aplicación, inicios y primeros inicios tuvo la aplicación y cuál fue la duración media de la sesión?
* **[!UICONTROL Adquisición]**: ¿Cómo funcionan los vínculos de adquisición móvil?
* **[!UICONTROL Rendimiento]**: ¿Cómo funciona la aplicación y dónde tienen problemas los usuarios?
* **[!UICONTROL Retención]**: ¿Quiénes son mis fieles usuarios y qué hacen?
* **[!UICONTROL Viajes]**: ¿Cuáles son los patrones de uso más destacados de mi aplicación?

Este es un extracto de la plantilla Uso de aplicaciones móviles:

![Uso de aplicaciones móviles](assets/mobile-app-usage.png)

Para acceder a las plantillas:

1. Log in to `experience.adobe.com` and select Analytics.
1. Asegúrese de que se encuentra en un grupo de informes habilitado para Mobile Services.
1. Click the **[!UICONTROL Workspace]** tab.
1. Haga clic en **[!UICONTROL Crear nuevo proyecto]**.
1. Seleccione cualquiera de las plantillas de Mobile y haga clic en **[!UICONTROL Crear]**.

## Migrar otras funciones de Mobile Services

La siguiente funcionalidad de Mobile Services también tiene vínculos con Adobe Analytics, pero requiere un SKU de Adobe Analytics adquirido:

* Vínculos de adquisición
* Mensajería push
* Mensajería en la aplicación
* Administración de puntos de interés de ubicación

Si aprovecha Mobile Services para la funcionalidad de pago, no tiene una ruta de migración viable a otras herramientas internas o externas:

* Para los vínculos de adquisición, podemos dirigirle a los socios de Adobe para satisfacer sus necesidades.
* La mensajería push y la mensajería en la aplicación están disponibles en Adobe Campaign Standard y Adobe Campaign Classic (solo push). Sin embargo, el conjunto de datos subyacente utilizado para la segmentación es diferente. Le sugerimos que trabaje con su equipo de cuenta de Adobe para determinar las opciones de migración para los datos de mensajería.
* En cuanto a la funcionalidad Ubicación, se le recomienda que adopte el nuevo servicio [de ubicación de](https://www.adobe.com/experience-platform/location-service.html)Adobe Experience Platform, que es gratuito para todos los clientes de AEP.
