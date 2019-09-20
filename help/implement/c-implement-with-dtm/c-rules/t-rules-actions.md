---
description: Configurar las acciones que desea que la condición active.
keywords: Administración dinámica de etiquetas;regla;crear regla;nueva regla;etiquetas de javascript/terceros;configurar acciones para la condición;agregar nueva secuencia de comandos;javascript no secuencial;javascript secuencial;html no secuencial
seo-description: Configurar las acciones que desea que la condición active.
seo-title: Configurar acciones para que la condición active
solution: Experience Cloud,Analytics,Target,Administración dinámica de etiquetas
title: Configurar acciones para que la condición active
uuid: 2e892f0b-7261-41ee-b849-6e3054a38de0
translation-type: tm+mt
source-git-commit: e060fb745d611f37f28708b3fe103c1191aa483b

---


# Configurar acciones para que la condición active

Configurar las acciones que desea que la condición active.

Una vez configurada la condición, debe configurar las acciones que desea que la condición active. Estas acciones pueden incluir eventos de [!DNL Analytics], etiquetas de terceros y secuencias de comandos personalizadas. Este ejemplo describe cómo configurar secuencias de comandos y etiquetas de terceros.

Más allá de herramientas integradas como [!DNL Adobe Analytics] y Google Analytics, Dynamic Tag Management puede activar cualquier tipo de JavaScript o introducir HTML en su sitio, en páginas seleccionadas o en determinados escenarios.

Cada regla puede activar tantas secuencias de comandos o introducciones de HTML como desee.

>[!NOTE]
>
>Because DTM allows you to inject custom code into your page, please take care not to create cross-site scripting (XSS) vulnerabilities (see [OWASP’s guide](https://www.owasp.org/index.php/Cross-site_Scripting_(XSS)) for more info). Debe prestar especial atención cuando utilice elementos de datos en un script. Tenga en cuenta que los valores de elementos de datos no siempre provienen de una fuente de confianza.

**Configurar acciones para que la condición active**

1. Click **[!UICONTROL JavaScript / Third Party Tags]** to add a new script to your rule.

   ![](assets/scripts-actions.png)

1. Haga clic en **[!UICONTROL Agregar nuevo script]**.

   ![](assets/scripts-actions2.png)

1. Asigne un nombre a la secuencia de comandos.
1. Especifique cómo quiere que se active la secuencia de comandos, y pegue el contenido deseado en el área de texto. ![](assets/scripts-actions3.png)

1. Click **[!UICONTROL Save Code]**, and the script will be added to the queue for the rule. ![](assets/scripts-actions4.png)

