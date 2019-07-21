---
description: Los analizadores de paquetes permiten ver los datos que se envían desde la implementación a los servidores de recopilación de datos de Adobe.
keywords: Implementación de Analytics
seo-description: Los analizadores de paquetes permiten ver los datos que se envían desde la implementación a los servidores de recopilación de datos de Adobe.
seo-title: Analizadores de paquetes
solution: Analytics
subtopic: Depurador
title: Analizadores de paquetes
topic: Desarrollador e implementación
uuid: 3597 c 23 a -1 c 72-46 e 6-909 d-f 861 cbeef 490
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Analizadores de paquetes

Los analizadores de paquetes permiten ver los datos que se envían desde la implementación a los servidores de recopilación de datos de Adobe.

Al igual que [!DNL DigitalPulse Debugger], un monitor de paquetes muestra qué parámetros de datos se están pasando en una solicitud de imagen. Sin embargo, los monitores de paquetes proporcionan más funciones:

* Ver solicitudes de imagen de seguimiento de enlaces personalizados
* Ver solicitudes de imagen usando métodos de implementación diferentes de JavaScript, como solicitudes de imagen preprogramadas o [!DNL Appmeasurement]

Para ver solicitudes de Analytics, filtre las solicitudes de salida mediante "b/ss".

En casos muy excepcionales, el depurador informará de una solicitud de imagen aunque en realidad no se haya realizado ninguna solicitud en nuestros servidores de procesamiento de [!DNL Analytics]. Usar un monitor de paquetes es una buena forma de asegurarse por completo de que se envía correctamente una solicitud de imagen específica.

Aunque Adobe no proporciona un monitor de paquetes oficial, hay una amplia variedad en Internet. A continuación se nombran varios monitores de paquetes que otros usuarios consideran útiles.

>[!NOTE]
>
>Estas listas no pretenden ser completas, sino más bien información sobre monitores utilizados con frecuencia. Si conoce un monitor de paquetes que ha utilizado satisfactoriamente y considera que es útil, no dude en proporcionar información sobre él usando el botón [!UICONTROL Comentario], que se encuentra a la derecha de esta ventana.

| Firefox | Internet Explorer | Chrome | Programas independientes |
|---|---|---|---|
| [Observe Point](https://www.observepoint.com/product#plugin) (visor de etiquetas) | [HttpWatch](https://www.httpwatch.com/) | [Observe Point](https://www.observepoint.com/product#plugin) (visor de etiquetas) | [Charles](https://www.charlesproxy.com/) |
| [HttpFox](https://addons.mozilla.org/en-US/firefox/addon/httpfox/) |  | [Herramientas para desarrolladores Chrome](https://code.google.com/chrome/devtools/docs/overview.html) | [Fiddler](https://www.fiddler2.com/fiddler2/) |
| [Tamper Data](https://addons.mozilla.org/en-us/firefox/addon/tamper-data/) |  | [Firebug Lite](https://chrome.google.com/webstore/detail/bmagokdooijbeehmkpknfglimnifench) | [Wireshark](https://www.wireshark.org/) |
| [HttpWatch](https://www.httpwatch.com/) |  |  |  |
| [Firebug](https://getfirebug.com/) |  |  |  |

>[!NOTE]
>
>Adobe NO admite ni solución problemas que pueda experimentar con estos monitores de paquetes. Consulte el sitio de origen del monitor de paquetes para obtener asistencia.

<!-- 

debugger_ns_binding.xml

 -->

Este error se produce porque la solicitud de imagen de seguimiento de vínculos está diseñada para permitir al explorador pasar a la página siguiente sin esperar la respuesta de los servidores de recopilación de datos de Adobe. 

La respuesta de Adobe a la solicitud de imagen es una imagen transparente vacía de 1x1 que no es importante para el contenido de la página. Si ve un elemento de línea en el monitor de paquetes de Adobe, bien con una respuesta **[!UICONTROL 200 OK]** o con una respuesta **NS_BINDING_ABORTED], los datos han llegado a nuestros servidores.[!UICONTROL ** No es necesario hacer que la página espere más.

Los monitores de paquetes integrados como complemento casi nunca ven la respuesta completa. Los monitores suelen ver la solicitud como anulada ya que no se recibió la respuesta completa. Estos monitores rara vez distinguen entre si lo que se anuló fue la solicitud o la respuesta. Un monitor de paquetes independiente normalmente tiene mensajes más detallados e informa del estado de manera más precisa. Por ejemplo, un usuario puede recibir un mensaje en *Charles* que indique “El cliente cerró la conexión antes de recibir la respuesta completa”. Esto significa que los datos llegaron a los servidores de Adobe, pero que el explorador pasó a la página siguiente antes de que se recibiera la imagen de 1x1 píxeles.

Si un detector de paquetes externo informa de que se ha anulado la solicitud de recopilación de datos, y no la respuesta, esto podría ser motivo de preocupación. Adobe [!DNL Customer Care] puede proporcionar ayuda para solucionar el problema.
