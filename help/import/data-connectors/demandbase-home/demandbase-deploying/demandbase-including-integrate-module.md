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
source-git-commit: e96de98b3176a05654fdf697210f992b0fd4adb1

---


# Inclusión del módulo Integrate{#including-the-integrate-module}

El código de integración requiere que el módulo Integrate exista en la implementación de Adobe Analytics.

Si todavía no tiene el módulo Integrate como parte de su implementación, complete los pasos siguientes según el tipo de implementación que tenga.

## Para appmeasurement v 1.0 + {#section-f28d090bf2404cabaae34cd9c66fc575}

1. Descomprima el archivo zip de appmeasurement que descargó desde **[!UICONTROL Analytics]** &gt; **[!UICONTROL Administración]** &gt; **[!UICONTROL codemanager]**.

1. Abra el archivo denominado [!DNL AppMeasurement_Module_Integrate.js].
1. Copie y pegue el contenido de este archivo en el [!DNL AppMeasurement.js] archivo principal.

   >[!NOTE]
   >
   >Péguelo justo antes del comentario DO NOT ALTER ANYTHING BELOW THIS LINE dentro del archivo.

## Para código preexistente (código H) {#section-bba8ad8c715e4f97883e7de3269f681a}

1. Descargue el módulo Integrate desde el área «Recursos» de la interfaz de usuario de Conectores de datos (en la ficha Asistencia).

   ![](assets/h_code.png)

1. Copie y pegue el contenido de dicho archivo en el [!DNL s_code] archivo.

   >[!NOTE]
   >
   >Péguelo justo antes del comentario DO NOT ALTER ANYTHING BELOW THIS LINE dentro del archivo.

