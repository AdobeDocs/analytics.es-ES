---
title: Analizadores de paquetes
description: Los analizadores de paquetes permiten ver los datos que se envían desde la implementación a los servidores de recopilación de datos de Adobe.
keywords: detector de paquetes, estado http, 200, 302, charles
feature: Implementation Basics
exl-id: db077293-f72c-4933-8a30-f1e1963f332e
role: Admin, Developer, Leader
TQID: 'https://experienceleague.adobe.com/debgxI3FK1fp1Q02GY1-0H40z-L4G2HSmq11Tog97-Y'
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
subfeature_v2: id: e992d880-33bc-4949-a648-aa7d410276cd
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: f8a45b24-4be7-4f1b-909b-60d06b483a20id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c1579802-ddd4-4214-8a91-97b2066abe11id: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 301a0341e725ca15f1700046528ea5f42969add4
workflow-type: tm+mt
source-wordcount: 679
ht-degree: 69%

---

# Analizadores de paquetes

Los analizadores de paquetes permiten ver los datos que se envían desde la implementación a los servidores de recopilación de datos de Adobe.

Al igual que Adobe CX Enterprise Debugger, un monitor de paquetes muestra qué parámetros de datos se pasan en una solicitud de imagen. Sin embargo, los monitores de paquetes proporcionan más funciones:

* Ver solicitudes de imagen de seguimiento de enlaces personalizados
* Ver solicitudes de imagen usando métodos de implementación diferentes de JavaScript, como solicitudes de imagen preprogramadas o [!DNL Appmeasurement]

Para ver solicitudes de Analytics, filtre las solicitudes de salida mediante &quot;b/ss&quot;.

En casos muy excepcionales, el depurador informará de una solicitud de imagen aunque en realidad no se haya realizado ninguna solicitud en nuestros servidores de procesamiento de [!DNL Analytics]. El uso de un monitor de paquetes es una buena manera de estar 100% seguro de que una solicitud de imagen específica se está activando correctamente.

Aunque Adobe no proporciona un monitor oficial de paquetes, hay una amplia gama de ellos en Internet. Los siguientes son algunos monitores de paquetes que otros han encontrado útiles.

>[!TIP]
>
>Estas listas no son completas, solo ofrecen información sobre monitores usados con frecuencia.

| Firefox | Internet Explorer | Chrome | Programas independientes |
|---|---|---|---|
| [Punto de observación](https://www.observepoint.com/product#plugin) (visor de etiquetas) | [HttpWatch](https://www.httpwatch.com/) | [Punto de observación](https://www.observepoint.com/product#plugin) (visor de etiquetas) | [Charles](https://www.charlesproxy.com/) |
| [HttpFox](https://addons.thunderbird.net/en-us/firefox/addon/httpfox/) |  | [Herramientas para desarrolladores Chrome](https://code.google.com/chrome/devtools/docs/overview.html) | [Violinista](https://www.telerik.com/fiddler) |
| [Datos de manipulación](https://addons.mozilla.org/es-ES/firefox/addon/tamper-data-for-ff-quantum/) |  | [Firebug Lite](https://chromewebstore.google.com/detail/firebug-lite-for-google-c/ehemiojjcpldeipjhjkepfdaohajpbdo) | [Wireshark](https://www.wireshark.org/) |
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

La respuesta de Adobe a la solicitud de imagen es una imagen transparente vacía de 1x1 que no es importante para el contenido de la página. Si ve un elemento de línea en el monitor de paquetes de Adobe, bien con una respuesta **[!UICONTROL 200 OK]** o con una respuesta **[!UICONTROL NS_BINDING_ABORTED]**, los datos han llegado a los servidores de Adobe. No es necesario que la página espere más.

Los monitores de paquetes integrados como un complemento rara vez ven la respuesta completa. Los monitores suelen ver la solicitud como anulada ya que no se recibió la respuesta completa. Estos monitores rara vez distinguen entre si la solicitud o la respuesta se anularon. Un monitor de paquetes independiente suele tener mensajes más detallados e informa del estado con mayor precisión. Por ejemplo, un usuario puede recibir un mensaje en *Charles* que dice &quot;Conexión cerrada del cliente antes de recibir una respuesta completa&quot;. Esto significa que los datos sí llegaron a nuestros servidores, solo que el navegador pasó a la siguiente página antes de que se recibiera el píxel 1x1.

Si un monitor de paquetes externo informa de que se ha anulado la solicitud de recopilación de datos, y no la respuesta, esto podría ser motivo de preocupación. Adobe [!DNL Customer Care] puede proporcionar ayuda para solucionar el problema.
