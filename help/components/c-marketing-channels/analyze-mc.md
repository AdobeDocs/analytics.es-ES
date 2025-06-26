---
title: Analizar Canales de marketing
description: Obtenga información sobre cómo utilizar las dimensiones de Canales de marketing en Workspace.
feature: Marketing Channels
exl-id: 7030e41a-4e92-45c7-9725-66a3ef019313
source-git-commit: 16fdad50b9d63bc6db07347c6ec91fb0d2df5722
workflow-type: tm+mt
source-wordcount: '405'
ht-degree: 90%

---

# Analizar Canales de marketing

>[!NOTE]
>
>Para maximizar la efectividad de los canales de marketing para Attribution y Adobe Analytics, hemos publicado [prácticas recomendadas revisadas](/help/components/c-marketing-channels/mchannel-best-practices.md).
>
>Los administradores de Analytics pueden administrar canales de marketing para sus organizaciones, tal como se describe en [Administrar canales de marketing](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/marketing-channels/c-channels.md).

Quizá quiera saber cuál de sus canales de marketing es el más efectivo y con quién, para que pueda dirigir mejor sus esfuerzos y recibir un mejor retorno de la inversión de marketing. En Adobe Analytics, las dimensiones y métricas de los Canales de marketing en Workspace son una de las herramientas que pueden ayudarle a realizar un seguimiento de la influencia de diferentes canales en sus pedidos, ingresos, etc. y le proporciona información útil sobre el canal. Estas son las dimensiones y métricas que puede usar relacionadas con los Canales de marketing:

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

Los detalles de Canales de marketing se insertan más profundamente en cada canal para mostrar campañas, colocaciones, etc. específicas. Puede desglosar cada Canal de marketing en detalles:

![](assets/mc-viz4.png)

## Aplicar modelos de atribución

Puede usar [Atribución](/help/analyze/analysis-workspace/attribution/overview.md) para aplicar distintos modelos de atribución de forma instantánea:

![](assets/mc-viz5.png)

Observe cómo la misma métrica (Pedidos en línea) genera resultados diferentes al aplicar modelos de atribución diferentes.

## Análisis de marketing entre fichas

Con el Canal de primer contacto heredado y el Canal de último contacto, puede obtener una vista útil en las interacciones del canal:

![](assets/mc-viz6.png)

Obtenga más información acerca del análisis de marketing entre pestañas en este vídeo: [Uso del análisis entre pestañas para explorar la atribución de marketing básica en Analysis Workspace](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/attribution-iq/using-cross-tab-analysis-to-explore-basic-marketing-attribution-in-analysis-workspace.html?lang=es).
