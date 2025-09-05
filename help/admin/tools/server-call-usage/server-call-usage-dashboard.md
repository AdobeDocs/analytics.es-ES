---
description: Visualización del uso actual de llamadas al servidor en Adobe Analytics.
title: Ver uso de llamadas al servidor actual
feature: Server Call Usage
exl-id: 07eac732-b9d6-41ab-be34-5688eaa8166e
role: Admin
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '291'
ht-degree: 100%

---

# Ver uso de llamadas al servidor actual

**[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Uso de llamadas al servidor]** > **[!UICONTROL Uso actual]**

>[!IMPORTANT]
>
>Los números de uso y asignación que vea son acumulativos en el conjunto de empresas de inicio de sesión y grupos de informes.

El tablero de Uso actual:

* Muestra un desglose de su consumo y asignación de llamadas al servidor en todos sus tipos de llamadas al servidor. Esta vista podría ser diferente para diferentes clientes y es coherente con lo que incluye el contrato. Por ejemplo, puede que se haya suscrito para 4 tipos separados de llamadas al servidor, primarias y secundarias para web y primarias y secundarias para móvil. En ese caso, esta vista comprenderá 4 fichas, una para cada tipo. En cada ficha, podrá ver el consumo para el periodo de uso actual.
* Compara el uso actual (línea verde) con su límite de uso contractual (línea roja).

  ![](/help/admin/tools/server-call-usage/assets/current_period.png)

* Compara el uso de su periodo actual con el del año pasado (línea azul). Obviamente, la línea azul solo aparecerá si su empresa tiene datos de uso de llamadas al servidor del año anterior.

  >[!NOTE]
  >
  >Si desea ver el uso de un período de tiempo anterior, debe ir a la pestaña [Uso del grupo de informes](/help/admin/tools/server-call-usage/report-suite-usage.md) y descargar los datos de uso de un período anterior.

* Muestra el porcentaje de llamadas utilizado (en porcentajes y datos sin procesar) y el porcentaje del periodo de uso empleado (en porcentajes y datos sin procesar).
* De forma predeterminada, se actualiza a diario, con una latencia de procesamiento de 5 días.
* Permite contraer y ampliar todos los informes breves.

![](/help/admin/tools/server-call-usage/assets/server_call_dashboard.png)

| Término de interfaz de usuario | Definición |
| --- | --- |
| Uso del periodo actual (verde) | El periodo actual se basa en el [periodo de uso](/help/admin/tools/server-call-usage/overage-overview.md). |
| Uso del periodo anterior (azul) | El periodo anterior se define como el periodo de uso actual menos 1 año. |
| Límite de uso (rojo) | Su límite de uso contractual para este periodo de uso. |
