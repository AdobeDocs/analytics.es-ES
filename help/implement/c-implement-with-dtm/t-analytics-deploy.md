---
description: Cree una herramienta Adobe Analytics para la implementación mediante el uso de Dynamic Tag Management. Este procedimiento describe una implementación manual (heredada).
keywords: Dynamic Tag Management
seo-description: Cree una herramienta Adobe Analytics para la implementación mediante el uso de Dynamic Tag Management. Este procedimiento describe una implementación manual (heredada).
seo-title: Implementar Adobe Analytics manualmente (heredado)
solution: Marketing Cloud, Analytics, Target, Administración dinámica de etiquetas
title: Implementar Adobe Analytics manualmente (heredado)
uuid: d 3 ad 2035-393 d -4 a 77-81 f 6-e 749 ee 717 c 09
translation-type: tm+mt
source-git-commit: 6250335d05c8e7799802fce26192896a7a6598fe

---


# Implementar Adobe Analytics manualmente (heredado)

Create an Adobe Analytics tool for deployment using [!UICONTROL Dynamic Tag Management]. Este procedimiento describe una implementación manual (heredada).

Para obtener información sobre la administración de la implementación automática, consulte [Agregar la herramienta Adobe Analytics](../../implement/c-implement-with-dtm/c-aa-tool/analytics-dtm.md#concept_FBA6679A0B79490F8296437F11E5E4F8).

Si desea cambiar una configuración de manual a automática, edite una herramienta y haga clic en **[!UICONTROL Activar configuración automática]**.

1. Descargar código Analytics de medición:
   1. In Analytics, click **[!UICONTROL Admin]** &gt; **[!UICONTROL Code Manager]**.
   1. Click **[!UICONTROL JavaScript (new)]** to download the code locally.
1. In [!UICONTROL Dynamic Tag Management], [create a web property](../../implement/c-implement-with-dtm/t-create-web-property.md#task_960467FBB7A54499AC228CB3AA3C4123).

   ![](assets/dtm-property.png)

   Una vez que haya creado la propiedad web, podrá editarla en la ficha [!UICONTROL Propiedades web] del [!UICONTROL Tablero]. No es necesario activar la propiedad web.

1. Agregue un herramienta Analytics a la propiedad:
   1. On the **[!UICONTROL Web Properties]** tab, click the property.
   1. On the **[!UICONTROL Overview]** tab, click **[!UICONTROL Add a Tool]**.
   1. From the **[!UICONTROL Tool Type]** menu, select **[!UICONTROL Adobe Analytics]**.

      ![](assets/dtm-add-analytics-tool.png)

   1. Configure los campos siguientes:

      | Elemento | Descripción |
      |---|---|
      | Tipo de herramienta | La solución de Experience Cloud, como Analytics, Target, Social, etc. |
      | Nombre de la herramienta | El nombre de esta herramienta. Este nombre se muestra en la ficha [!UICONTROL Información general] en [!UICONTROL Herramientas instaladas]. |
      | ID de cuenta de producción | Un número de su cuenta de producción para la recopilación de datos. Dynamic Tag Management instala automáticamente la cuenta correcta en el entorno de producción y ensayo. |
      | ID de cuenta de ensayo | Un número que se utiliza en el entorno de prueba o desarrollo. Una cuenta de ensayo permite separar los datos de prueba de los de producción. |

1. Haga clic en **[!UICONTROL Crear herramienta]**.

   La herramienta instalada se muestra en la ficha [!UICONTROL Información general].

1. To configure the code, click **[!UICONTROL Settings]** ![](assets/settings_gear.png).

   Se requiere, como mínimo, hacer clic en **[!UICONTROL Cookies]y configurar el servidor de seguimiento y el servidor de seguimiento SSL.**

1. Click **[!UICONTROL General]** and [insert the core AppMeasurement code](../../implement/c-implement-with-dtm/c-aa-tool/t-appmeasurement-code.md#task_068D72664B2743359A64ADB8692D3658).
1. Define a [page load rule](../../implement/c-implement-with-dtm/c-rules/t-rules-create.md#task_B7FB5ED415AF430C952265AC2835C0DB) to collect [!DNL Analytics]data.

   Ya está todo preparado para definir reglas para recopilar datos de análisis. Es posible que desee definir antes unos cuantos elementos de datos. Los elementos de datos le permiten extraer datos de la página que puede utilizar para configurar una regla. Para comenzar, puede definir una regla de carga de página que no disponga de condiciones para recopilar datos de [!DNL Analytics] en cada página.
1. [Agregue el código de encabezado y pie de página](../../implement/c-implement-with-dtm/c-headers-footers/t-header-footer-code.md#task_43C8DD699A514638B0620775C06423E5) en la ficha Insertar.

   Para el ensayo, puede dejar la opción de alojamiento predeterminada de Amazon. Puede cambiarla si es necesario antes de la implementación de producción.
1. (Optional) Click **[!UICONTROL Settings]** ![](assets/settings_gear.png) on the Options tab, and configure the Adobe Analytics code.

   >[!NOTE]
   >
   >The settings on the [!UICONTROL Adobe Analytics] page (General, Cookies, and so on) override settings in your `s_code`. Si esta configuración existe en `s_code`, no es necesario reiterarla aquí.

