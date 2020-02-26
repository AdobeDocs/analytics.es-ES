---
description: Se puede especificar un intervalo de fechas complejo mediante la creación de una expresión personalizada.
title: Resumen de expresiones de fechas personalizadas
topic: Report builder
uuid: 7d6d7c03-a3f4-4dec-8343-de2e6478bf06
translation-type: tm+mt
source-git-commit: fa1b0b7fb24d0cd2c205fbbb6a1e526f243531f8

---


# Resumen de expresiones de fechas personalizadas

Se puede especificar un intervalo de fechas complejo mediante la creación de una expresión personalizada.

Le recomendamos que consulte un calendario al crear expresiones para especificar correctamente el número de semanas y días. Excel cuenta con distintas funciones incorporadas que permiten calcular el número de días, días laborables, meses y años entre fechas. Estas funciones se pueden utilizar en fórmulas para calcular otros intervalos como, por ejemplo, semanas y trimestres.

**Para activar expresiones personalizadas**

Este es un ejemplo de uso **[!UICONTROL Rolling Dates]**.

1. En el [!UICONTROL Request Wizard: Step 1], en lugar de usar **[!UICONTROL Preset Dates]**, seleccione **[!UICONTROL Rolling Dates]**.

   ![](assets/rolldates1.png)

1. Cambie a móvil semanal, mensual, trimestral o anual. Observe cómo cambian las opciones siguientes.
1. Para obtener más opciones de personalización, haga clic en **[!UICONTROL Show Advanced Options]**.

   ![](assets/rolldates2.png)

1. Por ejemplo, si cambia las fechas anteriores a móvil mensualmente desde el primer día hace tres meses hasta el primer día de este mes, las fechas de la parte de opciones avanzadas se actualizarán para reflejar lo siguiente:

   ![](assets/rolldatesfor3.png)

1. Activar **[!UICONTROL Customize Expression]**. Al seleccionar las opciones en **[!UICONTROL Rolling Dates]**, puede ver fácilmente la sintaxis de las expresiones de fecha personalizadas.

   ![](assets/rolldatesfor5.png)

   Puede utilizar Opciones avanzadas para combinar y coincidir expresiones de fecha personalizadas. Por ejemplo, si desea ver los datos del primer día del año hasta el final del último mes completo, puede introducir lo siguiente: `From: cy``To: cm-1d`. En el asistente, esas fechas se muestran como 1/1/2020-1/31/2020.
