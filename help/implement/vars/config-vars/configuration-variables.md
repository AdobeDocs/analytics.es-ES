---
title: Variables de configuración
description: Utilice variables de configuración para determinar cómo se recopilan los datos.
feature: Appmeasurement Implementation
exl-id: 3f017a94-b71d-47da-8ab4-daf32475ed34
role: Admin, Developer
TQID: https://experienceleague.adobe.com/amtLWIgyADqWBOv38xdJ6AF4IjhJ0aGVrvYqXLckfkI
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: c069c44e-5426-4c1a-accc-8028662f2fdeid: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 126
ht-degree: 65%

---

# Información general de variables de configuración

Las variables de configuración controlan la manera en que se capturan y procesan los datos en los informes. No suelen contener valores de dimensión o valores de métrica.

## Establecer variables de configuración

En implementaciones que utilizan la extensión Web SDK o la extensión Analytics, las variables de configuración generalmente se encuentran en la configuración de la extensión:

1. Inicie sesión en la [Recopilación de datos de Adobe Experience Platform](https://experience.adobe.com/data-collection) con sus credenciales de Adobe ID.
1. Haga clic en la propiedad de etiquetas deseada.
1. Haga clic en la ficha [!UICONTROL Extensiones] y, a continuación, haga clic en [!UICONTROL Configurar] en la extensión.

En implementaciones de JavaScript que utilizan `AppMeasurement.js`, las variables de configuración generalmente se establecen en la parte superior del archivo JS.

>[!IMPORTANT]
>
>Asegúrese de que todas las variables de configuración estén establecidas antes de llamar a un método de seguimiento ([`t()`](../functions/t-method.md) o [`tl()`](../functions/tl-method.md)). Evite establecer variables de configuración en la función [`doPlugins()`](../functions/doplugins.md).
