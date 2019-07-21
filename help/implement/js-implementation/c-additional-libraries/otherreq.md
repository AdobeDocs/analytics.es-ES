---
description: Hay algunos requisitos y configuraciones adicionales para implementar Analytics sin JavaScript.
keywords: Implementación de Analytics; distingue entre mayúsculas y minúsculas; codificar parámetros de consulta; caracteres no válidos; secure image requests; longitud máxima de variable; referir; url; almacenamiento en caché; namespace
seo-description: Hay algunos requisitos y configuraciones adicionales para implementar Analytics sin JavaScript.
seo-title: Implementación sin directrices de JavaScript
solution: Analytics
title: Implementación sin directrices de JavaScript
topic: Desarrollador e implementación
uuid: c 672 dd 63-1 c 74-4 f 66-8992-9257 c 5 a 75 e 36
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Implementación sin directrices de JavaScript

Hay algunos requisitos y configuraciones adicionales para implementar Analytics sin JavaScript.

Puede ver un ejemplo de código para comprender mejor la implementación. La siguiente información describe los requisitos y configuraciones adicionales:

<!--Meike, I converted this from a table. Table within a table was a mess, and I'm not sure I captured everything. Please check this content against the orginal. -Bob -->

**Distinción entre mayúsculas y minúsculas**

The parameter names (`pageName`, `purchaseID`, and so forth) are case-sensitive and will not properly record data unless they appear as designated in the table displayed in [Query Parameters](../../../implement/js-implementation/data-collection/query-parameters.md).

**Codificar los parámetros de consulta**

Los valores de cada uno de los parámetros de cadena de consulta deben codificarse con URL. La codificación URL convierte los caracteres que normalmente no se admiten cuando aparecen en una cadena de consulta, como el espacio, en un carácter codificado que comienza por `%`. Por ejemplo, un carácter de espacio se convierte en `%20`.

La versión para JavaScript de esta función se denomina escape (y para decodificar, unescape). Microsoft IIS versión 5.0 también incluye las funciones Escape y Unescape para codificar cadenas de consulta. Otros lenguajes de scripting de servidor web también proporcionan utilidades de codificación/descodificación.

**Longitud de variable máxima**

Cada variable tiene una longitud máxima. Esta longitud se especifica para cada variable en [Variables de Analytics](../../../implement/js-implementation/c-variables/sc-variables.md). Si se supera la longitud máxima de una variable, el valor de esta variable se trunca al almacenarse y mostrarse en Analytics.

**Caracteres no válidos**

Los caracteres con códigos de carácter superiores a 128 decimal no son válidos, como tampoco lo son los códigos de carácter de no impresión inferiores a 128. Tampoco son válidos el formato HTML ("&lt;h1&gt;") ni los símbolos de marca comercial, marca registrada y copyright.

**Secure (&lt; https: &gt; frente a no seguro (&lt; http: &gt; Solicitudes de imagen**

En las páginas a las que se accede mediante https (protocolo seguro), la parte URL de la solicitud de imagen cambia para acomodar un conjunto diferente de servidores de recopilación de datos.

La siguiente información ilustra las distintas URL utilizadas para solicitudes de imagen seguras y no seguras.

* The `*` in the URL above denotes a data-center specific URL that is provided to you by your Adobe Consultant. Adobe usa varios centros de datos y es necesario implementar la dirección URL correcta a la que ha sido asignada su organización. Todo el código que se descargue desde Admin Console en su cuenta de empresa tiene el centro de datos correcto de forma automática. El código proporcionado por fuentes externas quizás tenga que corregirse para que apunte al centro de datos correcto.
* Para aquellos clientes que usan varios grupos de informes, deben incluirse solo en la sección de directorio y no en la sección de dominio de la dirección URL, como se muestra a continuación.
* The `*` in the URL above denotes a data-center specific URL that is provided to you by your Adobe Consultant. Adobe usa varios centros de datos y es necesario implementar la dirección URL correcta a la que ha sido asignada su organización.

**Dirección URL y dirección URL de referencia**

The URL and Referring URL may be populated from the server in the `g=` and `r=` variables. Use the Request ServerVariables (`HTTP\_REFERRER`) or Request ServerVariables `(URL) (IIS/ASP)`, or the appropriate variable for your server/scripting technology. The referring URL `( r=)` is extremely important for tracking referring URLs, domains, search engines, and search terms.

Si no se utiliza pagename, es imperativo que el campo URL actual se rellene de forma única. If neither pageName nor Current URL `(g=)` is populated, the record is invalid and is not processed. Como mínimo se necesita la dirección URL para procesar el registro.

**Efectos del almacenamiento en caché**

Las páginas HTML y otras páginas web pueden ser almacenadas en caché por los exploradores o servidores que están entre el visitante y el sitio web que sirve el contenido. El almacenamiento en caché impide un recuento preciso de vistas de página y otros eventos a menos que se emplee una técnica de «batida de caché».

El código JavaScript estándar de Adobe incluye un método dinámico para cambiar la solicitud de imagen con el fin de evitar el almacenamiento en caché de páginas e imágenes, lo que permite un recuento preciso de las vistas de página.

Sin embargo, en la creación de una solicitud de imagen en el lado del servidor no se produce esta aleatorización. Las recargas de página y las páginas en caché (ya sea en la memoria caché del explorador o en un servidor proxy) no se contabilizan en determinados casos cuando se usan solicitudes de imagen del lado del servidor.

SSL (`https:`) pages are not, by definition, ever cached so this warning applies only to non-secure (`http:`) pages. Additionally, pages with parameters (`https://www.samplesite.com/page.asp?parameter=1`) or certain file extensions (`.asp`, `.jsp`, etc.) tampoco se almacenan en caché.

El ejemplo siguiente ilustra también una solución JavaScript mínima que ensambla la solicitud de imagen del lado del servidor y agrega un número aleatorio en el explorador. Este método supera el almacenamiento en caché que de otro modo se encontraría en páginas HTML estáticas a las que se accede mediante https: protocolo.

**Variable nameSpace**

El parámetro de cadena de consulta nameSpace es necesario en implementaciones que no son de JavaScript.

Ejemplo: ns=nameSpace

Póngase en contacto con su consultor de Adobe o con el Administrador de cuentas para obtener el valor de nameSpace de su organización.
