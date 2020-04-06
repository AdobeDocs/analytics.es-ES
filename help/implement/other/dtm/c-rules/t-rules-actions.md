---
description: Configurar las acciones que desea que la condición active.
keywords: Dynamic Tag Management;rule;create rule;new rule;javascript/third party tags;set up actions for condition;add new script;non-sequential javascript;sequential javascript;non-sequential html
solution: Experience Cloud,Analytics,Target,Dynamic Tag Management
title: Configurar acciones para que la condición active
uuid: 2e892f0b-7261-41ee-b849-6e3054a38de0
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Configurar acciones para que la condición active

Configurar las acciones que desea que la condición active.

Después de configurar la condición, debe configurar las acciones que desea que la condición active. Estas acciones pueden incluir eventos de [!DNL Analytics], etiquetas de terceros y secuencias de comandos personalizadas. Este ejemplo describe cómo configurar secuencias de comandos y etiquetas de terceros.

Más allá de herramientas integradas como [!DNL Adobe Analytics] y Google Analytics, Dynamic Tag Management puede activar cualquier tipo de JavaScript o introducir HTML en su sitio, en páginas seleccionadas o en determinados escenarios.

Cada regla puede activar tantas secuencias de comandos o introducciones de HTML como desee.

>[!NOTE] Dado que la DTM le permite insertar código personalizado en su página, debe procurar no crear vulnerabilidades de scripts de sitios cruzados (XSS) (consulte la [guía de OWASP](https://www.owasp.org/index.php/Cross-site_Scripting_(XSS)) para obtener más información). Debe prestar especial atención cuando utilice elementos de datos en un script. Supongamos siempre que los valores del elemento de datos provienen de un origen que no es de confianza.

**Configurar acciones para que la condición active**

1. Haga clic en **[!UICONTROL JavaScript / Third Party Tags]** para agregar una nueva secuencia de comandos a la regla.

   ![](assets/scripts-actions.png)

1. Haga clic en **[!UICONTROL Add New Script]**.

   ![](assets/scripts-actions2.png)

1. Asigne un nombre a la secuencia de comandos.
1. Especifique cómo quiere que se active la secuencia de comandos, y pegue el contenido deseado en el área de texto. ![](assets/scripts-actions3.png)

1. Click **[!UICONTROL Save Code]**, and the script will be added to the queue for the rule. ![](assets/scripts-actions4.png)

