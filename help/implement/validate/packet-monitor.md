---
title: Analizadores de paquetes
description: Los analizadores de paquetes permiten ver los datos que se envían desde la implementación a los servidores de recopilación de datos de Adobe.
keywords: packet sniffer, http status, 200, 302, charles
translation-type: tm+mt
source-git-commit: b359582fe8ab6ee04bb478825d9989d850390f96
workflow-type: tm+mt
source-wordcount: '659'
ht-degree: 58%

---


# Analizadores de paquetes

Los analizadores de paquetes permiten ver los datos que se envían desde la implementación a los servidores de recopilación de datos de Adobe.

Al igual que Adobe Experience Cloud Debugger, un monitor de paquetes muestra qué parámetros de datos se pasan en una solicitud de imagen. Sin embargo, los monitores de paquetes proporcionan más funciones:

* Ver solicitudes de imagen de seguimiento de enlaces personalizados
* Ver solicitudes de imagen usando métodos de implementación diferentes de JavaScript, como solicitudes de imagen preprogramadas o [!DNL Appmeasurement]

Para ver solicitudes de Analytics, filtre las solicitudes de salida mediante &quot;b/ss&quot;.

En casos muy excepcionales, el depurador informará de una solicitud de imagen aunque en realidad no se haya realizado ninguna solicitud en nuestros servidores de procesamiento de [!DNL Analytics]. Usar un monitor de paquetes es una buena forma de asegurarse por completo de que se envía correctamente una solicitud de imagen específica.

Aunque Adobe no proporciona un monitor de paquetes oficial, hay una amplia variedad en Internet. A continuación se nombran varios monitores de paquetes que otros usuarios consideran útiles.

>[!TIP]
>
>Estas listas no son completas, solo ofrecen información sobre monitores usados con frecuencia.

| Firefox | Internet Explorer | Chrome | Programas independientes |
|---|---|---|---|
| [Observe Point](https://www.observepoint.com/product#plugin) (visor de etiquetas) | [HttpWatch](https://www.httpwatch.com/) | [Observe Point](https://www.observepoint.com/product#plugin) (visor de etiquetas) | [Charles](https://www.charlesproxy.com/) |
| [HttpFox](https://addons.thunderbird.net/en-us/firefox/addon/httpfox/) |  | [Herramientas para desarrolladores Chrome](https://code.google.com/chrome/devtools/docs/overview.html) | [Fiddler](https://www.fiddler2.com/fiddler2/) |
| [Tamper Data](https://addons.mozilla.org/en-US/firefox/addon/tamper-data-for-ff-quantum/) |  | [Firebug Lite](https://chrome.google.com/webstore/detail/bmagokdooijbeehmkpknfglimnifench) | [Wireshark](https://www.wireshark.org/) |
| [HttpWatch](https://www.httpwatch.com/) |  |  |  |
| [Firebug](https://getfirebug.com/) |  |  |  |

>[!NOTE]
>
>Adobe NO admite ni soluciona ningún problema que experimente con estos monitores de paquetes. Consulte el sitio de origen del monitor de paquetes para obtener ayuda.

## Códigos de estado de respuesta HTTP habituales

Cuando AppMeasurement envía datos a los servidores de recopilación de datos de Adobe, los servidores responden con un código de estado de respuesta.

* **200 OK**: La respuesta más común de los servidores de recopilación de datos. La solicitud de imagen se recibió correctamente y se devolvió una imagen transparente.
* **302 ENCONTRADOS**: Existen dos razones posibles para recibir esta respuesta:
   * Primera solicitud de imagen de un visitante: Se produce una redirección si un usuario visita el sitio por primera vez. Esta redirección es para obtener una cookie de visitante. No afecta a la recopilación de datos.
   * Integración entre Comscore y Adobe: Si su organización utiliza una integración de Comscore/Analytics, cada solicitud de imagen siempre resulta en una respuesta 302.
* **404 NO ENCONTRADO**: Esta respuesta significa que no se encontró la solicitud de imagen y que los datos no se envían a los servidores de recopilación de datos de Adobe. Esta respuesta también es posible cuando las solicitudes de imagen codificadas no tienen el formato correcto. Póngase en contacto con el individuo o equipo que implementó Analytics para resolver este problema.

## NS_BINDING_ABORTED en códigos de respuesta

Este mensaje se produce porque la solicitud de imagen de seguimiento de vínculos está diseñada para permitir que el explorador continúe con la página siguiente antes de esperar una respuesta de los servidores de recopilación de datos de Adobe.

La respuesta de Adobe a la solicitud de imagen es una imagen transparente vacía de 1x1 que no es importante para el contenido de la página. If you see a line item in your packet monitor from Adobe, either with a **[!UICONTROL 200 OK]** response or an **[!UICONTROL NS_BINDING_ABORTED]** response, the data has reached Adobe&#39;s servers. No es necesario hacer que la página espere más.

Los monitores de paquetes integrados como complemento casi nunca ven la respuesta completa. Los monitores suelen ver la solicitud como anulada ya que no se recibió la respuesta completa. Estos monitores rara vez distinguen entre si lo que se anuló fue la solicitud o la respuesta. Un monitor de paquetes independiente normalmente tiene mensajes más detallados e informa del estado de manera más precisa. Por ejemplo, un usuario puede recibir un mensaje en *Charles* que indique “El cliente cerró la conexión antes de recibir la respuesta completa”. Esto significa que los datos llegaron a los servidores de Adobe, pero que el explorador pasó a la página siguiente antes de que se recibiera la imagen de 1x1 píxeles.

Si un monitor de paquetes externo informa de que se ha anulado la solicitud de recopilación de datos, en lugar de la respuesta, esto es motivo de preocupación. Adobe [!DNL Customer Care] puede proporcionar ayuda para solucionar el problema.
