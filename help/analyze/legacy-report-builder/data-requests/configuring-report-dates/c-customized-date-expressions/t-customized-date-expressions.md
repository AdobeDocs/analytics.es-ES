---
description: Se puede especificar un intervalo de fechas complejo mediante la creación de una expresión personalizada.
title: Resumen de expresiones de fechas personalizadas
uuid: 7d6d7c03-a3f4-4dec-8343-de2e6478bf06
feature: Report Builder
role: User, Admin
exl-id: b3bdc07e-5c2d-4be3-86c9-b4b7380be0f6
source-git-commit: bb908f8dd21f7f11d93eb2e3cc843f107b99950d
workflow-type: tm+mt
source-wordcount: '278'
ht-degree: 24%

---

# Expresiones de fecha personalizadas

Se puede especificar un intervalo de fechas complejo mediante la creación de una expresión personalizada.

Cuando genere expresiones, consulte un calendario para especificar correctamente el número de semanas y días. Excel cuenta con distintas funciones incorporadas que permiten calcular el número de días, días laborables, meses y años entre fechas. Estas funciones se pueden utilizar en fórmulas para calcular otros intervalos como, por ejemplo, semanas y trimestres.

**Para activar expresiones personalizadas**

El siguiente ejemplo muestra cómo habilitar una expresión personalizada para **[!UICONTROL Fechas móviles]**.

1. En el [!UICONTROL Asistente para solicitudes: Paso 1], en lugar de usar **[!UICONTROL Fechas preestablecidas]**, seleccione **[!UICONTROL Fechas móviles]**.

   ![Captura de pantalla que muestra las fechas móviles seleccionadas.](assets/rolldates1.png)

1. Cambie a Móvil semanal, mensual, trimestral o anual. Observe cómo cambian las opciones siguientes.
1. Para obtener más opciones de personalización, haga clic en **[!UICONTROL Mostrar opciones avanzadas]**.

   ![Captura de pantalla que resalta las opciones avanzadas de Show.](assets/rolldates2.png)

1. Por ejemplo, si cambia las fechas anteriores a móvil mensual desde el primer día hace tres meses hasta el primer día de este mes, las fechas de la parte de opciones avanzadas se actualizarán para reflejar lo siguiente:

   ![Captura de pantalla que muestra las fechas móviles desde el primer día hace tres meses hasta el primer día de este mes.](assets/rolldatesfor3.png)

1. Habilitar **[!UICONTROL Personalizar expresión]**. Al seleccionar opciones en **[!UICONTROL Fechas móviles]**, puede ver fácilmente la sintaxis de las expresiones de fecha personalizadas.

   ![Captura de pantalla que muestra la expresión personalizada seleccionada.](assets/rolldatesfor5.png)

   Puede utilizar Opciones avanzadas para mezclar y hacer coincidir expresiones de fecha personalizadas. Por ejemplo, si desea ver los datos desde el primer día del año hasta el final del último mes completo, puede escribir lo siguiente: `From: cy` `To: cm-1d`. En el asistente, esas fechas se muestran como 1/1/2020-1/31/2020.
