---
description: Instale el depurador heredado de Adobe Experience Cloud. Este depurador inspecciona las etiquetas de Analytics, Target, Advertising Cloud, Identity Service, DTM e Launch.
seo-description: Instale el depurador heredado de Adobe Experience Cloud. Este depurador inspecciona las etiquetas de Analytics, Target, Advertising Cloud, Identity Service, DTM e Launch.
seo-title: Depurador heredado de Adobe Experience Cloud
title: Depurador heredado de Adobe Experience Cloud
translation-type: tm+mt
source-git-commit: 2ea071c4d4f675c74770396610219d405a07a0e1

---


# Depurador heredado de Adobe Experience Cloud

> [!IMPORTANT] Esta herramienta de depuración ya no se mantiene. Adobe recomienda usar la extensión [Adobe Experience Cloud Debugger Chrome Extension](https://docs.adobe.com/content/help/en/debugger/using/experience-cloud-debugger.html).

El depurador [!UICONTROL heredado] inspecciona las etiquetas de la mayoría de los servicios de Adobe Experience Cloud. El uso del depurador permite ver qué datos se envían a Adobe en cualquier página del sitio. Puede utilizar esta información para solucionar problemas o validar la implementación de su organización.

## Instalación del depurador heredado

Cree un bookmarklet JavaScript para instalar el depurador.

### Paso 1: Copiar código de bookmarklet

Copie el siguiente código en el portapapeles:

```JavaScript
javascript:void(window.open("","stats_debugger","width=800,height=800,location=0,menubar=0,status=1,toolbar=0,resizable=1,scrollbars=1").document.write("<script language=\"JavaScript\" id=dbg src=\"https://www.adobetag.com/d1/digitalpulsedebugger/live/DPD.js\"></"+"script>"+"<script language=\"JavaScript\">window.focus();</script>"));
```

### Paso 2: Pegar código de bookmarklet en un marcador

Cada navegador tiene diferentes formas de administrar marcadores, pero el concepto es el mismo. Se crea un marcador con el nombre deseado y el código del bookmarklet como dirección URL.

#### Chrome

Si insiste en no utilizar la extensión [de](https://docs.adobe.com/content/help/en/debugger/using/experience-cloud-debugger.html)Chrome, se puede utilizar el bookmarklet del depurador heredado.

1. Haga clic en los tres puntos de la parte superior derecha y, a continuación, vaya a Marcadores &gt; Administrador de marcadores. También puede pulsar `Ctrl` + `Shift` + `O` (Windows) o `Cmd` + `Shift` + `O` (Mac).
2. En la parte superior derecha del administrador de marcadores, haga clic en los tres puntos y luego en 'Agregar nuevo marcador'.
3. En el campo Nombre, etiquete "Adobe Experience Cloud Debugger" y pegue el fragmento de código en el campo URL.
4. Use el administrador de marcadores para colocar el nuevo bookmarklet en la ubicación deseada.

#### Firefox

1. Haga clic en las tres líneas de la parte superior derecha y, a continuación, vaya a Biblioteca &gt; Marcadores &gt; Mostrar todos los marcadores. También puede pulsar `Ctrl` + `Shift` + `B` (Windows) o `Cmd` + `Shift` + `B` (Mac).
2. Haga clic en Organizar &gt; Nuevo marcador.
3. En el campo Nombre, etiquete "Adobe Experience Cloud Debugger" y pegue el fragmento de código en el campo Ubicación. Los campos Etiquetas y Palabras clave no son obligatorios.
4. Utilice la ventana de la biblioteca para colocar el nuevo bookmarklet en la ubicación deseada.

#### Edge

Edge no tiene la capacidad de crear manualmente un bookmarklet, pero se puede editar una dirección URL de marcador.

1. Haga clic en el icono de estrella en la parte derecha del campo URL para marcar la página actual.
2. Name the bookmark "Adobe Experience Cloud Debugger", and save it in the desired location.
3. Click the star icon with lines to open the Favorites bar.
4. Right click the newly created bookmark, the select 'Edit URL'.
5. Paste the code snippet in the text field, then hit Enter.

#### Safari

Safari does not have the ability to manually create a bookmarklet, but a bookmark URL can be edited.

1. Click the Share icon in the top right, which opens a bookmark modal window.
2. Name the bookmark "Adobe Experience Cloud Debugger", and save it in the desired location.
3. Click Bookmarks &gt; Edit Bookmarks, and locate the newly created bookmark.
4. Right click &gt; Edit Address, then paste the code snippet into text field.

## Using the legacy debugger

To use the debugger, navigate to the desired page on your site, then click the bookmarklet. A pop-up window appears, showing data sent to Adobe.

> [!NOTE] Certain ad-blocking plug-ins and pop-up blockers can interfere with the loading of the debugger window. Check for blocked pop-ups in your browser, and allow them so the debugger can work correctly.

The debugger has several options available, all of which customize how data is displayed. Ninguna de estas opciones afecta a la recopilación de datos.

* **** Productos de Experience Cloud mostrados: Muestra u oculta solicitudes de imagen para cada producto de Experience Cloud correspondiente.
* **** Descodificación de URL: La dirección URL descodifica la solicitud de imagen para que coincida con lo que se muestra en los informes. Adobe recomienda dejar esta casilla marcada.
* **** Actualización automática: Actualiza automáticamente la ventana emergente cada pocos segundos para buscar más solicitudes de imagen en la página. Si necesita copiar/pegar contenido en el depurador, deshabilite la actualización automática para que la selección se mantenga.
* **** Formato sencillo: Cambia el formato de visualización entre etiquetas útiles y cadenas de consulta sin procesar en una solicitud de imagen. Consulte Parámetros [de consulta de recopilación de](../js-implementation/data-collection/query-parameters.md) datos para obtener más información.

Para guardar las opciones de visualización predeterminadas para el depurador, haga clic con el botón secundario en el vínculo 'Adobe Debugger' en la esquina superior derecha y copie la dirección del vínculo. Edite el bookmarklet del depurador actual y pegue el fragmento de código actualizado en el campo URL.
