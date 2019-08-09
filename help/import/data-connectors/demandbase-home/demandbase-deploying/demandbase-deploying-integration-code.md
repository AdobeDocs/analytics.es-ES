---
description: Después de completar el asistente para integración, debe implementar el código de integración en el código de implementación de Adobe Analytics (s_ code).
seo-description: Después de completar el asistente para integración, debe implementar el código de integración en el código de implementación de Adobe Analytics (s_ code).
seo-title: Implementación del código de integración
title: Implementación del código de integración
uuid: b 3 fbda 0 b -4 ed 3-4967-84 ee -6 c 66564606 e 7
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e96de98b3176a05654fdf697210f992b0fd4adb1

---


# Implementación del código de integración{#deploying-the-integration-code}

Después de completar el asistente para integración, debe implementar el código de integración en el código de implementación de Adobe Analytics (s_ code).

>[!NOTE]
>
>Si ha utilizado Adobe tagmanager o Administración dinámica de etiquetas para implementar Adobe Analytics, puede agregar fácilmente el código de integración mediante una de estas herramientas.

1. Vaya a la ficha **[!UICONTROL Asistencia técnica]** y descargue y guarde `integration code v2_0_1` el recurso desde el área Recursos de la integración.

1. Si corresponde, realice las modificaciones necesarias en el código para obtener más información, consulte [Modificación del código de integración](../../demandbase-home/demandbase-deploying/demandbase-deploying-integration-code.md#concept-2e9e56282c9940d78e879aa45f70d855).
1. Incluya el módulo Integrate si no está presente en el código de implementación de Adobe Analytics. Para obtener más información, consulte [Inclusión del módulo Integrate](../../demandbase-home/demandbase-deploying/demandbase-including-integrate-module.md#concept-2cc81dff010a4da89b097a59476f8b6e).
1. Implemente el código con uno de los métodos siguientes:

   * Use Adobe tagmanager o Administración dinámica de etiquetas para añadir el código.
   * O bien, envíe el código al recurso organizativo responsable de actualizar el código de implementación de Adobe Analytics.

>[!IMPORTANT]
>
>Asegúrese de probar la implementación de esta integración en un entorno de desarrollo/ensayo antes de implementarlo en un entorno de producción.

