---
description: Configure un grupo de informes asignado a Experience Cloud para utilizarlo en Advertising Analytics.
title: Habilitación de un grupo de informes para Advertising Analytics
feature: Advertising Analytics
exl-id: 3a467e41-2755-46c1-b077-b42946562e6b
TQID: https://experienceleague.adobe.com/sGEXiz2RiDhf9p-2df76o-XxBERTKPB-O-rZeIb4BBI
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: eb9732ab-8232-4b21-bc4c-89de86dbe4d7
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 268
ht-degree: 27%

---

# Habilitación de un grupo de informes para Advertising Analytics

Para ver los datos de búsqueda de Advertising Analytics en Analytics, debe configurar cada grupo de informes asignado a Experience Cloud para los informes de Advertising Analytics.

1. Vaya a **[!UICONTROL Administración]** > **[!UICONTROL Grupos de informes]**.

1. Seleccione el grupo de informes asignado a su organización de Experience Cloud.
1. Haga clic en **[!UICONTROL Editar configuración]** > **[!UICONTROL Configuración de Advertising Analytics]**.

   ![Creación de informes](assets/aa-reporting.png)

1. Seleccione **[!UICONTROL No está familiarizado con Advertising Analytics? Haga clic aquí para obtener más información sobre]** y obtener más información sobre Advertising Analytics.

1. Establezca la asignación y caducidad de la variable que desea que utilice la variable de ID de AMO. Las variables de conversión (eVars) permiten a Adobe Analytics atribuir eventos de éxito a valores de variable específicos. A veces, las variables encuentran más de un valor antes de alcanzar un evento de éxito. En estos casos, la asignación determina qué valor de variable recibe crédito por el evento.

   | Configuración | Definición |
   |--- |--- |
   | **[!UICONTROL Asignación]** | Seleccionar entre:<br/> **[!UICONTROL Valor original (primero)]**: El primer valor visto obtiene crédito de asignación completo, independientemente de los valores subsiguientes de esa variable. <br/>**[!UICONTROL Más reciente (último)]**: el último valor visto obtiene crédito de asignación completo para el evento de éxito, independientemente de las variables que se activaron antes. |
   | **[!UICONTROL Caduca después de]** | Permite especificar un período de tiempo o un evento tras el cual caduca el valor de la eVar (es decir, ya no recibe crédito por los eventos de éxito).  Si se da un evento de éxito después de que caduque la eVar, el valor Ninguno recibe crédito por el evento (no había ninguna eVar activa). |

1. Haga clic en **[!UICONTROL Habilitar los informes de Advertising Analytics]** (primera vez) o en **[!UICONTROL Actualizar los informes de Advertising Analytics]** (veces posteriores). El grupo de informes ya está listo para recibir los datos de búsqueda de Advertising Analytics. Ya está listo para [crear cuentas de Advertising](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-create-ad-account.md).
