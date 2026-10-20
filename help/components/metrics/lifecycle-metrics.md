---
title: Métricas del ciclo de vida móvil
description: Métricas basadas en datos recopilados mediante el SDK móvil.
feature: Metrics
exl-id: 64af4942-d249-47a5-a62f-6051f4c44ee3
TQID: 'https://experienceleague.adobe.com/Y1IigGbQygTsS9UD3WEp9z8rLTqkeDuhZZ83AJQMa3o'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
source-git-commit: 6fd4400b33fcfc8bc3cd3ffc54fa738fef3441ef
workflow-type: tm+mt
source-wordcount: '367'
ht-degree: 10%
---
# Métricas del ciclo de vida móvil

>[!BEGINSHADEBOX]

*Esta página hace referencia a datos rastreados con frecuencia a través de Adobe Experience Platform Mobile SDK. Para las dimensiones rastreadas con Mobile SDK, consulte [Dimensiones del ciclo vital móviles](../dimensions/lifecycle-dimensions.md). Para obtener información del dispositivo móvil mediante el agente de usuario, consulte [Dimensiones de búsqueda móvil](../dimensions/mobile-dimensions.md).*

>[!ENDSHADEBOX]

| Nombre de métrica de ciclo vital | Descripción | Variable de datos de contexto |
| --- | --- | --- |
| **[!UICONTROL Primeros lanzamientos]** | Número de veces que la aplicación se ejecutó por primera vez después de instalarla o reinstalarla. | `a.InstallEvent` |
| **[!UICONTROL Actualizaciones]** | El número de veces que la aplicación se ejecutó por primera vez después de una actualización o después de que cambiara su número de versión. | `a.UpgradeEvent` |
| **[!UICONTROL Inicios]** | El número de veces que se ejecutó la aplicación, incluidas las ejecuciones después de bloqueos e instalaciones. También se cuenta un inicio cuando la aplicación se reanuda desde segundo plano después de superar el tiempo de espera de sesión del ciclo vital. | `a.LaunchEvent` |
| **[!UICONTROL Bloqueos]** | El número de veces que la aplicación se bloqueó antes de cerrarse. Se informa del bloqueo la próxima vez que se inicie la aplicación. | `a.CrashEvent` |
| **[!UICONTROL Duración total de la sesión]** | Cantidad total de segundos que duraron las sesiones de la aplicación, según el tiempo que la aplicación haya estado abierta en primer plano. Cada inicio informa de la duración de la sesión anterior; esta métrica es la suma de esos valores. | `a.PrevSessionLength` |
| **[!UICONTROL Tiempo total de la acción]** | Número total de segundos (hora del reloj) entre el inicio y el final de una acción temporizada, entre sesiones. Rellenado con los métodos `trackTimedAction` en el SDK heredado de Mobile Services (4.x). | `a.action.time.total` |
| **[!UICONTROL Tiempo de la acción dentro de la aplicación]** | Cantidad de segundos que la aplicación ha invertido entre el inicio y el final de una acción temporizada, en todas las sesiones. Rellenado con los métodos `trackTimedAction` en el SDK heredado de Mobile Services (4.x). | `a.action.time.inapp` |
| **[!UICONTROL Valor de duración (evento)]** | El valor de duración de un usuario, como compras acumuladas en el tiempo, visualizaciones de anuncios, visualizaciones de vídeo completas o usos compartidos en medios sociales. Rellenado con el método `trackLifetimeValueIncrease` en la versión heredada de SDK de Mobile Services (4.x). | `a.ltv.amount` |

>[!NOTE]
>
>Las métricas [!UICONTROL Tiempo de acción total], [!UICONTROL Tiempo de acción en la aplicación] y [!UICONTROL Valor de duración (evento)] se rellenan con métodos del SDK heredado de Mobile Services (4.x), que ya no es compatible. Adobe Experience Platform Mobile SDK no rellena estas métricas automáticamente. Consulte [Migración de la biblioteca móvil de Adobe (v4) a Experience Platform Analytics](https://developer.adobe.com/client-sdks/resources/upgrade-platform-sdks/analytics/) para ver alternativas a las acciones temporizadas y el seguimiento de valores de duración.
