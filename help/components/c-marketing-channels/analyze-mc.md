---
title: Analizar Canales de marketing
description: Obtenga información sobre cómo utilizar las dimensiones de Canales de marketing en Workspace.
feature: Marketing Channels
exl-id: 7030e41a-4e92-45c7-9725-66a3ef019313
TQID: https://experienceleague.adobe.com/XWjRuwOusH-TsOb5rzG8rAIkye3faYxfZzyQOMrav3Q
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32id: c153fd90-23e1-4614-81d3-3cc7571227f7
subfeature_v2: id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06id: b3a8b8a0-1cc2-48a8-ac82-ffd9c66ccab4id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 435
ht-degree: 77%

---

# Analizar Canales de marketing

>[!NOTE]
>
>Para maximizar la efectividad de los canales de marketing para Attribution y Adobe Analytics, hemos publicado [prácticas recomendadas revisadas](/help/components/c-marketing-channels/mchannel-best-practices.md).
>
>Los administradores de Analytics pueden administrar canales de marketing para sus organizaciones, tal como se describe en [Administrar canales de marketing](/help/admin/tools/manage-rs/edit-settings/marketing-channels/c-channels.md).

Quizá quiera saber cuál de sus canales de marketing es el más efectivo y con quién, para que pueda dirigir mejor sus esfuerzos y recibir un mejor retorno de la inversión de marketing. En Adobe Analytics, las dimensiones y métricas de los Canales de marketing en Workspace son una de las herramientas que pueden ayudarle a realizar un seguimiento de la influencia de diferentes canales en sus pedidos, ingresos, etc. y proporcionarle perspectivas de canal útiles. Estas son las dimensiones y métricas que puede usar relacionadas con los Canales de marketing:

![](assets/mc-dims.png)

| Dimensión/Métrica | Definición |
| --- | --- |
| Canal de marketing | Esta es la dimensión de Canales de marketing que se recomienda utilizar. Los modelos de atribución se pueden aplicar en tiempo de ejecución. Esta dimensión se comporta de forma idéntica a la dimensión del canal de último contacto, pero tiene una etiqueta diferente para evitar confusiones al usarla con un modelo de atribución distinto. |
| Canal de último contacto | Dimensión heredada, con modelo de atribución de último contacto preaplicado e inmodificable. |
| Canal de primer contacto | Dimensión heredada, con modelo de atribución de primer contacto preaplicado e inmodificable. |
| Instancias de Canal de marketing | Esta métrica mide el número de veces que se definió un canal de marketing en una solicitud de imagen, incluidas las vistas de página estándar y las llamadas de vínculo personalizado. No incluye valores persistentes. |
| Nuevos compromisos | Esta métrica es similar a Instancias, pero solo se incrementa cuando el canal de marketing de primer contacto se define en una solicitud de imagen. |

## Análisis básico

Esta tabla de forma libre muestra las métricas Pedidos en línea, Ingresos en línea y la Tasa de conversión de cada uno de los Canales de marketing:

![](assets/mc-viz1.png)

Aquí puede ver los pedidos en línea e ingresos en línea de cada Canal de marketing en un gráfico circular:

![](assets/mc-viz2.png)

Este gráfico de líneas muestra las tendencias de los pedidos en línea de varios canales a lo largo del tiempo:

![](assets/mc-viz3.png)

## Análisis avanzado

Los detalles de Canales de marketing se insertan más profundamente en cada canal para mostrar campañas, ubicaciones, etc. específicas. Puede desglosar cada Canal de marketing en detalles:

![](assets/mc-viz4.png)

## Aplicar modelos de atribución

Puede usar [Atribución](/help/analyze/analysis-workspace/attribution/overview.md) para aplicar distintos modelos de atribución de forma instantánea:

![](assets/mc-viz5.png)

Observe cómo la misma métrica (Pedidos en línea) genera resultados diferentes al aplicar modelos de atribución diferentes.

## Análisis de marketing entre fichas

Con el Canal de primer contacto heredado y el Canal de último contacto, puede obtener una vista útil en las interacciones del canal:

![](assets/mc-viz6.png)

Obtenga más información acerca del análisis de marketing entre pestañas en este vídeo: [Uso del análisis entre pestañas para explorar la atribución de marketing básica en Analysis Workspace](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/attribution-iq/using-cross-tab-analysis-to-explore-basic-marketing-attribution-in-analysis-workspace.html?lang=es).
