---
description: Cree una herramienta Adobe Analytics para la implementación mediante el uso de Dynamic Tag Management. Este procedimiento describe una implementación manual (heredada).
keywords: Dynamic Tag Management
solution: Experience Cloud,Analytics,Target,Dynamic Tag Management
title: Implementar Adobe Analytics manualmente (heredado)
uuid: d3ad2035-393d-4a77-81f6-e749ee717c09
translation-type: ht
source-git-commit: dfe8409b13fcf67eae6a0c404f83c1209f89ae12
workflow-type: ht
source-wordcount: '423'
ht-degree: 100%

---


# Implementar Adobe Analytics manualmente (heredado)

Cree una herramienta Adobe Analytics para la implementación mediante el uso de [!UICONTROL Dynamic Tag Management]. Este procedimiento describe una implementación manual (heredada).

Para obtener información sobre la administración de la implementación automática, consulte [Agregar la herramienta Adobe Analytics](/help/implement/other/dtm/c-aa-tool/analytics-dtm.md).

Si desea cambiar una configuración de manual a automática, edite una herramienta y haga clic en **[!UICONTROL Activar configuración automática]**.

1. Descargar código Analytics de medición:
   1. En Analytics, haga clic en **[!UICONTROL Administración]** > **[!UICONTROL Administrador de códigos]**.
   1. Haga clic en **[!UICONTROL JavaScript (nuevo)]** para descargar el código localmente.
1. En [!UICONTROL Dynamic Tag Management], [cree una propiedad web](/help/implement/other/dtm/t-create-web-property.md).

   ![](assets/dtm-property.png)

   Una vez que haya creado la propiedad web, podrá editarla en la ficha [!UICONTROL Propiedades web] del [!UICONTROL Tablero]. No es necesario activar la propiedad web.

1. Agregue un herramienta Analytics a la propiedad:
   1. En la pestaña **[!UICONTROL Propiedades web]**, haga clic en la propiedad.
   1. En la pestaña **[!UICONTROL Información general]**, haga clic en **[!UICONTROL Agregar una herramienta]**.
   1. En el menú **[!UICONTROL Tipo de herramienta]**, seleccione **[!UICONTROL Adobe Analytics]**.

      ![](assets/dtm-add-analytics-tool.png)

   1. Configure los campos siguientes:

      | Elemento | Descripción |
      |---|---|
      | Tipo de herramienta | La solución de Experience Cloud, como Analytics, Target, Social, etc. |
      | Nombre de la herramienta | El nombre de esta herramienta. Este nombre se muestra en la ficha [!UICONTROL Información general] en [!UICONTROL Herramientas instaladas]. |
      | ID de cuenta de producción | Un número de su cuenta de producción para la recopilación de datos. Dynamic Tag Management instala automáticamente la cuenta correcta en el entorno de producción y ensayo. |
      | ID de cuenta de ensayo | Un número que se utiliza en el entorno de prueba o desarrollo. Una cuenta de ensayo mantiene los datos de prueba separados de la producción. |

1. Haga clic en **[!UICONTROL Crear herramienta]**.

   La herramienta instalada se muestra en la ficha [!UICONTROL Información general].

1. Para configurar el código, haga clic en **[!UICONTROL Configuración]** ![](assets/settings_gear.png).

   Se requiere, como mínimo, hacer clic en **[!UICONTROL Cookies]** y configurar el servidor de seguimiento y el servidor de seguimiento SSL.

1. Haga clic en **[!UICONTROL General]** e [inserte el código principal de AppMeasurement](/help/implement/other/dtm/c-aa-tool/t-appmeasurement-code.md).
1. Defina una [regla de carga de página](/help/implement/other/dtm/c-rules/t-rules-create.md) para recopilar datos de [!DNL Analytics].

   Ya está todo preparado para definir reglas para recopilar datos de análisis. Es posible que desee definir antes unos cuantos elementos de datos. Los elementos de datos le permiten extraer datos de la página que puede utilizar para configurar una regla. Para comenzar, puede definir una regla de carga de página que no disponga de condiciones para recopilar datos de [!DNL Analytics] en cada página.
1. [Agregue el código de encabezado y pie de página](/help/implement/other/dtm/c-headers-footers/t-header-footer-code.md) en la ficha Insertar.

   Para el ensayo, puede dejar la opción de alojamiento predeterminada de Amazon. Puede cambiarla si es necesario antes de la implementación de producción.
1. (Opcional) Haga clic en **[!UICONTROL Configuración]**![](assets/settings_gear.png) en la pestaña Opciones y configure el código de Adobe Analytics.

   >[!NOTE]
   >
   >La configuración de la página [!UICONTROL Adobe Analytics] (General, Cookies, etc.) anula la configuración de `s_code`. Si esta configuración existe en `s_code`, no es necesario reiterarla aquí.

