---
description: Cuando se programa un informe, se puede seleccionar una lista de publicación para utilizarla en la distribución.
title: Permitir anulaciones de la lista de publicación
topic: Report builder
uuid: f2cc9878-ab54-4c6f-8a88-3f3b579955e3
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Permitir anulaciones de la lista de publicación

Cuando se programa un informe, se puede seleccionar una lista de publicación para utilizarla en la distribución.

Las listas de publicaciones se configuran en las Herramientas de administración de Analytics.

Consulte el [Administrador de la Lista de publicaciones](https://marketing.adobe.com/resources/help/es_ES/reference/publishing_list.html) en la referencia de Analytics.

Para activar esta función, vaya a la [!UICONTROL Request Wizard: Step 1] ventana.

If you enable [!UICONTROL Allow Publishing List Override], the report suite assigned to each recipient in the publishing list replaces the report suite for this request. Asimismo, si el libro contiene varios grupos de informes, se utilizará el ID del grupo de informes asociado a la lista de publicación.

Esta opción no está disponible para los grupos de informes que se seleccionen desde las celdas.

>[!NOTE] Si el informe programado se envía a varias listas de publicación, el informe se ejecuta una vez para cada lista. Los grupos de informes variables se reemplazan por el grupo de informes asignado a la lista de publicación.

