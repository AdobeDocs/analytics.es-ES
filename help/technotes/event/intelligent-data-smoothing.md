---
title: Suavizado de datos inteligente
description: Descubra cómo el suavizado de datos inteligente analiza las tendencias históricas para predecir el valor de cualquier métrica dentro de un período de tiempo afectado.
feature: Herramientas de IA
role: Business Practitioner, Administrator
translation-type: tm+mt
source-git-commit: aa9f0a8f5b7b1780d0b0be729775c573e12caa35
workflow-type: tm+mt
source-wordcount: '258'
ht-degree: 1%

---

# Suavizado de datos inteligente

En raras ocasiones, algunos factores pueden afectar a la calidad de los datos. El tráfico de bots, los cambios de implementación o las interrupciones del servicio pueden afectar a la integridad de los datos recopilados. También complican el análisis sobre cómo el evento puede haber afectado a la integridad de los datos.

El suavizado de datos inteligente es un prototipo en [Analytics Labs](/help/analyze/tech-previews/overview.md) que puede ayudar a completar esta vista analizando tendencias históricas para predecir el valor de cualquier métrica dentro del período de tiempo afectado. El prototipo aplica algoritmos avanzados de aprendizaje automático para trazar los valores esperados para las métricas durante el período de tiempo que se analiza.

## Ejecución del suavizado de datos inteligente

1. Vaya a Adobe Analytics Labs:
   ![Labs](assets/labs.png)
1. Inicie el prototipo de suavizado de datos inteligente .
   ![Iniciar prototipo](assets/intelligent-ds.png)
1. Agregue la métrica que debe analizarse a la tabla improvisada. El prototipo solo funciona con una granularidad diaria, por lo que debe asegurarse de que la dimensión de la tabla sea Día.
   ![Añadir métrica](assets/add-metric.png)
1. Elija un intervalo de fechas que sea más ancho que la ventana del evento, pero asegúrese de que incluye el evento.
   ![Intervalo de fechas](assets/date-range.png)
1. Haga clic en el icono de engranaje de la métrica en la tabla improvisada.
   ![Icono de engranaje](assets/gear-icon.png)
1. En [!UICONTROL Configuración de datos], seleccione la opción [!UICONTROL Suavizado de datos].
   ![Suavizado de datos](assets/column-setting.png)
1. Seleccione el intervalo de fecha y fecha correspondiente al evento y haga clic en [!UICONTROL Aplicar].
Asegúrese de que el intervalo de datos para el suavizado de datos sea un subconjunto del intervalo de fechas seleccionado para el panel. La métrica de la tabla y el gráfico se sustituyen por los valores predichos.
   ![Valores predichos](assets/predictive-values.png)