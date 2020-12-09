---
title: Implementación con solicitudes de imagen codificadas
description: Implemente Adobe Analytics con una etiqueta de imagen HTML (solicitud de imagen codificada)
translation-type: tm+mt
source-git-commit: 09b453c1b4cd8555c5d1718759003945f5c230c5
workflow-type: tm+mt
source-wordcount: '655'
ht-degree: 100%

---


# Implementación con solicitudes de imagen codificadas

Las bibliotecas de AppMeasurement proporcionadas por Adobe compilan variables presentes en la página y, a continuación, las envían como una solicitud de imagen a Adobe. Puede omitir todas las bibliotecas de AppMeasurement y enviar manualmente una solicitud de imagen a Adobe. Este método necesita que formule manualmente la solicitud de imagen y la cadena de consulta.

Este método de implementación se puede utilizar en cualquier plataforma que muestre imágenes de fuentes externas. No se basa en JavaScript.

>[!NOTE]
>
>Aunque las solicitudes de imagen codificadas son fáciles de configurar, son difíciles de depurar, mantener y adaptar en proyectos más grandes. Asegúrese de que las solicitudes de imagen codificadas sean la mejor opción antes de continuar.

## Sintaxis de solicitud de imagen

A continuación se muestra un ejemplo de solicitud de imagen codificada mediante HTML:

```html
<img src="https://example.data.adobedc.net/b/ss/examplersid/1?AQB=1&g=http%3A%2F%2Fexample.com&pageName=Example%20hardcoded%20hit&v1=Example%20value&AQE=1"/>
```

* `https://` designa el protocolo. Haga coincidir el protocolo utilizado en la solicitud de imagen con el protocolo que utiliza el resto del sitio.
* `example.data.adobedc.net` es el valor contenido en la variable [`trackingServer`](/help/implement/vars/config-vars/trackingserver.md).
* `/b/ss/` se incluye en todas las solicitudes de imagen. Forma parte de la estructura de archivos de las imágenes almacenadas en los servidores de recopilación de datos de Adobe.
* `examplersid` es el ID del grupo de informes al que desea enviar los datos.
* `/1/` es el origen de la visita. Consulte `hit_source` en [Referencia de columna Datos](../../export/analytics-data-feed/c-df-contents/datafeeds-reference.md) en la Guía del usuario de exportación. Controla el orden que utilizan las cookies y otros métodos para identificar a los visitantes.
* Todo lo que hay después del delimitador de cadena de consulta (`?`) son los datos que desea incluir en los informes. Consulte [Parámetros de consulta de recopilación de datos](../validate/query-parameters.md) para ver la lista completa de parámetros que puede incluir en una solicitud de imagen.

## Solicitudes de imagen codificadas en Microsoft Outlook

Dado que la mayoría de los mensajes de correo electrónico están basados en HTML, es posible rastrear los mensajes abiertos y enviar esos datos a Adobe Analytics. Si su organización decide utilizar este método, tenga en cuenta lo siguiente:

* Cada procesamiento de correo electrónico puede incrementar una llamada al servidor facturable.
* Solo se realiza el seguimiento de los clientes de correo electrónico que admiten HTML y permiten imágenes. Algunos clientes de correo electrónico, como Microsoft Outlook, bloquean las imágenes externas de forma predeterminada. Estos correos electrónicos no se rastrean hasta que el destinatario decide descargar las imágenes externas.

Para componer un correo electrónico de Outlook que incluya una solicitud de imagen:

1. Abra un editor HTML. Si no hay un editor HTML disponible, también funciona un editor de texto sin formato.
2. En un nuevo archivo HTML, inserte una etiqueta `<img>` de solicitud de imagen codificada en una etiqueta `<body>`.
3. Guarde el archivo HTML.
4. Abra Microsoft Outlook y redacte un correo electrónico.
5. Vaya a la pestaña Insertar y haga clic en **Adjuntar archivo**. Seleccione el archivo HTML de solicitud de imagen.
6. Haga clic en el menú emergente situado junto a Insertar y seleccione **Insertar como texto**. Si hace clic en el botón Insertar sin el menú emergente, el archivo HTML se convierte en un archivo adjunto, que no funciona.

El correo electrónico no parece cambiar, ya que la solicitud de imagen es un píxel transparente de 1x1. Si desea ver la solicitud de imagen con fines de prueba, modifique el archivo HTML para incluir un borde, texto adicional u otro contenido.

## Preguntas más frecuentes

Descubra las preguntas más comunes sobre el uso solicitudes de imagen codificadas.

### ¿Distinguen entre mayúsculas y minúsculas los parámetros de cadena de consulta?

Sí. Asegúrese de que los parámetros de cadena de consulta coincidan exactamente o de que no se registren. Por ejemplo, `pagename` no es un parámetro de cadena de consulta válido, mientras que `pageName` lo es.

### ¿Puedo incluir espacios en la cadena de consulta?

Los valores de cada uno de los parámetros de cadena de consulta se codifican con URL. La codificación de URL convierte los caracteres que normalmente no son válidos en las direcciones URL en caracteres válidos. Por ejemplo, un carácter de espacio se convierte en `%20`. Asegúrese de que cualquier carácter que no sea alfanumérico tenga codificación de dirección URL. La URL de Adobe descodifica automáticamente los valores cuando las solicitudes de imagen llegan a los servidores de recopilación de datos.

Consulte [Referencia de codificación de URL HTML](https://www.w3schools.com/tags/ref_urlencode.asp) en W3Schools para obtener más información sobre cómo funciona la codificación de URL.

### ¿Cuál es el número máximo de caracteres que puede tener un solo valor?

Cada variable tiene una longitud máxima diferente. La mayoría de las variables de tráfico tienen hasta 100 bytes, mientras que la mayoría de las variables de conversión tienen hasta 255 bytes. Cuando una solicitud de imagen llega a los servidores de recopilación de datos, Adobe trunca automáticamente estos valores a su longitud máxima.
