---
description: El código de integración requiere que el módulo Integrate exista en la implementación de Adobe Analytics.
seo-description: El código de integración requiere que el módulo Integrate exista en la implementación de Adobe Analytics.
seo-title: Inclusión del módulo Integrate
title: Inclusión del módulo Integrate
uuid: e 574 f 3 db -49 fa -4 f 72-bbcf-fd 98540 d 3198
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5e22d080398d74df29b1f849258e6500168cd5aa

---


# Including the Integrate Module{#including-the-integrate-module}

El código de integración requiere que el módulo Integrate exista en la implementación de Adobe Analytics.

Si todavía no tiene el módulo Integrate como parte de su implementación, complete los pasos siguientes según el tipo de implementación que tenga.

## For AppMeasurement v1.0+ {#section-f28d090bf2404cabaae34cd9c66fc575}

1. Unzip the AppMeasurement zip file that you downloaded from **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]** &gt; **[!UICONTROL CodeManager]**.

1. Open the file named [!DNL AppMeasurement_Module_Integrate.js].
1. Copy and paste the contents of this file into your primary [!DNL AppMeasurement.js] file.

   >[!NOTE]
   >
   >Péguelo justo antes del comentario DO NOT ALTER ANYTHING BELOW THIS LINE dentro del archivo.

## For Legacy Code (H-code) {#section-bba8ad8c715e4f97883e7de3269f681a}

1. Descargue el módulo Integrate desde el área «Recursos» de la interfaz de usuario de Conectores de datos (en la ficha Asistencia).

   ![](assets/h_code.png)

1. Copy and paste the contents of that file into your [!DNL s_code] file.

   >[!NOTE]
   >
   >Péguelo justo antes del comentario DO NOT ALTER ANYTHING BELOW THIS LINE dentro del archivo.

