---
description: Añada o administre alertas de uso de llamadas al servidor. Al configurar una alerta, se aplica a todos los grupos de informes en todas las empresas de inicio de sesión de una empresa de facturación.
title: Alertas sobre el uso de llamadas al servidor
uuid: 701fd542-5b24-42df-97a0-08e10929fa48
translation-type: tm+mt
source-git-commit: 8d6685d241443798be46c19d70d8150d222ab9e8

---


# Alertas sobre el uso de llamadas al servidor

Al configurar una alerta, se aplica a todos los grupos de informes en todas las empresas de inicio de sesión de una empresa de facturación.

## Información general

A new alert category called **[!UICONTROL Server Calls Usage Alert]** is part of the existing [Alert Management](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/virtual-analyst/intelligent-alerts/intellligent-alerts.html) user interface.

Está previamente completado con **1 alerta predeterminada** que aparece en cualquier empresa de inicio de sesión con acceso a la función Uso de llamadas al servidor. Esta alerta activa una notificación destinada a todos los administradores de la empresa de inicio de sesión si se cumple uno de los siguientes criterios:

* “Cualquier” uso de llamadas al servidor que sea “mayor o igual que” el 100 % para cualquier tipo de llamada al servidor para la que esté autorizado, O
* “Cualquier” uso de llamadas al servidor que sea “mayor o igual que” el 90 % para cualquier tipo de llamada al servidor para la que esté autorizado, O
* “Cualquier” uso de llamadas al servidor que sea “mayor o igual que” el 75 % para cualquier tipo de llamada al servidor para la que esté autorizado Y “Periodo de uso empleado” que sea “menor o igual que” el 75 % del periodo de uso.

![](assets/alerts.png)

Puede acceder a las alertas de uso de llamadas al servidor de dos formas:

* Click **[!UICONTROL Manage Alerts]** in the upper right corner on the Current Usage tab or the Report Suite usage tab, or
* Vaya a **[!UICONTROL Components]** > **[!UICONTROL Alerts]** en Adobe Analytics.

## Crear alertas de uso de llamadas al servidor {#section_2A2882C6D48D47C1944D52FB7C766BEC}

Para crear alertas adicionales,

1. Haga clic **[!UICONTROL + Add]** y seleccione **[!UICONTROL Server Call Usage Alert]**.

   ![](assets/server_call_alert.png)

1. Defina la alerta.

   ![](assets/sc_alert.png)

   * **Título**: Especifique un nombre descriptivo. No es posible guardar la alerta sin nombre.
   * **Granularidad**: Hace referencia a la frecuencia con la que se consultará la alerta. *En este momento solo admitimos granularidad Semanal.* Esto significa que la alerta se comprobará de forma semanal y consultará los datos del periodo de uso actual.
   * **Destinatarios**: Especifique cualquier miembro de la organización que deba recibir un correo electrónico cuando la alerta active el umbral especificado.
   * **Fecha de caducidad**: De forma predeterminada, la fecha de caducidad es de un año a partir de la fecha de creación de la alerta.
   * **Enviar una alerta cuando**:

      * Activación por cualquiera de estas métricas
Añada el tipo de llamadas al servidor como métrica y especifique el umbral de alertas seleccionando el modificador y el umbral:
         * mayor o igual que
         * menor o igual que
      * con
Especifique el umbral y la condición (mayor o igual que, menor o igual que) para el Periodo de uso empleado.

1. Haga clic en **[!UICONTROL Save]**.

## Administrar alertas de uso de llamadas al servidor {#section_8FF98170763C4B5CBEC6DD43F893177A}

![](assets/alert_mgmt.png)

Para administrar alertas:

1. Seleccione la casilla junto a una o más alertas. Las acciones de la administración de alertas se muestran en la parte superior.
1. Complete una o más de estas acciones:

   | Acción | Definición |
   |--- |--- |
   | + Agregue | Access the [Alert Builder](/help/admin/c-server-call-usage/scu-alerts.md) by clicking  [!UICONTROL + Add]. |
   | Etiqueta | Etiquete alertas para organizarlas y que sea más fácil utilizarlas. |
   | Eliminar | Puede eliminar todas las alertas excepto las predeterminadas. |
   | Cambiar nombre | Puede cambiar el nombre de todas las alertas excepto el de las predeterminadas. |
   | Aprobar | Apruebe alertas para hacerlas “oficiales”. |
   | Habilitar/Deshabilitar | Puede habilitar o deshabilitar todas las alertas, incluso las predeterminadas. |
   | Renovar | Cuando se seleccionan una o varias alertas, estas se pueden renovar. This extends their expiration dates to be 1 year from the day [!UICONTROL Renew] was clicked, regardless of their original expiration date. |
   | Exportar a CSV | Consulte [Descargar informe de uso](/help/admin/c-server-call-usage/report-suite-usage.md) |

