---
description: Explica cómo crear una métrica que muestre los canales de marketing asistidos al realizar pedidos. Esto puede adaptarse a cualquier otro evento de éxito o dimensión que resulte de interés.
title: Métrica de ayudas para pedidos
uuid: 7c82227a-7fcc-486f-bef8-164ea84af77c
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Métrica de ayudas para pedidos

Explica cómo crear una métrica que muestre los canales de marketing asistidos al realizar pedidos. Esto puede adaptarse a cualquier otro evento de éxito o dimensión que resulte de interés.

1. En el Generador de métricas calculadas, asigne el nombre “Pedidos asistidos” a la métrica.
1. En el lienzo Definición, arrastre una métrica de Pedidos. A continuación, para ajustar el modelo de atribución mediante el engranaje de configuración, active la casilla **[!UICONTROL Usar modelos de atribución no predeterminados]**.

   ![](assets/attr-model.png)

1. Seleccione **[!UICONTROL Personalizado]** como el modelo de atribución. Cambie las ponderaciones a 0 (inicial), 100 (reproductor) y 0 (más próximo).

   ![](assets/custom-attr-model.png)

1. Guarde la métrica.
1. Cree una tabla de forma libre en Analysis Workspace con la dimensión Canal de marketing, Pedidos y la nueva métrica Pedidos asistidos.

   ![](assets/mktg-channel-assists.png)

Esta es una forma sencilla de indicar los canales de marketing asistidos al realizar pedidos. Como alternativa, desde una tabla de forma libre, puede hacer clic con el botón derecho en cualquier métrica y ajustar el modelo de atribución directamente desde la tabla.
