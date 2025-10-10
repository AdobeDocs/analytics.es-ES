---
description: Configure un grupo de informes asignado a Experience Cloud para utilizarlo en Advertising Analytics.
title: Habilitación de un grupo de informes para Advertising Analytics
feature: Advertising Analytics
exl-id: 3a467e41-2755-46c1-b077-b42946562e6b
source-git-commit: c53b533a1d037ab3ed811bcc0960418f037a708f
workflow-type: tm+mt
source-wordcount: '292'
ht-degree: 47%

---

# Habilitación de un grupo de informes para Advertising Analytics

Para ver los datos de búsqueda de Advertising Analytics en Analytics, debe configurar cada grupo de informes asignado a Experience Cloud para los informes de Advertising Analytics.

1. Vaya a **[!UICONTROL Administración]** > **[!UICONTROL Grupos de informes]**.

1. Seleccione el grupo de informes asignado a su organización de Experience Cloud.
1. Haga clic en **[!UICONTROL Editar configuración]** > **[!UICONTROL Configuración de Advertising Analytics]**.

   ![Creación de informes](assets/aa-reporting.png)

   >[!IMPORTANT]
   >
   >El ID de AMO hace referencia a la variable de Adobe Advertising Cloud (también conocida como Adobe Media Optimizer) en la que se van a insertar los datos de búsqueda.

1. Seleccione **[!UICONTROL No está familiarizado con Advertising Analytics? Haga clic aquí para obtener más información sobre]** y obtener más información sobre Advertising Analytics.

1. Establezca la asignación y caducidad de la variable que desea que utilice la variable de ID de AMO. Las variables de conversión (eVars) permiten que Adobe Analytics atribuya eventos de éxito a valores específicos de variables. En ocasiones, las variables encuentran más de un valor antes de visitar un evento de éxito. Para estos casos, la asignación determina qué valor de variable recibe crédito por el evento.

   | Configuración | Definición |
   |--- |--- |
   | **[!UICONTROL Asignación]** | Seleccionar entre:<br/> **[!UICONTROL Valor original (primero)]**: El primer valor visto obtiene crédito de asignación completo, independientemente de los valores subsiguientes de esa variable. <br/>**[!UICONTROL Más reciente (último)]**: el último valor visto obtiene crédito de asignación completo para el evento de éxito, independientemente de las variables que se activaron antes. |
   | **[!UICONTROL Caduca después de]** | Permite especificar un período de tiempo o un evento tras el cual caduca el valor de la eVar (es decir, ya no recibe crédito por los eventos de éxito).  Si se da un evento de éxito después de que caduque la eVar, el valor Ninguno recibe crédito por el evento (no había ninguna eVar activa). |

1. Haga clic en **[!UICONTROL Activar informes de Advertising Analytics]** (primera vez) o en **[!UICONTROL Actualizar informes de Advertising Analytics]** (veces subsiguientes). Ahora, su grupo de informes está listo para recibir datos de búsqueda de Advertising Analytics. Ya está listo para [crear cuentas de Advertising](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-create-ad-account.md).
