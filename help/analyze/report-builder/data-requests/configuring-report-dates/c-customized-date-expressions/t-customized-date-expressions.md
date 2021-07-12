---
description: Se puede especificar un intervalo de fechas complejo mediante la creación de una expresión personalizada.
title: Resumen de expresiones de fechas personalizadas
uuid: 7d6d7c03-a3f4-4dec-8343-de2e6478bf06
feature: Report Builder
role: User, Admin
exl-id: b3bdc07e-5c2d-4be3-86c9-b4b7380be0f6
source-git-commit: 7226b4c77371b486006671d72efa9e0f0d9eb1ea
workflow-type: tm+mt
source-wordcount: '240'
ht-degree: 30%

---

# Resumen de expresiones de fechas personalizadas

Se puede especificar un intervalo de fechas complejo mediante la creación de una expresión personalizada.

Se recomienda hacer referencia a un calendario al crear expresiones para especificar el número de semanas y días correctamente. Excel cuenta con distintas funciones incorporadas que permiten calcular el número de días, días laborables, meses y años entre fechas. Estas funciones se pueden utilizar en fórmulas para calcular otros intervalos como, por ejemplo, semanas y trimestres.

**Para activar expresiones personalizadas**

Este es un ejemplo que utiliza **[!UICONTROL Fechas móviles]**.

1. En el [!UICONTROL Asistente para solicitudes: Paso 1], en lugar de utilizar **[!UICONTROL Fechas preestablecidas]**, seleccione **[!UICONTROL Fechas móviles]**.

   ![](assets/rolldates1.png)

1. Cambie a móvil semanal, mensual, trimestral o anual. Observe cómo cambian las opciones siguientes.
1. Para obtener más opciones de personalización, haga clic en **[!UICONTROL Mostrar opciones avanzadas]**.

   ![](assets/rolldates2.png)

1. Por ejemplo, si cambia las fechas anteriores a móvil mensual desde el primer día de hace tres meses hasta el primer día de este mes, las fechas de la parte de opciones avanzadas se actualizarán para reflejar eso:

   ![](assets/rolldatesfor3.png)

1. Active **[!UICONTROL Personalizar expresión]**. Al seleccionar opciones en **[!UICONTROL Fechas móviles]**, puede ver fácilmente la sintaxis de las expresiones de fecha personalizadas.

   ![](assets/rolldatesfor5.png)

   Puede utilizar Opciones avanzadas para combinar expresiones de fecha personalizadas. Por ejemplo, si desea ver los datos del primer día del año hasta el final del último mes completo, puede introducir lo siguiente: `From: cy` `To: cm-1d`. En el asistente, esas fechas se muestran como 31/1/2020-1/2020.
