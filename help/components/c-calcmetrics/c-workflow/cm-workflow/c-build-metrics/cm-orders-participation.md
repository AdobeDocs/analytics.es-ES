---
description: Explica cómo crear una métrica que muestre los canales de marketing asistidos al realizar pedidos. Esto puede adaptarse a cualquier otro evento de éxito o dimensión que resulte de interés.
seo-description: Explica cómo crear una métrica que muestre los canales de marketing asistidos al realizar pedidos. Esto puede adaptarse a cualquier otro evento de éxito o dimensión que resulte de interés.
seo-title: Métrica de ayudas para pedidos
title: Métrica de ayudas para pedidos
uuid: 7 c 82227 a -7 fcc -486 f-bef 8-164 ea 84 af 77 c
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Métrica de ayudas para pedidos

Explica cómo crear una métrica que muestre los canales de marketing asistidos al realizar pedidos. Esto puede adaptarse a cualquier otro evento de éxito o dimensión que resulte de interés.

1. En el Generador de métricas calculadas, asigne el nombre “Pedidos asistidos” a la métrica.
1. En el lienzo Definición, arrastre una métrica de Pedidos. A continuación, para ajustar el modelo de atribución mediante el engranaje de configuración, active la casilla **[!UICONTROL Usar modelos de atribución no predeterminados].**

   ![](assets/attr-model.png)

1. Seleccione **[!UICONTROL Personalizado]como el modelo de atribución.** Cambie las ponderaciones a 0 (inicial), 100 (reproductor) y 0 (más próximo).

   ![](assets/custom-attr-model.png)

1. Guarde la métrica.
1. Cree una tabla de forma libre en Analysis Workspace con la dimensión Canal de marketing, Pedidos y la nueva métrica Pedidos asistidos.

   ![](assets/mktg-channel-assists.png)

Esta es una forma sencilla de indicar los canales de marketing asistidos al realizar pedidos. Como alternativa, desde una tabla de forma libre, puede hacer clic con el botón derecho en cualquier métrica y ajustar el modelo de atribución directamente desde la tabla.
