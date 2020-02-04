---
title: Implementación con solicitudes de imagen codificadas
description: Implementación de Adobe Analytics mediante una etiqueta de imagen HTML (solicitud de imagen codificada)
translation-type: tm+mt
source-git-commit: 819f719c4ce131c04916f3b668bcbda1a1b03651

---


# Implementación con solicitudes de imagen codificadas

Las bibliotecas de AppMeasurement proporcionadas por Adobe compilan variables presentes en la página y, a continuación, las envían como una solicitud de imagen a Adobe. Puede omitir todas las bibliotecas de AppMeasurement y enviar manualmente una solicitud de imagen a Adobe. Este método requiere que formule manualmente la solicitud de imagen y la cadena de consulta.

Este método de implementación se puede utilizar en cualquier plataforma que muestre imágenes de fuentes externas. No se basa en absoluto en JavaScript.

> [!NOTE] Aunque las solicitudes de imagen codificadas son fáciles de configurar, son difíciles de depurar, mantener y escalar en proyectos más grandes. Asegúrese de que las solicitudes de imagen codificadas son la mejor opción antes de continuar.

## Sintaxis de solicitud de imagen

A continuación se muestra un ejemplo de solicitud de imagen codificada mediante HTML:

```html
<img src="https://example.sc.omtrdc.net/b/ss/examplersid/1?AQB=1&g=http%3A%2F%2Fexample.com&pageName=Example%20hardcoded%20hit&v1=Example%20value&AQE=1"/>
```

* `https://` designa el protocolo. Haga coincidir el protocolo utilizado en la solicitud de imagen con el protocolo que utiliza el resto del sitio.
* `example.sc.omtrdc.net` es el valor contenido en la `trackingServer` variable.
* `/b/ss/` se incluye en todas las solicitudes de imagen. Forma parte de la estructura de archivos de las imágenes almacenadas en los servidores de recopilación de datos de Adobe.
* `examplersid` es la ID del grupo de informes a la que desea enviar los datos.
* `/1/` es el origen de la visita. Consulte `hit_source` en Referencia [de columna](../../export/analytics-data-feed/c-df-contents/datafeeds-reference.md) Datos en la Guía del usuario de exportación. Controla el orden que utilizan las cookies y otros métodos para identificar a los visitantes.
* Todo lo que hay después del delimitador de cadena de consulta (`?`) son los datos que desea incluir en los informes. Consulte Parámetros [de consulta de recopilación de](../validate/query-parameters.md) datos para ver la lista completa de parámetros que puede incluir en una solicitud de imagen.

## Preguntas más frecuentes

Obtenga información sobre las preguntas más comunes mediante solicitudes de imagen codificadas.

**¿Distinguen entre mayúsculas y minúsculas los parámetros de cadena de consulta?**

Sí. Asegúrese de que los parámetros de cadena de consulta coincidan exactamente o de que no se registren. Por ejemplo, `pagename` no es un parámetro de cadena de consulta válido, mientras que `pageName` lo es.

**¿Puedo incluir espacios en la cadena de consulta?**

Los valores de cada uno de los parámetros de cadena de consulta están codificados con la dirección URL. La codificación de URL convierte los caracteres que normalmente no son válidos en las direcciones URL en caracteres legales. Por ejemplo, un carácter de espacio se convierte en `%20`. Asegúrese de que cualquier carácter que no sea alfanumérico tenga codificación de dirección URL. La URL de Adobe descodifica automáticamente los valores cuando las solicitudes de imagen llegan a los servidores de recopilación de datos.

Consulte Referencia [de codificación de URL](https://www.w3schools.com/tags/ref_urlencode.asp) HTML en W3Schools para obtener más información sobre cómo funciona la codificación de URL.

**¿Cuál es el número máximo de caracteres que puede tener un solo valor?**

Cada variable tiene una longitud máxima diferente. La mayoría de las variables de tráfico tienen hasta 100 bytes, mientras que la mayoría de las variables de conversión tienen hasta 255 bytes. Cuando una solicitud de imagen llega a los servidores de recopilación de datos, Adobe trunca automáticamente estos valores a su longitud máxima.
