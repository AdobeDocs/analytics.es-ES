---
description: Describe los pasos involucrados en la aplicación de filtros a un informe de visitas en el orden previsto.
title: Filtrado de un informe de abandonos mediante el Asistente para solicitudes
feature: Report Builder
role: User, Admin
exl-id: 6134d7d4-7287-4a83-92b6-d250ca15cf69
TQID: https://experienceleague.adobe.com/b-OBsmKfOFGtPK3Ar6pJtGUc3vZ4L2Jeei2sNK-7Npg
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 248
ht-degree: 77%

---

# Filtrado de un informe de abandonos mediante el Asistente para solicitudes

{{legacy-arb}}

Describe los pasos involucrados en la aplicación de filtros a un informe de visitas en el orden previsto.

Este ejemplo muestra el informe Visitas en el orden previsto de la página.

1. En Report Builder de Adobe, haga clic en **[!UICONTROL Crear]** para abrir el Asistente para solicitudes.
1. Seleccione el grupo de informes adecuado.
1. En la vista de árbol de la izquierda, seleccione **[!UICONTROL Rutas]** > **[!UICONTROL Página]** > **[!UICONTROL Página Visitas]**.

   ![Captura de pantalla que muestra la vista de árbol de Windows para el directorio de Report Builder. Visita en el orden previsto de la página seleccionada.](assets/page_fallout.png)

1. Configure los [intervalos de fechas](/help/analyze/legacy-report-builder/data-requests/configuring-report-dates/custom-calendar.md) adecuados.
1. Haga clic en **[!UICONTROL Siguiente]**.
1. En el paso 2 del asistente, en **[!UICONTROL Rótulos de fila]**, haga clic en el vínculo **[!UICONTROL Definir puntos de comprobación]**. (En un informe de visitas en el orden previsto, siempre tiene que definir los elementos de ruta, a diferencia de en un informe de ruta, donde se aplica un patrón previamente).

   ![Captura de pantalla que muestra el vínculo Definir puntos de comprobación.](assets/define_checkpoints.png)

1. Seleccione la opción **[!UICONTROL Filtro]**.

1. En el cuadro de diálogo **[!UICONTROL Definir puntos de comprobación de visitas en el orden previsto de sección del sitio]**, defina los puntos de comprobación entre un rango de celdas o de una lista. A continuación, haga clic en **[!UICONTROL Aceptar]**.
1. Decida si desea seleccionar de un rango de celdas o de una lista.
1. Si selecciona de una lista, haga clic en **[!UICONTROL Añadir]** para seleccionar los puntos de comprobación que desea añadir en la ruta de visitas en el orden previsto. Puede definir entre 3 y 8 puntos de comprobación. (Busque los elementos disponibles haciendo clic en **[!UICONTROL Más]**).

   Para obtener más información sobre cómo perfeccionar el filtro, vea [Dimensiones de filtro](/help/analyze/legacy-report-builder/layout/c-filter-dimensions/filter-dimensions.md).

1. Mueva **[!UICONTROL Elementos disponibles]** de la columna izquierda a la derecha, para ello selecciónelos y haga clic en la flecha naranja.
1. Haga clic en **[!UICONTROL Aceptar]** tres veces y, a continuación, haga clic en **[!UICONTROL Finalizar]**.

   El informe debería actualizarse en este momento.
