---
description: Compruebe que la biblioteca de Dynamic Tag Management se está cargando correctamente en el sitio.
keywords: Implementación de Analytics;método de implementación;Dynamic Tag Management;dtm;código;código de página;código de encabezado;código de pie de página;incrustar código;comprobar código;comprobar código de encabezado;comprobar código de pie de página;pestaña insertar;insertar;incrustar
seo-description: Compruebe que la biblioteca de Dynamic Tag Management se está cargando correctamente en el sitio.
seo-title: Comprobación de código de Encabezado y de Pie de página
solution: Analytics
title: Comprobación de código de Encabezado y de Pie de página
topic: Desarrollador e implementación
uuid: d395a417-0c61-41a6-a124-d2f400f4626f
translation-type: ht
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Comprobación de código de Encabezado y de Pie de página

Compruebe que la biblioteca de Dynamic Tag Management se está cargando correctamente en el sitio.

1. Abra el sitio en el explorador.
1. Abra la [!UICONTROL Consola del programador] haciendo clic con el botón derecho y seleccione **[!UICONTROL Inspeccionar elemento]** &gt; **[!UICONTROL Consola]**.
1. Pulse **[!UICONTROL Intro]**.

   Si el código se instaló correctamente, se mostrará *`true`* en la consola.

   Si el código no se instaló correctamente, se visualizará el error de referencia:

   `_satellite is not defined`

   Si recibe este error, asegúrese de que:

* Incluyó el código de Encabezado completo en cada una de las páginas del sitio en la sección [!DNL HEAD], lo más cerca posible de la etiqueta [!DNL <head><meta http-equiv="Content-Type" content="text/html; charset=UTF-8">].
* No aparecen caracteres inesperados en el fragmento de código, como resultado de copiar y pegar de un documento con formato.

