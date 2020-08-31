---
description: Descubra cómo migrar las reglas de procesamiento de Mobile Services a Adobe Analytics
title: Migración de reglas de procesamiento de Mobile Services a Adobe Analytics
translation-type: tm+mt
source-git-commit: 67c8880e125ca31aa96ecea56a7ef0b85bc3abba
workflow-type: tm+mt
source-wordcount: '667'
ht-degree: 18%

---


# Migración de reglas de procesamiento de Mobile Services a Adobe Analytics

Con la próxima (aún no anunciada) puesta en marcha de la funcionalidad de Adobe Mobile Services, este documento le proporciona instrucciones sobre cómo migrar cualquier regla de procesamiento adicional (más allá de las métricas del ciclo vital) que haya creado en la interfaz de usuario de Mobile Services a Adobe Analytics.

Las reglas de procesamiento se utilizan para mover valores desde variables de datos de contexto a props y eVars. Por ejemplo, puede colocar el valor de una variable de datos de contexto &quot;término de búsqueda&quot; en el valor de un eVar de variable de comercio y sobrescribir ese valor en cada visita. Sin reglas de procesamiento, las variables de datos de contexto no tienen sentido y no rellenan ningún informe en Analytics.

## Migrar reglas de procesamiento

Si está aprovechando Mobile Services para la funcionalidad gratuita, como reglas de procesamiento y funciones de sistema de informes de uso, puede pasar sin problemas a la interfaz de usuario de Analytics (IU de reglas de procesamiento o Analysis Workspace) para realizar estas funciones. Para las métricas del ciclo vital o las reglas configuradas en la interfaz de usuario de las reglas de procesamiento de AA, no es necesario realizar ninguna migración. Las métricas del ciclo vital son métricas &quot;listas para usar&quot; que se recopilan automáticamente cuando el SDK de Mobile se implementa por primera vez en la aplicación.

Sin embargo, si configura reglas de procesamiento adicionales en la interfaz de usuario de Mobile Services (más allá de las métricas del ciclo vital), debe migrarlas para poder editarlas o eliminarlas en Analytics después de perder el acceso a Mobile Services.

1. Inicie sesión en experience.adobe.com y vaya a Mobile Services.
1. Haga clic en el icono de engranaje de una aplicación móvil cuyas asignaciones de variables de contexto desee migrar a Adobe Analytics.
1. Haga clic en el elemento de menú **[!UICONTROL Administrar variables y métricas]** y, a continuación, haga clic en la ficha Variables **** personalizadas. Aquí puede ver qué asignaciones de variables de contexto (datos de contexto) se han agregado a la configuración. Anote estas configuraciones (o tome una captura de pantalla). Ejemplo:

   ![Variable de contexto](assets/context-var.png)

1. En Experience Cloud, cambie a Adobe Analytics y asegúrese de que está en el mismo grupo de informes móviles que estaba viendo en Mobile Services.
1. Vaya a Administración > Grupos de informes > Editar configuración > General > Reglas de procesamiento.
1. Haga clic en Agregar regla.
1. Ignore las condiciones y continúe agregando las mismas variables de contexto que existen en Mobile Services.

   ![Regla de procesamiento](assets/proc-rule.png)

## Sistema de informes de uso móvil en Analysis Workspace

Además de las métricas y dimensiones móviles (si el grupo de informes está habilitado para Mobile Services), Analysis Workspace contiene varias plantillas de proyecto de Mobile que pueden facilitar la análisis:

* Mensajería: Se centra en el rendimiento de la mensajería en la aplicación y mensajería push.
* Ubicación: Incluye un mapa que muestra los datos de ubicación.
* Métricas clave: Observar las métricas clave de su aplicación.
* Uso de la aplicación: ¿Cuántos usuarios de la aplicación, ejecuciones y ejecuciones por primera vez ha tenido la aplicación y cuál es la longitud promedio de cada sesión?
* Adquisición: ¿Cómo funcionan los vínculos de adquisición móvil?
* Rendimiento: ¿Qué rendimiento tiene la aplicación y dónde tienen problemas los usuarios?
* Retención: ¿Quiénes son mis usuarios más fieles y qué hacen?
* Recorridos: ¿Cuáles son los patrones de uso más destacados de mi aplicación?

Para acceder a las plantillas:

1. Inicie sesión en experience.adobe.com y seleccione Analytics.
1. Asegúrese de que se encuentra en un grupo de informes habilitado para Mobile Services.
1. Haga clic en la ficha Espacio de trabajo.
1. Haga clic en Crear nuevo proyecto.
1. Seleccione cualquiera de las plantillas de Mobile y haga clic en Crear.

## Migrar otras funciones de Mobile Services

La siguiente funcionalidad de Mobile Services también tiene vínculos con Adobe Analytics, pero requiere un SKU de Adobe Analytics adquirido:

* Vínculos de adquisición
* Mensajería push
* Mensajería en la aplicación
* Administración de puntos de interés de ubicación

Si aprovecha Mobile Services para la funcionalidad de pago, no tiene una ruta de migración viable a otras herramientas internas o externas:

* Para los vínculos de adquisición, podemos dirigirle a los socios de Adobe para satisfacer sus necesidades.
* Aunque los sabores de la mensajería push y la mensajería en la aplicación se encuentran en Adobe Campaign Standard y Adobe Campaign Classic (solo push), el conjunto de datos subyacente que se utiliza para la segmentación es diferente y no es posible migrar datos ni mensajes en actividad.
* En cuanto a la funcionalidad Ubicación, se le recomienda que adopte el nuevo servicio [de ubicación de](https://www.adobe.com/experience-platform/location-service.html)Adobe Experience Platform, que es gratuito para todos los clientes de AEP.
