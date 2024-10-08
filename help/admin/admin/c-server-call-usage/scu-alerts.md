---
description: Añada o administre alertas de uso de llamadas al servidor. Al configurar una alerta, se aplica a todos los grupos de informes en todas las empresas de inicio de sesión de una empresa de facturación.
title: Alertas sobre el uso de llamadas al servidor
feature: Server Call Usage
exl-id: 35926566-c570-4ed2-9bbc-0906518bcf64
role: Admin
source-git-commit: 373a1ecffafdcefe3c7b60954f14c2f3a5ca386d
workflow-type: tm+mt
source-wordcount: '513'
ht-degree: 92%

---

# Alertas de uso de llamadas al servidor

Al configurar una alerta, se aplica a todos los grupos de informes en todas las empresas de inicio de sesión de una empresa de facturación.

Las alertas de uso de llamadas al servidor forman parte de la interfaz de usuario [Alertas](/help/components/c-alerts/alert-manager.md).

Está previamente completado con **1 alerta predeterminada** que aparece en cualquier empresa de inicio de sesión con acceso a la función Uso de llamadas al servidor. Esta alerta activa una notificación destinada a todos los administradores de la empresa de inicio de sesión si se cumple uno de los siguientes criterios:

* “Cualquier” uso de llamadas al servidor que sea “mayor o igual que” el 100 % para cualquier tipo de llamada al servidor para la que esté autorizado, O
* “Cualquier” uso de llamadas al servidor que sea “mayor o igual que” el 90% para cualquier tipo de llamada al servidor para la que esté autorizado, O
* “Cualquier” uso de llamadas al servidor que sea “mayor o igual que” el 75 % para cualquier tipo de llamada al servidor para la que esté autorizado Y “Periodo de uso empleado” que sea “menor o igual que” el 75 % del periodo de uso.

![](/help/admin/admin/c-server-call-usage/assets/alerts.png)

Puede acceder a las alertas de uso de llamadas al servidor de dos formas:

* Haga clic en **[!UICONTROL Administrar alertas]** en la esquina superior derecha de la ficha Uso actual en la pestaña de uso de Grupo de informes o
* Vaya a **[!UICONTROL Componentes]** > **[!UICONTROL Alertas]** en Adobe Analytics.

## Crear alertas de uso de llamadas al servidor {#create}

Para crear alertas adicionales,

1. Haga clic en **[!UICONTROL + Añadir]** y seleccione **[!UICONTROL Alerta de uso de llamadas al servidor]**.

   ![](/help/admin/admin/c-server-call-usage/assets/server_call_alert.png)

1. Defina la alerta.

   ![](/help/admin/admin/c-server-call-usage/assets/sc_alert.png)

   * **Título**: Especifique un nombre descriptivo. No es posible guardar la alerta sin nombre.
   * **Granularidad**: Hace referencia a la frecuencia con la que se consultará la alerta. *En este momento solo admitimos granularidad Semanal.* Esto significa que la alerta se comprobará de forma semanal y consultará los datos del periodo de uso actual.
   * **Destinatarios**: Especifique cualquier miembro de la organización que deba recibir un correo electrónico cuando la alerta active el umbral especificado.
   * **Fecha de caducidad**: De forma predeterminada, la fecha de caducidad es de un año a partir de la fecha de creación de la alerta.
   * **Enviar una alerta cuando**:

      * Activación por cualquiera de estas métricas
Añada el tipo de llamadas al servidor como métrica y especifique el umbral de alertas seleccionando el modificador y el umbral:
         * mayor o igual que
         * menor o igual que
      * Con
Especifique el umbral y la condición (mayor o igual que, menor o igual que) para el Periodo de uso empleado.

1. Haga clic en **[!UICONTROL Guardar]**.

## Administrar alertas de uso de llamadas al servidor {#manage}

![](/help/admin/admin/c-server-call-usage/assets/alert_mgmt.png)

Para administrar alertas:

1. Seleccione la casilla junto a una o más alertas. Las acciones de la administración de alertas se muestran en la parte superior.
1. Complete una o más de estas acciones:

   | Acción | Definición |
   |--- |--- |
   | + Agregue | Acceda al [Generador de alertas](/help/admin/admin/c-server-call-usage/scu-alerts.md) haciendo clic en [!UICONTROL + Añadir]. |
   | Etiqueta | Etiquete alertas para organizarlas y que sea más fácil utilizarlas. |
   | Eliminar | Puede eliminar todas las alertas excepto las predeterminadas. |
   | Cambiar nombre | Puede cambiar el nombre de todas las alertas excepto el de las predeterminadas. |
   | Aprobar | Apruebe alertas para hacerlas “oficiales”. |
   | Habilitar/Deshabilitar | Puede habilitar o deshabilitar todas las alertas, incluso las predeterminadas. |
   | Renovar | Cuando se seleccionan una o varias alertas, estas se pueden renovar. Esto retrasa las fechas de caducidad y las amplía a 1 año a partir del momento en que se hace clic en [!UICONTROL Renovar] sin tener en cuenta la fecha de caducidad original. |
   | Exportar a CSV | Consulte [Descargar informe de uso](/help/admin/admin/c-server-call-usage/report-suite-usage.md) |

   {style="table-layout:auto"}
