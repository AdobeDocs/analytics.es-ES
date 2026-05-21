---
title: Depurador heredado
description: Instale el depurador heredado. Este depurador inspecciona las etiquetas de recopilación de datos y de Analytics, Target, Advertising e Identity Service.
feature: Implementation Basics
exl-id: 8fd07285-f702-4770-81bd-5f856561f4a9
role: Admin, Developer, Leader, User
TQID: https://experienceleague.adobe.com/igbKBwN0NmXCPRi9Rc1UtG7Ty1ffpd0rwyWEOTWPWdk
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 157cc2bde1047063014aff39319d5cfaa1de9b5c
workflow-type: tm+mt
source-wordcount: 681
ht-degree: 75%

---

# Depurador heredado

>[!IMPORTANT]
>
>Esta herramienta de depuración ya no se mantiene. Adobe recomienda usar la [extensión de Chrome de Adobe CX Enterprise Debugger](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html?lang=es).

[!UICONTROL Legacy Debugger] inspecciona las etiquetas de la mayoría de los servicios empresariales de Adobe CX. El uso del depurador permite ver qué datos se envían a Adobe en cualquier página del sitio. Puede utilizar esta información para solucionar problemas o validar la implementación de su organización.

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

Si insiste en no utilizar la [extensión de Chrome](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html?lang=es), se puede utilizar el bookmarklet una versión anterior del depurador.

1. Haga clic en los tres puntos de la parte superior derecha y, a continuación, vaya a Marcadores > Administrador de marcadores. También puede pulsar `Ctrl` + `Shift` + `O` (Windows) o `Cmd` + `Shift` + `O` (Mac).
2. En la parte superior derecha del administrador de marcadores, haga clic en los tres puntos y luego en “Agregar nuevo marcador”.
3. En el campo Nombre, etiquete &quot;Debugger heredado&quot; y pegue el fragmento de código en el campo URL.
4. Use el administrador de marcadores para colocar el nuevo bookmarklet en la ubicación deseada.

#### Firefox

1. Haga clic en las tres líneas de la parte superior derecha y, a continuación, vaya a Biblioteca > Marcadores > Mostrar todos los marcadores. También puede pulsar `Ctrl` + `Shift` + `B` (Windows) o `Cmd` + `Shift` + `B` (Mac).
2. Haga clic en Organizar > Nuevo marcador.
3. En el campo Nombre, etiquete &quot;Depurador heredado&quot; y pegue el fragmento de código en el campo Ubicación. Los campos Etiquetas y Palabras clave no son obligatorios.
4. Utilice la ventana de la biblioteca para colocar el nuevo bookmarklet en la ubicación deseada.

#### Edge

Edge no tiene la capacidad de crear manualmente un bookmarklet, pero se puede editar una dirección URL de marcador para que sea un bookmarklet.

1. Haga clic en el icono de estrella en la parte derecha del campo URL para marcar la página actual.
2. Asigne un nombre al marcador &quot;Legacy Debugger&quot; y guárdelo en la ubicación deseada.
3. Haga clic en el icono de estrella con líneas para abrir la barra Favoritos.
4. Haga clic con el botón derecho en el marcador recién creado y seleccione “Editar URL”.
5. Pegue el fragmento de código en el campo de texto y, a continuación, pulse Intro.

#### Safari

Safari no tiene la capacidad de crear manualmente un bookmarklet, pero se puede editar una dirección URL de marcador para que sea un bookmarklet.

1. Haga clic en el icono Compartir en la parte superior derecha, que abre una ventana modal de marcador.
2. Asigne un nombre al marcador &quot;Legacy Debugger&quot; y guárdelo en la ubicación deseada.
3. Haga clic en Marcadores > Editar marcadores y busque el marcador recién creado.
4. Haga clic con el botón derecho (ratón) > Editar dirección y, a continuación, pegue el fragmento de código en el campo de texto.

## Uso del depurador antiguo

Navegue hasta la página deseada en el sitio y haga clic en el bookmarklet. Aparece una ventana emergente que muestra los datos enviados a Adobe.

>[!NOTE]
>
>Algunos complementos y bloqueadores de ventanas emergentes que bloquean anuncios pueden interferir con la carga de la ventana del depurador. Compruebe si hay ventanas emergentes bloqueadas en el explorador y déjelas para que el depurador funcione correctamente.

El depurador tiene varias opciones disponibles, que personalizan el modo en que se muestran los datos. Ninguna de estas opciones afecta a la recopilación de datos.

* **[!UICONTROL Productos de Experience Cloud mostrados]**: muestra u oculta solicitudes de imagen para cada producto de CX Enterprise correspondiente.
* **[!UICONTROL Descodificación de URL]**: La URL descodifica la solicitud de imagen para que coincida con lo que se muestra en los informes. Adobe recomienda dejar esta casilla marcada.
* **[!UICONTROL Actualización automática]**: actualiza automáticamente la ventana emergente cada pocos segundos para buscar más solicitudes de imagen en la página. Si necesita copiar/pegar contenido en el depurador, deshabilite la actualización automática para que la selección se mantenga.
* **[!UICONTROL Formato sencillo]**: cambia el formato de presentación entre etiquetas útiles y cadenas de consulta sin procesar en una solicitud de imagen. Consulte [Parámetros de consulta de recopilación de datos](query-parameters.md) para obtener más información.

Para guardar las opciones de visualización predeterminadas del depurador, haga clic con el botón derecho en el vínculo “Adobe Debugger” en la esquina superior derecha y copie la dirección del vínculo. Edite el bookmarklet del depurador actual y pegue el fragmento de código actualizado en el campo URL.
