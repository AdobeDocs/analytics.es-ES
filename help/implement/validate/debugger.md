---
title: Adobe Experience Cloud Debugger antiguo
description: Instale una versión anterior de Adobe Experience Cloud Debugger. Este depurador inspecciona las etiquetas de Analytics, Target, Advertising Cloud, Identity Service y Launch.
exl-id: 8fd07285-f702-4770-81bd-5f856561f4a9
source-git-commit: f3eb3c024a80d0b65729929960173f8b3a4267b0
workflow-type: tm+mt
source-wordcount: '688'
ht-degree: 98%

---

# Adobe Experience Cloud Debugger antiguo

>[!IMPORTANT]
>
>Esta herramienta de depuración ya no se mantiene. Adobe recomienda usar la extensión [Adobe Experience Cloud Debugger](https://docs.adobe.com/content/help/es-ES/debugger/using/experience-cloud-debugger.html) para Chrome.

Las versiones anteriores de [!UICONTROL Debugger] inspeccionan las etiquetas de la mayoría de los servicios de Adobe Experience Cloud. El uso del depurador permite ver qué datos se envían a Adobe en cualquier página del sitio. Puede utilizar esta información para solucionar problemas o validar la implementación de su organización.

## Instalación de versiones anteriores de Debugger

Cree un bookmarklet de JavaScript para instalar el depurador.

### Paso 1: copiar el código de bookmarklet.

Copie el código en el portapapeles:

```JavaScript
javascript:void(window.open("","stats_debugger","width=800,height=800,location=0,menubar=0,status=1,toolbar=0,resizable=1,scrollbars=1").document.write("<script language=\"JavaScript\" id=dbg src=\"https://www.adobetag.com/d1/digitalpulsedebugger/live/DPD.js\"></"+"script>"+"<script language=\"JavaScript\">window.focus();</script>"));
```

### Paso 2: pegar el código de bookmarklet en un marcador

Cada navegador tiene diferentes formas de administrar los marcadores, pero el concepto es el mismo. Se crea un marcador con el nombre deseado y el código del bookmarklet como dirección URL.

#### Chrome

Si insiste en no utilizar la [extensión de Chrome](https://docs.adobe.com/content/help/en/debugger/using/experience-cloud-debugger.html), se puede utilizar el bookmarklet una versión anterior del depurador.

1. Haga clic en los tres puntos de la parte superior derecha y, a continuación, vaya a Marcadores > Administrador de marcadores. También puede pulsar `Ctrl` + `Shift` + `O` (Windows) o `Cmd` + `Shift` + `O` (Mac).
2. En la parte superior derecha del administrador de marcadores, haga clic en los tres puntos y luego en “Agregar nuevo marcador”.
3. En el campo Nombre, etiquete “Adobe Experience Cloud Debugger” y pegue el fragmento de código en el campo URL.
4. Use el administrador de marcadores para colocar el nuevo bookmarklet en la ubicación deseada.

#### Firefox

1. Haga clic en las tres líneas de la parte superior derecha y, a continuación, vaya a Biblioteca > Marcadores > Mostrar todos los marcadores. También puede pulsar `Ctrl` + `Shift` + `B` (Windows) o `Cmd` + `Shift` + `B` (Mac).
2. Haga clic en Organizar > Nuevo marcador.
3. En el campo Nombre, etiquete “Adobe Experience Cloud Debugger” y pegue el fragmento de código en el campo Ubicación. Los campos Etiquetas y Palabras clave no son obligatorios.
4. Utilice la ventana de la biblioteca para colocar el nuevo bookmarklet en la ubicación deseada.

#### Edge

Edge no tiene la capacidad de crear manualmente un bookmarklet, pero se puede editar una dirección URL de marcador para que sea un bookmarklet.

1. Haga clic en el icono de estrella en la parte derecha del campo URL para marcar la página actual.
2. Asigne un nombre al marcador “Adobe Experience Cloud Debugger” y guárdelo en la ubicación deseada.
3. Haga clic en el icono de estrella con líneas para abrir la barra Favoritos.
4. Haga clic con el botón derecho en el marcador recién creado y seleccione “Editar URL”.
5. Pegue el fragmento de código en el campo de texto y, a continuación, pulse Intro.

#### Safari

Safari no tiene la capacidad de crear manualmente un bookmarklet, pero se puede editar una dirección URL de marcador para que sea un bookmarklet.

1. Haga clic en el icono Compartir en la parte superior derecha, que abre una ventana modal de marcador.
2. Asigne un nombre al marcador “Adobe Experience Cloud Debugger” y guárdelo en la ubicación deseada.
3. Haga clic en Marcadores > Editar marcadores y busque el marcador recién creado.
4. Haga clic con el botón derecho (ratón) > Editar dirección y, a continuación, pegue el fragmento de código en el campo de texto.

## Uso del depurador antiguo

Navegue hasta la página deseada en el sitio y haga clic en el bookmarklet. Aparece una ventana emergente que muestra los datos enviados a Adobe.

>[!NOTE]
>
>Algunos complementos y bloqueadores de ventanas emergentes que bloquean anuncios pueden interferir con la carga de la ventana del depurador. Compruebe si hay ventanas emergentes bloqueadas en el explorador y déjelas para que el depurador funcione correctamente.

El depurador tiene varias opciones disponibles, que personalizan el modo en que se muestran los datos. Ninguna de estas opciones afecta a la recopilación de datos.

* **Productos de Experience Cloud mostrados:** muestra u oculta solicitudes de imagen para cada producto de Experience Cloud correspondiente.
* **Descodificación de URL:** la dirección URL descodifica la solicitud de imagen para que coincida con lo que se muestra en los informes. Adobe recomienda dejar esta casilla marcada.
* **Actualización automática:** actualiza automáticamente la ventana emergente cada pocos segundos para buscar más solicitudes de imagen en la página. Si necesita copiar/pegar contenido en el depurador, deshabilite la actualización automática para que la selección se mantenga.
* **Formato sencillo:** cambia el formato de visualización entre etiquetas útiles y cadenas de consulta sin procesar en una solicitud de imagen. Consulte [Parámetros de consulta de recopilación de datos](query-parameters.md) para obtener más información.

Para guardar las opciones de visualización predeterminadas del depurador, haga clic con el botón derecho en el vínculo “Adobe Debugger” en la esquina superior derecha y copie la dirección del vínculo. Edite el bookmarklet del depurador actual y pegue el fragmento de código actualizado en el campo URL.
