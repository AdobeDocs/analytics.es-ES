---
description: Habilite dimensiones y métricas para usarlas en el seguimiento de aplicaciones móviles.
title: Creación de informes de aplicaciones
feature: Admin Tools
exl-id: ec19695a-2961-45e4-bf44-434f0ff9e3c9
TQID: https://experienceleague.adobe.com/oF-tETs2-MWjSLoo5bVUmrr2nS4N1o2shD4DkMDAVLU
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32id: c153fd90-23e1-4614-81d3-3cc7571227f7id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7aid: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
subfeature_v2: id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06id: b3a8b8a0-1cc2-48a8-ac82-ffd9c66ccab4id: c4cb071e-4667-4fb1-b1f1-d8994549cfb2id: c77ba355-6681-41fe-b719-563d3f507fdbid: ef60b66e-5984-4336-ba72-6d978b1b6f87id: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 543
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

Las métricas disponibles son las siguientes:

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
* Identificar, crear y visualizar puntos de interés específicos. Los puntos de interés deben definirse en el archivo de configuración de Mobile SDK.
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

Las métricas disponibles son las siguientes:

* [!UICONTROL Sesión de finalización de voz]
* [!UICONTROL Error de voz]
* [!UICONTROL Expresiones de voz]

## Uso de informes anteriores y atribución de resultados en segundo plano

Los informes heredados significan que las visitas generadas cuando una aplicación está en segundo plano se tratan como visitas en primer plano normales. Aparecen en los informes y afectan a la atribución. Esta configuración heredada suele ser deseable para mantener la coherencia con implementaciones heredadas.

Adobe recomienda deshabilitar los informes heredados para que las visitas en segundo plano no sean visibles. Si desea incluir las visitas en segundo plano en el análisis, puede habilitar la configuración [Grupo de informes virtuales](/help/components/vrs/vrs-about.md) **[!UICONTROL Incluir visitas en segundo plano]**.
