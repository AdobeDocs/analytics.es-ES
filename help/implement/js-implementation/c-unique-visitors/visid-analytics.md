---
description: 'Cuando un usuario visita el sitio, el servidor web de Adobe configura una cookie persistente incluyéndola en la respuesta HTTP al explorador. Esta cookie se configura en el dominio de recopilación de datos especificado. '
keywords: Implementación de Analytics
seo-description: 'Cuando un usuario visita el sitio, el servidor web de Adobe configura una cookie persistente incluyéndola en la respuesta HTTP al explorador. Esta cookie se configura en el dominio de recopilación de datos especificado. '
seo-title: ID de visitante de Analytics
solution: Analytics
title: ID de visitante de Analytics
topic: Desarrollador e implementación
uuid: fa 7737 cc -0190-4 d 27-af 1 b -87301 a 715 df 2
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# ID de visitante de Analytics

Cuando un usuario visita el sitio, el servidor web de Adobe configura una cookie persistente incluyéndola en la respuesta HTTP al explorador. Esta cookie se configura en el dominio de recopilación de datos especificado. 

Cuando se envía una solicitud al servidor de recopilación de datos de Adobe, se comprueba la existencia de la cookie de ID de visitante (`s_vi`) en el encabezado. Si la cookie se encuentra en la solicitud, se usa para identificar al visitante. En caso contrario, el servidor genera una ID de visitante única, la establece como cookie en el encabezado de respuesta HTTP y la devuelve con la solicitud. La cookie se almacena en el explorador y se devuelve al servidor de recopilación de datos durante las visitas subsiguientes al sitio, lo que permite identificar al visitante en las distintas visitas.

## Cookies de terceros y registros CNAME {#section_61BA46E131004BB2B75929C1E1C93139}

Algunos exploradores, como Apple Safari, ya no almacenan cookies configuradas en el encabezado HTTP de los dominios que no coincidan con el dominio del sitio web actual (se trata de una cookie usada en un contexto de terceros o una cookie de terceros). Por ejemplo, si está en `mysite.com` y el servidor de recopilación de datos es `mysite.omtrdc.net`, el explorador puede rechazar la cookie que se devuelve en el encabezado HTTP desde `mysite.omtrdc.net`.

Para evitarlo, muchos clientes han implementado registros CNAME para sus servidores de recopilación de datos como parte de la [implementación de cookies de origen](https://marketing.adobe.com/resources/help/en_US/whitepapers/first_party_cookies/). Si se configura la asignación de un registro CNAME a un nombre de host en el dominio del cliente para el servidor de recopilación de datos (por ejemplo, si se asigna `metrics.mysite.com` a `mysite.omtrdc.net`), se almacenará la cookie de ID de visitante porque ahora coinciden los dominios de recopilación de datos y del sitio web. Así aumentan las probabilidades de que se almacene la cookie de ID de visitante, pero se obtiene una cierta sobrecarga porque es necesario configurar los registros CNAME y mantener los certificados SSL para los servidores de recopilación de datos.

## Cookies en dispositivos móviles {#section_7D05AE259E024F73A95C48BD1E419851}

A la hora de rastrear dispositivos móviles con cookies, el método de medición puede modificarse con ciertas opciones. Aunque la duración predeterminada de las cookies es de 5 años, puede modificarla con la variable del parámetro de consulta CL (`s.cookieLifetime`). Para establecer la ubicación de las cookies en implementaciones de cname, use la cadena de consulta CDP `s.cookieDomainPeriods`. Si no se modifica la configuración, el valor predeterminado es 2 y la ubicación predeterminada es domain.com. En las implementaciones que no usan CNAME, las cookies de ID de visitante se ubican en el dominio 207.net.
