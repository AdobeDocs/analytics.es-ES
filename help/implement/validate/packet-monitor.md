---
title: Analizadores de paquetes
description: Los analizadores de paquetes permiten ver los datos que se envían desde la implementación a los servidores de recopilación de datos de Adobe.
keywords: detector de paquetes, estado http, 200, 302, charles
exl-id: db077293-f72c-4933-8a30-f1e1963f332e
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '664'
ht-degree: 100%

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
| [Tamper Data](https://addons.mozilla.org/es-ES/firefox/addon/tamper-data-for-ff-quantum/) |  | [Firebug Lite](https://chrome.google.com/webstore/detail/bmagokdooijbeehmkpknfglimnifench) | [Wireshark](https://www.wireshark.org/) |
| [HttpWatch](https://www.httpwatch.com/) |  |  |  |
| [Firebug](https://getfirebug.com/) |  |  |  |

>[!NOTE]
>
>Adobe NO ofrece soporte ni solución de problemas en relación con ninguna incidencia que pueda sufrir con estos monitores de paquetes. Consulte el sitio de origen del monitor de paquetes para obtener asistencia.

## Códigos de estado de respuesta HTTP habituales

Cuando AppMeasurement envía datos a los servidores de recopilación de datos de Adobe, los servidores responden con un código de estado de respuesta.

* **200 OK**: La respuesta más común de los servidores de recopilación de datos. La solicitud de imagen se recibió correctamente y se devolvió una imagen transparente.
* **302 FOUND**: Hay dos razones posibles para recibir esta respuesta:
   * La primera solicitud de imagen de un visitante: Se produce una redirección si un usuario visita el sitio por primera vez. Este redireccionamiento es para obtener una cookie de visitante. No afecta a la recopilación de datos.
   * Integración entre Comscore y Adobe: Si su organización utiliza una integración de Comscore/Analytics, cada solicitud de imagen siempre resultará en una respuesta 302.
* **404 NOT FOUND**: Esta respuesta significa que la solicitud de imagen no se ha encontrado y que los datos no se envían a los servidores de recopilación de datos de Adobe. Esta respuesta también es posible cuando las solicitudes de imagen codificadas no tienen un formato correcto. Colabore con el individuo o equipo que implementó Analytics para resolver este problema.

## NS_BINDING_ABORTED en códigos de respuesta

Este mensaje se produce porque la solicitud de imagen de seguimiento de vínculos está diseñada para permitir al explorador pasar a la página siguiente sin esperar la respuesta de los servidores de recopilación de datos de Adobe.

La respuesta de Adobe a la solicitud de imagen es una imagen transparente vacía de 1x1 que no es importante para el contenido de la página. Si ve un elemento de línea en el monitor de paquetes de Adobe, bien con una respuesta **[!UICONTROL 200 OK]** o con una respuesta **[!UICONTROL NS_BINDING_ABORTED]**, los datos han llegado a los servidores de Adobe. No es necesario hacer que la página espere más.

Los monitores de paquetes integrados como complemento casi nunca ven la respuesta completa. Los monitores suelen ver la solicitud como anulada ya que no se recibió la respuesta completa. Estos monitores rara vez distinguen entre si lo que se anuló fue la solicitud o la respuesta. Un monitor de paquetes independiente normalmente tiene mensajes más detallados e informa del estado de manera más precisa. Por ejemplo, un usuario puede recibir un mensaje en *Charles* que indique “El cliente cerró la conexión antes de recibir la respuesta completa”. Esto significa que los datos llegaron a los servidores de Adobe, pero que el explorador pasó a la página siguiente antes de que se recibiera la imagen de 1x1 píxeles.

Si un monitor de paquetes externo informa de que se ha anulado la solicitud de recopilación de datos, y no la respuesta, esto podría ser motivo de preocupación. Adobe [!DNL Customer Care] puede proporcionar ayuda para solucionar el problema.
