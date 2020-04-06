---
description: Al programar un informe, puede elegir una lista de publicación para su distribución.
title: Permitir anulaciones de la lista de publicación
topic: Report builder
uuid: f2cc9878-ab54-4c6f-8a88-3f3b579955e3
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Permitir anulaciones de la lista de publicación

Al programar un informe, puede elegir una lista de publicación para su distribución.

Las listas de publicación están configuradas en las herramientas de administración de Analytics.

Consulte [Administrador](https://marketing.adobe.com/resources/help/es_ES/reference/publishing_list.html) de Listas de publicación en la referencia de Analytics.

Para activar esta función, vaya a la [!UICONTROL Request Wizard: Step 1] ventana.

Si se habilita [!UICONTROL Allow Publishing List Override], el grupo de informes asignado a cada destinatario en la lista de publicación reemplaza al grupo de informes para esta solicitud. Además, si el libro contiene varios grupos de informes, se utiliza la ID del grupo de informes asociada a la lista de publicación.

Esta opción no está disponible para los grupos de informes que se seleccionan de las celdas.

>[!NOTE] Si el informe programado se envía a varias listas de publicación, el informe se ejecuta una vez para cada lista. Los grupos de informes variables se reemplazan por el grupo de informes asignado a la lista de publicación.

