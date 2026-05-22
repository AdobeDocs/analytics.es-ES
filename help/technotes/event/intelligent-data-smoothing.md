---
title: Suavizado de datos inteligente
description: Descubra cómo el suavizado de datos inteligente analiza las tendencias históricas para predecir el valor de cualquier métrica dentro de un período de tiempo afectado.
feature: AI Tools
role: User, Admin
exl-id: b7a2e5d5-99d4-408d-84e6-67abff9e8727
TQID: 'https://experienceleague.adobe.com/iqjuEBGaCRcwmWfZo6rC1DXi8y4iyj9gB87tpvXmJdk'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: b7156124-d291-4de4-ac0c-ed17d8078449
topic_v2:
  - id: b4dd41a7-ccf8-4e9d-918e-acaab534a307
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: eb30f47f-d87a-400f-8f78-63ce7979ff56
source-git-commit: 50f9ff18816ad88f231762b8b37c1ab9e1787b6f
workflow-type: tm+mt
source-wordcount: 256
ht-degree: 3%

---

# Suavizado de datos inteligente

En raras ocasiones, algunos factores pueden afectar a la calidad de los datos. El tráfico de bots, los cambios de implementación o las interrupciones del servicio pueden afectar a la integridad de los datos recopilados. También complican el análisis sobre cómo el evento puede haber afectado a la integridad de los datos.

El suavizado de datos inteligente es un prototipo en [Analytics Labs](/help/analyze/labs.md) que puede ayudar a completar esta vista analizando las tendencias históricas para predecir el valor de cualquier métrica dentro del período de tiempo afectado. El prototipo aplica algoritmos avanzados de aprendizaje automático para trazar los valores esperados para las métricas a lo largo del período de tiempo que se analiza.

## Ejecutar suavizado de datos inteligente

1. Vaya a Adobe Analytics Labs:
   ![Labs](assets/labs.png)
1. Inicie el prototipo de suavizado de datos inteligente.
   ![prototipo de lanzamiento](assets/intelligent-ds.png)
1. Agregue la métrica que debe analizarse a la tabla de forma libre. El prototipo solo funciona con una granularidad diaria, por lo que asegúrese de que la dimensión de la tabla sea Día.
   ![Agregar métrica](assets/add-metric.png)
1. Elija un intervalo de fechas que sea más ancho que la ventana del evento, pero asegúrese de que incluye el evento.
   ![Intervalo de fecha](assets/date-range.png)
1. Haga clic en el icono de engranaje de la métrica en la tabla de forma libre.
   ![Icono de engranaje](assets/gear-icon.png)
1. En [!UICONTROL Configuración de datos], seleccione la opción [!UICONTROL Suavizado de datos].
   ![Suavizado de datos](assets/column-setting.png)
1. Seleccione el intervalo de fecha/fecha correspondiente al evento y haga clic en [!UICONTROL Aplicar].
Asegúrese de que el intervalo de datos para el suavizado de datos sea un subconjunto del intervalo de fechas seleccionado para el panel. Las métricas de la tabla y el gráfico se sustituyen por los valores predichos.
   ![Valores predichos](assets/predictive-values.png)
