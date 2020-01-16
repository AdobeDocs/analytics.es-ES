---
description: Cookies de Analytics
title: Preguntas más frecuentes sobre las cookies de explorador y análisis
uuid: null
translation-type: tm+mt
source-git-commit: 38de617d3c77195d2308e14783962f6690b4b3fc

---


# Preguntas más frecuentes sobre exploradores y cookies de Analytics

Para admitir la identificación persistente de usuarios en todas las propiedades y soluciones, Adobe Analytics responde a los cambios en el modo en que los navegadores gestionan las cookies. Las siguientes preguntas más frecuentes presentan información sobre cómo se preserva la identificación persistente del visitante con los cambios en las cookies del explorador.

## ¿Cómo están cambiando los exploradores la forma en que administran las cookies?

En general, la mayoría de los exploradores se están volviendo más restrictivos en la forma en que albergan cookies de terceros. Esto puede afectar al seguimiento si el explorador elimina o rechaza la cookie. El explorador Safari también está configurando algunas limitaciones para algunas cookies de origen.

La siguiente lista muestra algunos cambios recientes según los exploradores:

* Chrome: A partir de Chrome 80, el `SameSite` atributo se gestiona de forma diferente para administrar las cookies de terceros o las solicitudes entre sitios. En última instancia, los desarrolladores de Chrome buscan formas de [eliminar por completo las cookies](https://blog.chromium.org/2020/01/building-more-private-web-path-towards.html?m=1) de terceros.

* Firefox y Edge: Los anuncios de productos indican que las versiones sucesivas de sus navegadores deben seguir los mismos cambios que los realizados en Chrome 80.

* Safari: With [Safari 12.1](https://webkit.org/blog/category/privacy/), first party persistent cookies set through the document.cookie API, often known as “client-side” cookies, have their expiration capped at seven days.

## ¿Cuál es la diferencia entre las cookies de terceros y las cookies de origen?

### Cookies de origen

Las cookies individuales las crean los sitios web de los clientes (específicas del dominio) y se almacenan en los navegadores de los clientes a medida que los usuarios visitan los sitios web de los clientes. En general, todos los exploradores aceptan cookies de origen. En una implementación de Analytics de cookie de origen, la cookie de ID de visitante se crea en un nodo de Adobe cuando el nombre de host se concilia con el dominio mediante un [CNAME](https://docs.adobe.com/content/help/en/id-service/using/reference/analytics-reference/cname.html). El explorador acepta la cookie en un contexto de origen. Para obtener más información, consulte [Acerca de las cookies](https://docs.adobe.com/content/help/en/core-services/interface/ec-cookies/cookies-first-party.html)de origen.

### Cookies de terceros

Los sitios web que visitan los usuarios no crean cookies de terceros. Aunque los exploradores tratan todas las cookies de terceros de la misma manera y las almacenan en consecuencia, las cookies de terceros pueden comportarse de manera diferente e importante. Con la implementación de cookies de terceros de Analytics de un cliente, el cliente solo realiza llamadas a Adobe y no a dominios de terceros desconocidos o sospechosos. Este es el método actual para implementar Analytics para un seguimiento seguro (HTTPS) y fiable con identificadores persistentes. Este método se implementa configurando el archivo AppMeasurement.js. Para obtener más información, consulte [Cookies y el servicio](https://docs.adobe.com/content/help/en/id-service/using/intro/cookies.html)de identidad de la plataforma de experiencia.

![Diferencias de cookies](assets/cookieimage.PNG)

## ¿Cómo almacenan y administran los navegadores las cookies de Analytics en estos momentos?

Según la implementación, las cookies de Analytics se almacenan de la siguiente manera:

### Implementaciones de cookies de terceros

Los navegadores almacenan actualmente el ID de Adobe [demdex.net](https://docs.adobe.com/content/help/en/audience-manager/user-guide/reference/demdex-calls.html) como una cookie de terceros. Esta cookie proporciona identificadores persistentes entre dominios y permite el contenido seguro (https).

### Implementaciones de cookies de origen

Al configurar un CNAME, el usuario puede recibir cookies de Adobe en un contexto de cookie de origen para sus navegadores. Esta puede ser una opción viable si la implementación de cookies de terceros no es óptima para los usuarios.

## ¿Qué es el atributo de cookie SameSite y cómo afecta a Analytics?

Con el lanzamiento del explorador Chrome 80 (y las versiones sucesivas de Firefox y los exploradores Edge), el atributo SameSite fuerza la especificación de tres valores diferentes para controlar el comportamiento de las solicitudes entre sitios, de la siguiente manera:

* `None`:: Esta configuración habilita el acceso entre sitios y permite que las cookies se pasen en un contexto de terceros. Para especificar este atributo, también debe especificar `Secure` y todas las solicitudes del explorador deben seguir HTTPS. Por ejemplo, al configurar la cookie, empareja los valores del atributo de la siguiente manera: `Set-Cookie: example_session=test12; SameSite=None; Secure`. Si no se etiquetan correctamente, las cookies no se pueden utilizar en los exploradores más recientes y se rechazarán.

* `Lax`:: Permite que las solicitudes entre sitios se envíen con cookies del mismo sitio únicamente para las exploraciones de nivel superior con métodos HTTP *seguros* (solo lectura, como `GET`).

* `Strict`:: La cookie del mismo sitio no se envía para ninguna solicitud de sitio web de terceros. La cookie solo se envía si el sitio de la cookie coincide con el sitio de la barra URL.

El comportamiento predeterminado en estas versiones del explorador es tratar las cookies que no tienen un `SameSite` atributo especificado de la misma manera que `SameSite=Lax`.

## ¿Cómo responde Adobe Analytics a estos cambios?

Todas las actualizaciones de cookies de Adobe se gestionan mediante servidores de Adobe y Adobe ha actualizado sus servidores Edge para establecer los atributos de cookies correspondientes. Adobe ha publicado actualizaciones en el servidor para establecer las cookies de terceros con los atributos adecuados. No se requieren actualizaciones de JavaScript para los sitios.

Esta actualización por parte de los servidores Edge de Adobe se producirá automáticamente cuando los usuarios visiten cualquier sitio Web donde se utilice la cookie. Para la mayoría de los productos de Adobe, las cookies tendrán los indicadores adecuados, ya que Chrome 80 está disponible. La excepción son las implementaciones de Adobe Analytics que utilizan la recopilación de datos de terceros y no usan el servicio de identidad de Experience Cloud (ECID). Es posible que estos clientes experimenten un pequeño aumento temporal en visitantes nuevos que, de lo contrario, se habrían etiquetado como visitantes que retornan.

En el caso de los exploradores que Google identificó como mal manejados cuando `SameSite` se establece en `None`, `SameSite` no se configurará.

La siguiente tabla resume las cookies de Analytics:


![Tabla de cookies de Analytics](assets/cookie_table.png)


## ¿Cuál es la mejor manera de preparar mi sitio para los cambios de Chrome, Firefox y Edge?

Los clientes de Analytics deben confirmar que su configuración de JavaScript utiliza HTTPS para sus llamadas a los servicios de Adobe. ECID redirige las llamadas HTTP de terceros a su extremo HTTPS, lo que puede aumentar la latencia, pero significa que no es necesario que cambie la configuración.

Adobe sugiere asegurarse de que todas las páginas del sitio se proporcionan con HTTPS.

### Un CNAME para varios dominios

Si tiene una implementación CNAME configurada en el mismo dominio que su sitio web, será un contexto de cookie de origen y no necesita realizar cambios.

Sin embargo, si es propietario de varios dominios y utiliza el mismo CNAME para la recopilación de datos en todos los dominios, se trata como una cookie de terceros en esos otros dominios. Con Chrome 80, ya no estará visible en estos otros dominios. Para que el comportamiento sea más similar en todos los exploradores, Analytics está estableciendo explícitamente el valor `SameSite` de esta cookie en `Lax`. Si utiliza esta cookie en un contexto de terceros práctico, deberá tener la cookie configurada con el `SameSite=None` valor, lo que también significa que siempre debe utilizar HTTPS. Póngase en contacto con el Servicio de atención al cliente de Adobe para que se cambie el valor de SameSite para sus CNAME seguros. Tenga en cuenta que esta acción NO es obligatoria para los clientes de Analytics que usan ECID.

## ¿Cuál es el impacto de los cambios de Safari (ITP 2.1) para Analytics?

A pesar de los cambios realizados en Safari 12.1, los conjuntos de datos de las cookies de Adobe Experience Cloud se siguen recopilando. Aunque las cookies tienen un límite de siete días, los visitantes que regresan a su propiedad dentro de ese tiempo renuevan la cookie y evitan que caduque durante otros siete días. Las ventanas de búsqueda y los recuentos de visitantes de retorno se pueden reducir para el tráfico de Safari hasta que haya una actualización de Adobe disponible.

Debido a la reducción de la ventana de caducidad de siete días, los clientes pueden ver un aumento de visitantes únicos. Los recuentos de visitas y vistas de página no deberían verse afectados. Si tiene una propiedad que tiene tráfico estacional, como servicios fiscales o venta minorista de vacaciones, puede que tenga un mayor impacto, ya que este visitante no estará conectado entre temporadas.

Si utiliza un CNAME, el servicio de ID de visitante guardará el ECID en una cookie de origen del lado del servidor. Esto permite que la cookie persista durante toda su duración.

**Nota: ITP 2.1 no se aplicará a los navegadores incrustados en aplicaciones móviles.**

### Cookies de origen afectadas

Las cookies de origen creadas a través de `document.cookie` se ven afectadas. Si está configurando cualquiera de estas cookies a través de una respuesta HTTP (en el servidor) o mediante la certificación CNAME, no se verá afectado por los cambios en ITP 2.1. Las siguientes cookies de origen y las bibliotecas de JavaScript de Adobe relacionadas se ven afectadas:

* Cookies AMCV establecidas por la biblioteca de servicios ECID (Experience Cloud ID)
* Cookie de reserva heredada de Analytics `s_fid`

La `s_vi` cookie heredada de Analytics como cookie de terceros, incluidos los destinos de recopilación de 2o7.net u omtrdc.net, sigue bloqueada en función de versiones anteriores de ITP.

En resumen:

* Si tiene un CNAME y utiliza el servicio de ID de visitante — su implementación no se verá afectada.

* Si utiliza un CNAME de origen en el contexto de origen y no utiliza el servicio de ID de visitante, su implementación no se verá afectada.

* Si utiliza un dominio de cookie de origen en el contexto de terceros o con los nombres de dominio de terceros estándar (por ejemplo, 2o7.net, omtrdc.net, etc.), Safari seguirá bloqueándolo como lo ha hecho.

* Si utiliza una ID de visitante personalizada — Esto dependerá de cómo almacene su ID de visitante. Si almacena su ID en una cookie &quot;del lado del cliente&quot; de origen, estará sujeto a la caducidad de siete días. Si utiliza otros medios para almacenar su ID personalizada, deberá evaluar si se ve afectado.

### Conjuntos de datos menos afectados

Los conjuntos de datos con visitantes activos que regresan con frecuencia son los menos afectados por los cambios. Si el contenido del sitio es tal que los clientes regresan a diario o al menos un par de veces por semana, las cookies de estos usuarios activos se renovarán antes de que caduquen. Es muy probable que las redes sociales, los sitios de noticias y otros medios tengan grandes comunidades de usuarios que regresan con frecuencia.

ITP 2.1 no afectará a los clientes que utilicen `s_vi` como ID de visitante principal y estén configurados con recopilación de datos de origen mediante un CNAME. Tenga en cuenta que en los casos en los que `s_vi` no se puede establecer, la cookie de reserva `s_fid` puede utilizarse y tendrá una caducidad de siete días.

Además, los conjuntos de datos que utilizan el servicio de ID de visitante y tienen un dominio de origen se ven menos afectados.

## ¿Afectarán los cambios de Safari a mi negocio?

Adobe recomienda que los clientes midan primero el impacto dentro de su propia empresa antes de realizar cambios en la recopilación de datos. Esto se puede hacer mediante los métodos que se indican a continuación en esta sección.

Para medir el impacto en los informes y las pruebas, es importante saber qué tipo de seguimiento de visitantes y cookies ha implementado y cuánto tráfico ha recibido de los usuarios con Safari. Considere lo siguiente para medir el impacto en su negocio individual:

* Compruebe qué tipos de cookies están configurando las bibliotecas de Adobe.

* Abra la consola del desarrollador en el último navegador Safari. Si ve alguna de las cookies enumeradas arriba configurada en su dominio de origen, puede verse afectado por estos cambios.

* Si ve una `s_vi` cookie, pero no una `AMCV` cookie establecida en el contexto de un CNAME, está utilizando un CNAME para la identificación de visitantes y el uso de Analytics no se ve afectado por estos cambios. Si ve una `s_vi` cookie y una `AMCV` cookie configuradas en el contexto de un CNAME, hace poco o está utilizando un período de gracia y es posible que parte del tráfico de Analytics se vea afectado.

* Utilice Analytics para medir el porcentaje de visitantes que no regresan en un plazo de siete días. Si los visitantes regresan repetidamente en un plazo de siete días, es posible que el tráfico no se vea significativamente afectado. Para obtener instrucciones sobre el uso de Analytics para averiguarlo, consulte Impacto [Safari ITP 2.1 en Adobe Experience Cloud y clientes](https://medium.com/adobetech/safari-itp-2-1-impact-on-adobe-experience-cloud-customers-9439cecb55ac)de la plataforma de experiencia.

* Mida el porcentaje de tráfico desde los exploradores Safari para determinar si se justifica realizar cambios. Para obtener instrucciones sobre el uso de Analytics para averiguar el porcentaje de tráfico de Safari en sus sitios, consulte [Safari ITP 2.1 Impact on Adobe Experience Cloud and Experience Platform Customers](https://medium.com/adobetech/safari-itp-2-1-impact-on-adobe-experience-cloud-customers-9439cecb55ac).

## ¿Qué exploradores utilizan más los visitantes?

Si le interesa conocer más sobre los navegadores utilizados por los visitantes, puede utilizar la dimensión [del](https://docs.adobe.com/content/help/en/analytics/components/variables/dimensions-reports/reports-browsers.html) explorador de Analytics para determinar qué exploradores se utilizan más en los sitios. También puede utilizar las dimensiones de Analytics para ver qué exploradores se utilizan más según las regiones geográficas. For more information, see [GeoSegmentation](https://docs.adobe.com/content/help/en/analytics/components/variables/dimensions-reports/reports-geosegmentation.html).

Según [statcounter](https://gs.statcounter.com/browser-market-share/all), a finales de 2019 la cuota de mercado mundial para cada navegador era la siguiente:

* Chrome: ~64%
* Safari: ~17%
* Firefox: ~4%
* Edge: ~2%

A medida que cambie la cuota de mercado, puede consultar dichas [estadísticas](https://gs.statcounter.com/browser-market-share/all) para revisar su estrategia de implementación.

## ¿Cómo puedo trabajar mejor con los cambios de ITP 2.1 en Safari a corto plazo?

El CNAME de Adobe y el programa de certificados administrados se utilizan para hacer frente a los cambios de ITP. El programa de certificados administrados le permite implementar un nuevo certificado de origen para cookies de origen sin coste adicional. En la actualidad, Adobe cuenta con varios servicios CNAME por solución y busca aprovechar el programa de certificación de Analytics a corto plazo.

Cualquier cliente actual de Analytics con una configuración CNAME que también utilice los servicios de ID de Experience Cloud para la identificación de visitantes podrá aprovechar una actualización futura de la biblioteca ECID. Este cambio permitirá que los servidores de seguimiento certificados CNAME mantengan ECID y se utilicen como referencia para la identificación del visitante. Hay más información disponible en versiones sucesivas de la biblioteca ECID.

Adobe es consciente de que no todos los clientes de la biblioteca ECID utilizan CNAMES o Analytics. A todos los clientes de ECID se les ofrecerá una configuración de CNAME en un esfuerzo por utilizar la misma capacidad.

Si actualmente no está utilizando un CNAME para la implementación, puede iniciar el proceso hablando con el Servicio de atención al cliente.

## ¿Cuáles son los planes futuros de Adobe para la identificación de visitantes persistentes?

Las nuevas capacidades e implementaciones incluyen:

* Opciones de autoservicio de certificación CNAME en todas las soluciones de Adobe

* Métodos flexibles de recopilación de ID de visitante, BYOI (Traer su propia identidad) y recopilación de datos con prioridad de API

* Gráficos de identidad de Adobe Experience Platform

* Enfoque unificado para la recopilación de datos de Adobe

Adobe está comprometido con una personalización más precisa para los consumidores que desean una experiencia personalizada. Adobe se esfuerza por ofrecer a nuestros clientes una funcionalidad de identidad en línea que les ayuda a alinearse con las opciones de privacidad de sus clientes.

## Más información

Para obtener información, consulte:

* [Adobe Experience Cloud: Actualizaciones de cookies para Google Chrome](https://medium.com/adobetech/adobe-experience-cloud-cookie-updates-for-google-chrome-19ad67cf1598)

* [Impacto de Safari ITP 2.1 en Adobe Experience Cloud y clientes de la plataforma de experiencia](https://medium.com/adobetech/safari-itp-2-1-impact-on-adobe-experience-cloud-customers-9439cecb55ac)

