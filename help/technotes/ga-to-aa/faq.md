---
title: Preguntas más frecuentes sobre la migración a Adobe Analytics
description: Conozca las respuestas a las preguntas más frecuentes sobre el cambio desde una plataforma de terceros a Adobe.
feature: Third-party Integration
exl-id: 1201909e-b20c-48c5-b287-393da8e22d78
TQID: https://experienceleague.adobe.com/NJPnGHUG-9krAfzRZiNbMd7DS9q5gRGTm-1KM3DMXag
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
subfeature_v2:
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
  - id: e38cbddc-1633-4cd5-bed5-9f289f2a6029
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 418
ht-degree: 54%

---

# Preguntas más frecuentes sobre la migración a Adobe Analytics

**¿Cómo puedo migrar mis datos históricos de mi plataforma de terceros a Adobe Analytics?**

Cada plataforma de Analytics tiene diferentes formas de recopilar, gestionar y almacenar datos. En lugar de migrar datos históricos, Adobe recomienda establecer una fecha de corte clara para empezar a recopilar y utilizar datos en Adobe Analytics. Las fechas de corte más frecuentes utilizadas son el comienzo de un año fiscal, el comienzo de un año natural o el comienzo de un mes natural. Si los usuarios desean ver los datos históricos, pueden iniciar sesión en la plataforma de terceros para obtener cualquier dato histórico necesario.

Si su organización insiste en tener datos históricos transferidos a Adobe, póngase en contacto con el equipo de cuenta de Adobe. Un consultor de implementación puede trabajar con su organización para traducir una exportación de datos de Google Analytics a una fuente de datos que los servidores de recopilación de datos de Adobe puedan ingerir.

Para pasar sobre los datos históricos, se recomienda usar [Customer Journey Analytics](https://experienceleague.adobe.com/es/docs/analytics-platform/using/cja-overview/cja-overview), que puede traer cualquier fuente de datos omnicanal.

**Estoy acostumbrado a ver una lista desplegable de segmentación en muchos de mis informes. ¿Cómo puedo recrear esta situación en [!UICONTROL Analysis Workspace]?**

Los filtros desplegables son una característica flexible y práctica de [!UICONTROL Analysis Workspace] que permite crear una lista desplegable de segmentación. En un proyecto de Workspace:

1. Use ***ctrl***+***clic*** (Windows) o ***cmd***+***haga clic*** (Mac) en los componentes que desee incluir en el filtro desplegable. No está limitado solo a segmentos. Cualquier componente se puede incluir en un filtro desplegable.
2. Arrastre el grupo de componentes al área de trabajo denominada *Colocar un segmento aquí*. Antes de soltarlo, mantén presionado **[!UICONTROL shift]**.

Los usuarios que tengan acceso a este proyecto de [!UICONTROL Workspace] pueden usar este filtro desplegable para aplicar segmentos y otros componentes al proyecto. Consulte [Información general sobre paneles](/help/analyze/analysis-workspace/c-panels/panels.md) en la guía de herramientas de Adobe Analytics para obtener más información.

**Estoy acostumbrado a hacer clic en un elemento de dimensión para ver la navegación por jerarquía. ¿Cómo puedo replicar ese sencillo flujo de trabajo en Analysis Workspace?**

Los valores de dimensión en [!UICONTROL Analysis Workspace] también tienen un flujo de trabajo de desglose sencillo. Acceda al desglose utilizando el menú contextual en un elemento de dimensión. A continuación, seleccione **[!UICONTROL Breakdown]** y el componente deseado. Puede aplicar el mismo desglose a varios elementos de dimensión usando ***ctrl***+***select*** (Windows) o ***cmd***+***select*** (Mac) en cada valor.
