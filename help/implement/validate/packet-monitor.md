---
title: Analizadores de paquetes
description: Los analizadores de paquetes permiten ver los datos que se envían desde la implementación a los servidores de recopilación de datos de Adobe.
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Analizadores de paquetes

Los analizadores de paquetes permiten ver los datos que se envían desde la implementación a los servidores de recopilación de datos de Adobe.

Al igual que Adobe Experience Cloud Debugger, un monitor de paquetes muestra qué parámetros de datos se pasan en una solicitud de imagen. Sin embargo, los monitores de paquetes proporcionan más funciones:

* Ver solicitudes de imagen de seguimiento de enlaces personalizados
* Ver solicitudes de imagen usando métodos de implementación diferentes de JavaScript, como solicitudes de imagen preprogramadas o [!DNL Appmeasurement]

Para ver solicitudes de Analytics, filtre las solicitudes de salida mediante &quot;b/ss&quot;.

En casos muy excepcionales, el depurador informará de una solicitud de imagen aunque en realidad no se haya realizado ninguna solicitud en nuestros servidores de procesamiento de [!DNL Analytics]. El uso de un monitor de paquetes es una buena manera de estar 100% seguro de que una solicitud de imagen específica se está activando correctamente.

Aunque Adobe no proporciona un monitor de paquetes oficial, hay una amplia gama de ellos en Internet. Los siguientes son algunos monitores de paquetes que otros han encontrado útiles.

>[!NOTE] Estas listas no son completas, solo ofrecen información sobre monitores usados con frecuencia. Si dispone de un monitor de paquetes que utiliza correctamente y le resulta útil, no dude en proporcionar comentarios con el [!UICONTROL Feedback] botón de la derecha de esta ventana.

| Firefox | Internet Explorer | Chrome | Programas independientes |
|---|---|---|---|
| [Observe Point](https://www.observepoint.com/product#plugin) (visor de etiquetas) | [HttpWatch](https://www.httpwatch.com/) | [Observe Point](https://www.observepoint.com/product#plugin) (visor de etiquetas) | [Charles](https://www.charlesproxy.com/) |
| [HttpFox](https://addons.mozilla.org/en-US/firefox/addon/httpfox/) |  | [Herramientas para desarrolladores Chrome](https://code.google.com/chrome/devtools/docs/overview.html) | [Fiddler](https://www.fiddler2.com/fiddler2/) |
| [Tamper datos](https://addons.mozilla.org/en-us/firefox/addon/tamper-data/) |  | [Firebug Lite](https://chrome.google.com/webstore/detail/bmagokdooijbeehmkpknfglimnifench) | [Wireshark](https://www.wireshark.org/) |
| [HttpWatch](https://www.httpwatch.com/) |  |  |  |
| [Firebug](https://getfirebug.com/) |  |  |  |

>[!NOTE] Adobe NO ofrece soporte ni solución de problemas en relación con ninguna incidencia que pueda sufrir con estos monitores de paquetes. Consulte el sitio de origen del monitor de paquetes para obtener asistencia.

## NS_BINDING_ABORTED en códigos de respuesta

Este error se produce porque la solicitud de imagen de seguimiento de vínculos está diseñada para permitir al explorador pasar a la página siguiente sin esperar la respuesta de los servidores de recopilación de datos de Adobe.

La respuesta de Adobe a la solicitud de imagen es una imagen transparente vacía de 1x1 que no es importante para el contenido de la página. Si ve un elemento de línea en el monitor de paquetes de Adobe, bien con una respuesta **[!UICONTROL 200 OK]** o con una respuesta **[!UICONTROL NS_BINDING_ABORTED]**, los datos han llegado a nuestros servidores. Ya no es necesario hacer que la página espere más.

Los monitores de paquetes integrados como complemento rara vez ven la respuesta completa. Los monitores suelen ver la solicitud como anulada ya que no se recibió la respuesta completa. Estos monitores rara vez distinguen entre si se anuló la solicitud o la respuesta. Un monitor de paquetes independiente generalmente tiene mensajes más detallados e informa del estado con mayor precisión. Por ejemplo, un usuario puede recibir un mensaje en *Charles* que diga &quot;El cliente cerró la conexión antes de recibir la respuesta completa&quot;. Esto significa que los datos llegaron a nuestros servidores, solo que el navegador pasó a la página siguiente antes de recibir el píxel 1x1.

Si un detector de paquetes externo tiene el sistema de informes de que se ha anulado la solicitud de recopilación de datos, en lugar de la respuesta, esto es motivo de preocupación. Adobe [!DNL Customer Care] puede proporcionar ayuda para solucionar el problema.
