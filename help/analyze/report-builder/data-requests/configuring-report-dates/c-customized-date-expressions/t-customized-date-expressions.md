---
description: Se puede especificar un intervalo de fechas complejo mediante la creación de una expresión personalizada.
title: Resumen de expresiones de fechas personalizadas
topic: Report builder
uuid: 7d6d7c03-a3f4-4dec-8343-de2e6478bf06
translation-type: tm+mt
source-git-commit: 4f879bc347656bc442108a5174be26efa171d7e3

---


# Resumen de expresiones de fechas personalizadas

Se puede especificar un intervalo de fechas complejo mediante la creación de una expresión personalizada.

Se recomienda que al crear expresiones haga referencia a un calendario con el fin de especificar el número de semanas y días correctamente. Excel cuenta con distintas funciones incorporadas que permiten calcular el número de días, días laborables, meses y años entre fechas. Estas funciones se pueden utilizar en fórmulas para calcular otros intervalos como, por ejemplo, semanas y trimestres.

**Para activar expresiones personalizadas**

1. En el [!UICONTROL Request Wizard: Step 1], en lugar de utilizar &quot;Fechas preestablecidas&quot;, seleccione **[!UICONTROL Rolling Dates]**. Observe cómo cambian las opciones siguientes.

   ![](assets/rolldates1.png)

1. Cambie a móvil semanal, mensual, trimestral o anual.
1. Para obtener más opciones de personalización, haga clic en **[!UICONTROL Show Advanced Options]**. Al seleccionar las opciones en la sección superior, puede ver fácilmente la sintaxis de las expresiones de fecha personalizadas.

   ![](assets/rolldates2.png)

1. Activar **[!UICONTROL Customize Expression]**. Al seleccionar las opciones en **[!UICONTROL Rolling Dates]**, puede ver fácilmente la sintaxis de las expresiones de fecha personalizadas.

   ![](assets/rolldatesfor5.png)

   Puede utilizar Opciones avanzadas para combinar y coincidir expresiones de fecha personalizadas. Por ejemplo, si desea ver los datos desde el primer día del año hasta el final del último mes completo, puede escribir lo siguiente:Desde: cy To: cm-1d. Puede ver que en el asistente confirma que esas fechas son el 1/1/2020-1/31/2020.

   Por ejemplo, si cambia las fechas anteriores a móvil mensualmente desde el primer día hace tres meses hasta el primer día de este mes, las fechas de la parte de opciones avanzadas se actualizarán para reflejar lo siguiente:

   ![](assets/rolldatesfor3.png)

