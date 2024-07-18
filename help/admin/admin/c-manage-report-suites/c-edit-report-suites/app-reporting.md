---
description: Habilite dimensiones y métricas para usarlas en el seguimiento de aplicaciones móviles.
title: Creación de informes de aplicaciones
feature: Admin Tools
exl-id: ec19695a-2961-45e4-bf44-434f0ff9e3c9
source-git-commit: e32821dd3f30404166554b8437c508172e4764e5
workflow-type: tm+mt
source-wordcount: '537'
ht-degree: 13%

---

# Creación de informes de aplicaciones

La interfaz de informes de aplicaciones permite habilitar dimensiones y métricas del ciclo vital dedicadas para su uso en el seguimiento de aplicaciones móviles.

**[!UICONTROL Analytics]** > **[!UICONTROL Administrador]** > **[!UICONTROL Grupos de informes]** > **[!UICONTROL Editar configuración]** > **[!UICONTROL Administración de aplicaciones]** > **[!UICONTROL Informes de aplicaciones]**

>[!IMPORTANT]
>
>Una vez que cualquiera de estas funciones está habilitada, no se pueden deshabilitar. Al habilitar una función determinada, sus dimensiones y métricas respectivas quedan disponibles de forma permanente en Analysis Workspace.

## [!UICONTROL Informes de aplicaciones]

Las dimensiones y métricas de [!UICONTROL Informes de aplicaciones] se usan para los siguientes propósitos:

* **Adquisición**: haga un seguimiento de las direcciones URL de referencia para las campañas de descarga de aplicaciones.
* **Ciclo de vida**: nivel base de los informes proporcionados por las mediciones enviadas con cada inicio de aplicación.
* **Acciones de aplicación**: Informes y rutas basadas en acciones internas de la aplicación.
* **Valor a largo plazo**: comprenda cómo acumulan valor los usuarios a lo largo del tiempo mediante los KPI de la aplicación (por ejemplo, compras, vistas de anuncios, vídeos completos, usos compartidos en medios sociales y cargas de fotografías).
* **Eventos cronometrados**: mida el tiempo que transcurre (en la aplicación y en tiempo total) entre las acciones clave de la aplicación (como el tiempo transcurrido hasta la primera compra).

Cuando habilita [!UICONTROL Informes de aplicaciones], están disponibles las siguientes dimensiones:

* [!UICONTROL Nombre de acción] (con [dimensiones de entrada](/help/components/dimensions/entry-dimensions.md) y [salida](/help/components/dimensions/exit-dimensions.md))
* [!UICONTROL Id. de aplicación]
* [!UICONTROL Contenido de adquisición]
* [!UICONTROL Medium de adquisición]
* [!UICONTROL Nombre de adquisición]
* [!UICONTROL Source de adquisición]
* [!UICONTROL Término de adquisición]
* [!UICONTROL Día de la semana (SDK)]
* [!UICONTROL Días transcurridos desde el primer uso]
* [!UICONTROL Días transcurridos desde el último uso]
* [!UICONTROL Nombre de dispositivo (SDK)]
* [!UICONTROL Hora del día (SDK)]
* [!UICONTROL Fecha de primer inicio]
* [!UICONTROL Número de inicios]
* [!UICONTROL Valor de duración (evar)]
* [!UICONTROL Versión del sistema operativo (SDK)]
* [!UICONTROL Resolución (SDK)]

Están disponibles las siguientes métricas:

* [!UICONTROL Tiempo de la acción dentro de la aplicación]
* [!UICONTROL Tiempo total de la acción]
* [!UICONTROL Bloqueos]
* [!UICONTROL Primeros lanzamientos]
* [!UICONTROL Inicios]
* [!UICONTROL Valor de duración (evento)]
* [!UICONTROL Duración total de la sesión]
* [!UICONTROL Actualizaciones]

## [!UICONTROL Seguimiento de ubicación]

Las dimensiones [!UICONTROL Seguimiento de ubicación] se usan para los siguientes propósitos:

* Seguimiento de datos de latitud y longitud
* Identificar, crear y visualizar puntos de interés específicos. Los puntos de interés deben definirse en el archivo de configuración del SDK móvil.
* Realizar un seguimiento de señalizaciones Bluetooth (UUID, principal, secundaria y proximidad).

Cuando habilita [!UICONTROL Seguimiento de ubicación], están disponibles las siguientes dimensiones:

* [!UICONTROL Beacon mayor] (con dimensiones [Entrada](/help/components/dimensions/entry-dimensions.md) y [Salida](/help/components/dimensions/exit-dimensions.md))
* [!UICONTROL Beacon menor] (con dimensiones [Entrada](/help/components/dimensions/entry-dimensions.md) y [Salida](/help/components/dimensions/exit-dimensions.md))
* [!UICONTROL Proximidad del Beacon] (con dimensiones [Entrada](/help/components/dimensions/entry-dimensions.md) y [Salida](/help/components/dimensions/exit-dimensions.md))
* [!UICONTROL UUID de señalización] (con dimensiones [Entrada](/help/components/dimensions/entry-dimensions.md) y [Salida](/help/components/dimensions/exit-dimensions.md))
* [!UICONTROL Ubicación (menos de 10 km)]
* [!UICONTROL Ubicación (menos de 100 m)]
* [!UICONTROL Ubicación (menos de 1 m)]
* [!UICONTROL Nombre del punto de interés]
* [!UICONTROL Distancia hasta el centro del punto de interés]
* [!UICONTROL Id. de punto de interés]

## [!UICONTROL Voz y bots de chat]

Las dimensiones y métricas [!UICONTROL Voz y bots de chat] le permiten medir asistentes de voz como Alexa o Google Home. También le permite medir bots de chat de cosecha propia. Las propiedades de medición incluyen:

* **Ciclo de vida**: nivel base del sistema de informes para cualquier aplicación, como el número de inicios y el tipo de plataforma.
* **Conversaciones**: mide intenciones, respuestas y otras métricas y dimensiones relacionadas con la conversación.

Cuando se habilita [!UICONTROL Voice y Chatbots], están disponibles las siguientes dimensiones:

* [!UICONTROL Capacidades del dispositivo de voz] (con las dimensiones [Entrada](/help/components/dimensions/entry-dimensions.md) y [Salida](/help/components/dimensions/exit-dimensions.md))
* [!UICONTROL Autenticación de voz]
* [!UICONTROL Tipo de error de voz]
* [!UICONTROL Calidad de voz]
* [!UICONTROL Respuesta de aplicación de voz]
* [!UICONTROL Idioma de voz]

Están disponibles las siguientes métricas:

* [!UICONTROL Sesión de finalización de voz]
* [!UICONTROL Error de voz]
* [!UICONTROL Expresiones de voz]

## Informes y atribuciones anteriores para visitas en segundo plano

Los informes heredados significan que las visitas generadas cuando una aplicación está en segundo plano se tratan como visitas en primer plano normales. Aparecen en los informes y afectan a la atribución. Esta configuración heredada suele ser deseable para mantener la coherencia con implementaciones heredadas.

El Adobe recomienda deshabilitar los informes heredados para que las visitas en segundo plano no sean visibles. Si desea incluir las visitas en segundo plano en el análisis, puede habilitar la configuración [Grupo de informes virtuales](/help/components/vrs/vrs-about.md) **[!UICONTROL Incluir visitas en segundo plano]**.
