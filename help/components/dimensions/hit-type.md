---
title: Tipo de visita
description: Determina si la visita fue una visita en primer o segundo plano.
feature: Dimensions
exl-id: b922adbb-fe36-46c7-aab2-b9471de07d2f
TQID: https://experienceleague.adobe.com/6G-XpOMMZGum9LAQzKn0zGdeNRmHFPpmYizqRrbKuUE
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: c4cb071e-4667-4fb1-b1f1-d8994549cfb2id: c77ba355-6681-41fe-b719-563d3f507fdbid: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 164
ht-degree: 84%

---

# Tipo de visita

El &quot;Tipo de visita&quot; [dimension](overview.md) determina si una aplicación móvil estaba en primer o segundo plano cuando la visita se envió a los servidores de recopilación de datos de Adobe. Esta dimensión solo es relevante para los grupos de informes que contienen datos para aplicaciones móviles. Los datos del explorador recopilados con AppMeasurement siempre informan de la visita como “Primer plano”.

## Rellene esta dimensión con datos

Esta dimensión funciona de forma predeterminada para todas las implementaciones de SDK móvil en la versión 4.13.6 o superior. Si no utiliza el SDK móvil, todas las visitas se enumeran en el elemento de dimensión “Primer plano”. Si la opción “Deshabilitar informes y atribuciones anteriores para visitas en segundo plano” está activada, las visitas individuales en segundo plano solo aparecerán en el [Grupo de informes virtual](../vrs/vrs-mobile-visit-processing.md).

## Elementos de dimensión

Los elementos de dimensión incluyen `"Foreground"` y `"Background"`. Cualquier visita individual que no se haya enviado en segundo plano de una aplicación móvil pertenece al elemento de dimensión `"Foreground"`. Cualquier visita enviada donde la aplicación móvil estaba en segundo plano pertenece al elemento de dimensión `"Background"`.
