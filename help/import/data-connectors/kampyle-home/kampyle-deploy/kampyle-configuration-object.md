---
description: Después de completar el asistente de integración, debe implementar el objeto de configuración de integración en su propiedad web.
seo-description: Después de completar el asistente de integración, debe implementar el objeto de configuración de integración en su propiedad web.
seo-title: Implementar el objeto de configuración de integración
solution: Analytics
title: Implementar el objeto de configuración de integración
uuid: e 951 c 864-2914-4324-9 f 03-5069 d 4 f 75 d 99
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e96de98b3176a05654fdf697210f992b0fd4adb1

---


# Implementar el objeto de configuración de integración{#deploy-the-integration-configuration-object}

Después de completar el asistente de integración, debe implementar el objeto de configuración de integración en su propiedad web.

En muchos casos, la manera más sencilla de implementar el objeto de configuración de integración es incluirla con el código de implementación de Adobe Analytics.

>[!NOTE]
>
>Si utiliza Adobe tagmanager o Administración dinámica de etiquetas para implementar Adobe Analytics, puede agregar fácilmente el objeto de configuración de integración a través de esa herramienta.

1. Vaya a la ficha **[!UICONTROL Recursos]** &gt; **[!UICONTROL Asistencia técnica]** de la integración.
1. Descargue y guarde el recurso de código de integración **[!UICONTROL de Kampyle]** (JS). El código tiene un aspecto similar al siguiente:

   ```
   /* Kampyle:  Integration configuration settings */
     window.k_sc_param = { "version":1.1 }
   ```

1. Implemente el código con uno de los métodos siguientes:

       | ** Utiliza Adobe tagmanager o Administración dinámica de etiquetas.** | Utilice la interfaz de administración de etiquetas para agregar el código. |
    |—|—|
    | ** En todos los demás casos** | Envíe el código al recurso organizativo responsable de actualizar el código de implementación de Adobe Analytics. |
   
