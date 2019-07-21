---
description: Compruebe que la biblioteca de Dynamic Tag Management se está cargando correctamente en el sitio.
keywords: Implementación de Analytics; método de implementación; administración dinámica de etiquetas; dtm; code; page code; código de encabezado; código de pie de página; incrustar código; verificar código; verificar el código de encabezado; verificar código de pie de página; incrustar, ficha; embed
seo-description: Compruebe que la biblioteca de Dynamic Tag Management se está cargando correctamente en el sitio.
seo-title: Comprobación de código de Encabezado y de Pie de página
solution: Analytics
title: Comprobación de código de Encabezado y de Pie de página
topic: Desarrollador e implementación
uuid: d 395 a 417-0 c 61-41 a 6-a 124-d 2 f 400 f 4626 f
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Comprobación de código de Encabezado y de Pie de página

Compruebe que la biblioteca de Dynamic Tag Management se está cargando correctamente en el sitio.

1. Abra el sitio en el explorador.
1. Open the [!UICONTROL Developer Console] by right-clicking and choosing **[!UICONTROL Inspect Element]** &gt; **[!UICONTROL Console]**.
1. Press **[!UICONTROL Enter]**.

   If the code was properly installed, you will see *`true`* display in the console.

   Si el código no se instaló correctamente, se visualizará el error de referencia:

   `_satellite is not defined`

   Si recibe este error, asegúrese de que:

* You have included the full header code on every page of the site in the [!DNL HEAD] section, as close to the [!DNL <head><meta http-equiv="Content-Type" content="text/html; charset=UTF-8">] inicial como sea posible.
* No aparecen caracteres inesperados en el fragmento de código, como resultado de copiar y pegar de un documento con formato.

