---
description: Hay algunos requisitos y configuraciones adicionales para implementar Analytics sin JavaScript.
keywords: Analytics Implementation;case sensitive;encode query parameters;invalid characters;secure image requests;maximum variable length;referring;url;caching;namespace
title: Implementación sin directrices de JavaScript
topic: Developer and implementation
uuid: c672dd63-1c74-4f66-8992-9257c5a75e36
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Implementación sin directrices de JavaScript

Hay algunos requisitos y configuraciones adicionales para implementar Analytics sin JavaScript.

Puede ver un ejemplo de código para comprender mejor la implementación. La siguiente información resume los requisitos y configuraciones adicionales:

<!--Meike, I converted this from a table. Table within a table was a mess, and I'm not sure I captured everything. Please check this content against the orginal. -Bob -->

**Distinción entre mayúsculas y minúsculas**

Los nombres de parámetro (`pageName`, `purchaseID`, etc.) distinguen entre mayúsculas y minúsculas y no registrarán correctamente los datos a menos que aparezcan tal y como se designan en la tabla que se muestra en [Parámetros de consulta](/help/implement/js-implementation/data-collection/query-parameters.md).

**Codificar los parámetros de consulta**

Los valores de cada uno de los parámetros de cadena de consulta deben codificarse con URL. La codificación URL convierte los caracteres que normalmente no se admiten cuando aparecen en una cadena de consulta, como el espacio, en un carácter codificado que comienza por `%`. Por ejemplo, un carácter de espacio se convierte en `%20`.

La versión para JavaScript de esta función se denomina escape (y para decodificar, unescape). Microsoft IIS versión 5.0 también incluye las funciones Escape y Unescape para codificar cadenas de consulta. Otros lenguajes de scripting de servidor web también proporcionan utilidades de codificación/descodificación.

**Longitud de variable máxima**

Cada variable tiene una longitud máxima. Esta longitud se especifica para cada variable en [Variables de Analytics](/help/implement/js-implementation/c-variables/sc-variables.md). Si se supera la longitud máxima de una variable, el valor de esta variable se trunca al almacenarse y mostrarse en Analytics.

**Caracteres no válidos**

Los caracteres con códigos de carácter superiores a 128 decimal no son válidos, como tampoco lo son los códigos de carácter de no impresión inferiores a 128. Tampoco son válidos el formato HTML ("&lt;h1&gt;") ni los símbolos de marca comercial, marca registrada y copyright.

**Solicitudes de imagen seguras (&lt;https:&gt;) frente a no seguras (&lt;http:&gt;)**

En las páginas a las que se accede mediante https (protocolo seguro), la parte URL de la solicitud de imagen cambia para acomodar un conjunto diferente de servidores de recopilación de datos.

La siguiente información ilustra las diferentes direcciones URL utilizadas para solicitudes de imagen seguras y no seguras.

* El `*` en la dirección URL anterior indica una dirección URL específica de un centro de datos facilitada por su consultor Adobe. Adobe usa varios centros de datos y es necesario implementar la dirección URL correcta a la que ha sido asignada su organización. Todo el código que se descargue desde Admin Console en su cuenta de empresa tiene el centro de datos correcto de forma automática. El código proporcionado por fuentes externas quizás tenga que corregirse para que apunte al centro de datos correcto.
* Para aquellos clientes que usan varios grupos de informes, deben incluirse solo en la sección de directorio y no en la sección de dominio de la dirección URL, como se muestra a continuación.
* El `*` en la dirección URL anterior indica una dirección URL específica de un centro de datos facilitada por su consultor Adobe. Adobe usa varios centros de datos y es necesario implementar la dirección URL correcta a la que ha sido asignada su organización.

**Dirección URL y dirección URL de referencia**

Las direcciones URL y URL de referencia se pueden rellenar desde el servidor en las variables `g=` y `r=`. Use Request ServerVariables (`HTTP\_REFERRER`) o Request ServerVariables `(URL) (IIS/ASP)` o las variables apropiadas para su tecnología de servidor/scripts. La dirección URL de referencia `( r=)` es extremadamente importante para realizar el seguimiento de direcciones URL de referencia, dominios, motores de búsqueda y términos de búsqueda.

Si pageName no se va a usar, es obligatorio que el campo URL actual se rellene de forma única. Si pageName ni la URL actual `(g=)` no están completadas, el registro no es válido y no se procesará. Como mínimo se necesita la dirección URL para procesar el registro.

**Efectos del almacenamiento en caché**

Las páginas HTML y otras páginas web pueden ser almacenadas en caché por los exploradores o servidores que están entre el visitante y el sitio web que sirve el contenido. El almacenamiento en caché impide un recuento preciso de vistas de página y otros eventos a menos que se emplee una técnica de batida de caché.

El código JavaScript estándar de Adobe incluye un método dinámico para cambiar la solicitud de imagen con el fin de evitar el almacenamiento en caché de páginas e imágenes, lo que permite un recuento preciso de las vistas de página.

Sin embargo, en la creación de una solicitud de imagen en el lado del servidor no se produce esta aleatorización. Las recargas de página y las páginas en caché (ya sea en la memoria caché del explorador o en un servidor proxy) no se contabilizan en determinados casos cuando se usan solicitudes de imagen del lado del servidor.

Por definición, las páginas SSL (`https:`) no se almacenan nunca en caché por lo que esta advertencia se aplica solo a páginas no seguras (`http:`). Además, las páginas con parámetros (`https://www.samplesite.com/page.asp?parameter=1`) o determinadas extensiones de archivo (`.asp`, `.jsp`, etc.) tampoco se almacenan en caché.

El ejemplo siguiente ilustra también una solución JavaScript mínima que ensambla la solicitud de imagen del lado del servidor y agrega un número aleatorio en el explorador. Este método evita el almacenamiento en caché que de otro modo se encontraría en las páginas HTML estáticas a las que se accede mediante el protocolo https:.

**Variable nameSpace**

El parámetro de cadena de consulta nameSpace es necesario en implementaciones que no son de JavaScript.

Ejemplo: ns=nameSpace

Póngase en contacto con su consultor de Adobe o con el Administrador de cuentas para obtener el valor de nameSpace de su organización.
