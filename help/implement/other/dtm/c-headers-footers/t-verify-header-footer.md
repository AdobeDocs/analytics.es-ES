---
description: Compruebe que la biblioteca de Dynamic Tag Management se está cargando correctamente en el sitio.
keywords: Implementación de Analytics;método de implementación;Dynamic Tag Management;dtm;código;código de página;código de encabezado;código de pie de página;incrustar código;comprobar código;comprobar código de encabezado;comprobar código de pie de página;pestaña insertar;insertar;incrustar
title: Comprobación de código de Encabezado y de Pie de página
topic-fix: Developer and implementation
uuid: d395a417-0c61-41a6-a124-d2f400f4626f
exl-id: bed44ba7-8e0e-49e2-bedc-fb1ba66e5b18
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '162'
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
