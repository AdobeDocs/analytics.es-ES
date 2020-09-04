---
description: Compruebe que la biblioteca de Dynamic Tag Management se está cargando correctamente en el sitio.
keywords: Analytics Implementation;implementation method;dynamic tag management;dtm;code;page code;header code;footer code;embed code;verify code;verify header code;verify footer code;embed tab;embed
title: Comprobación de código de Encabezado y de Pie de página
topic: Developer and implementation
uuid: d395a417-0c61-41a6-a124-d2f400f4626f
translation-type: tm+mt
source-git-commit: 82cf5ddfd4d18af09c2dbedba20514e4b643a94b
workflow-type: tm+mt
source-wordcount: '134'
ht-degree: 100%

---


# Comprobación de código de Encabezado y de Pie de página

Compruebe que la biblioteca de Dynamic Tag Management se está cargando correctamente en el sitio.

1. Abra el sitio en el explorador.
1. Abra la [!UICONTROL Consola del programador] haciendo clic con el botón derecho y seleccione **[!UICONTROL Inspeccionar elemento]** > **[!UICONTROL Consola]**.
1. Pulse **[!UICONTROL Intro]**.

   Si el código se instaló correctamente, se mostrará *`true`* en la consola.

   Si el código no se instaló correctamente, se visualizará el error de referencia:

   `_satellite is not defined`

   Si recibe este error, asegúrese de que:

* Incluyó el código de Encabezado completo en cada una de las páginas del sitio en la sección [!DNL HEAD], lo más cerca posible de la etiqueta `<head>` como sea posible.
* No aparecen caracteres inesperados en el fragmento de código, como resultado de copiar y pegar de un documento con formato.

