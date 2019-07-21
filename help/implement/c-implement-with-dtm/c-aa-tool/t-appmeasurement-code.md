---
description: Introduzca el código AppMeasurement si implementa de forma manual Dynamic Tag Management en Adobe Analytics.
keywords: Administración dinámica de etiquetas; cuentas vinculadas; vincular cuentas; editar código; appmeasurement; código de appmeasurement
seo-description: Introduzca el código AppMeasurement si implementa de forma manual Dynamic Tag Management en Adobe Analytics.
seo-title: Inserción del código principal de AppMeasurement
solution: Marketing Cloud, Analytics, Target, Administración dinámica de etiquetas
title: Inserción del código principal de AppMeasurement
uuid: 3 f 83 fbb 1-3 ed 5-4 e 45-888 a -0 a 183 aac 1 a 90
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Inserción del código principal de AppMeasurement

Introduzca el código AppMeasurement si implementa de forma manual Dynamic Tag Management en Adobe Analytics.

1. En la página de herramientas de [!DNL Adobe Analytics], expanda la sección **General** y, a continuación, haga clic en **[!UICONTROL Abrir editor]**.
1. Unzip the [!DNL AppMeasurement_JavaScript*.zip] file you downloaded in [deploy Adobe Analytics](../../../implement/c-implement-with-dtm/t-analytics-deploy.md#task_3A00639CADF14C9C844F962222077E4E).

   Si opta por una biblioteca personalizada, al abrir la ventana ya incluirá la versión de código más reciente. No es necesario descargar el zip desde Admin Console.
1. Open [!DNL AppMeasurement.js] in a text editor.
1. Copy and paste the contents into the **[!UICONTROL Edit Code]** window.

   ![](assets/edit-code.png)

1. Adobe recomienda añadir el siguiente código sobre *`Do Not Alter Anything Below This Line`*:

   ```
   var s_account="INSERT-RSID-HERE"
   var s=s_gi(s_account)
   ```

   >[!IMPORTANT]
   >
   >If you add this code, it is recommended that you also select the **[!UICONTROL Set report suites using custom code below]** checkbox in the overall library settings.

1. Click **[!UICONTROL Save and Close]**.

   Si está utilizando el módulo de medio, el módulo integrado o complementos de integración, también puede copiarlos en la sección de código. El código gestionado en Dynamic Tag Manager puede configurarse exactamente igual que el archivo JavaScript en una implementación típica.

