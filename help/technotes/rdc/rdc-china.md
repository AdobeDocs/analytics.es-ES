---
title: Recopilación de datos regionales para China
seo-title: Adobe Analytics China RDC
description: null
seo-description: null
translation-type: tm+mt
source-git-commit: ee0cb9b64a3915786f8f77d80b55004daa68cab6

---


# Recopilación de datos regionales para China

La recopilación de datos regionales (RDC, Regional Data Collection) de Adobe en China continental permite a los clientes en dicha zona enviar datos directamente a un centro de recogida de datos (DCC, Data Collection Center) en China, en lugar de a otras ubicaciones del mundo. Esto mejora los tiempos de carga de la página y la precisión de los datos en comparación con el envío de los mismos a los centros de recopilación de datos fuera de China.

> [!IMPORTANT] Existe un costo adicional asociado al uso del nodo RDC China. Antes de implementar la recopilación de datos en China utilizando el nodo RDC descrito en este documento, comuníquese con el administrador de cuentas de su organización para asegurarse de tener derecho a esta funcionalidad.

## Configuración del servidor de seguimiento para China

El seguimiento puede realizarse en la recopilación de datos regionales de China en cualquier momento que sea adecuado para su servicio. Para cualquier propiedad digital (como una aplicación móvil o una página web) que desee enrutar a RDC China, cambie el servidor de seguimiento a:

`<namespace>.sc.adobedc.cn`

Asegúrese de insertar el espacio de nombres correspondiente. Generalmente se encuentra al principio del servidor de seguimiento existente. For example: `<namespace>.sc.adobedc.cn` - although any namespace value will work. También puede asignar un registro [CNAME](https://marketing.adobe.com/resources/help/en_US/whitepapers/first_party_cookies/fpcookies_cname.html) propio sin SSL a esta nueva ubicación.

No establezca el valor de trackingserver globalmente, para todas las propiedades y regiones geográficas, en la RDC China si alguna parte sustancial de la base de clientes está fuera de China. Solo debe establecer el trackingServer en el valor RDC de China para los clientes que se encuentren en China. De lo contrario, afectará negativamente a la velocidad de los usuarios fuera de China, ya que obliga a la recopilación de datos a ir a China y volver para obtener una respuesta.

## Identificación de usuarios en China

Independientemente de la ubicación de la propiedad digital, o del idioma que utilice, los usuarios en China experimentarán mejoras si utiliza el nodo RDC en China. Por lo tanto, la práctica recomendada es determinar qué usuarios están ubicados en China y utilizar la RDC de China para dichos usuarios. Métodos para ayudarle a identificar a estos usuarios:

* Uso de una solución geoip fiable. Es posible que decida utilizar una solución del lado del servidor para integrarse fácilmente con el lanzamiento de la plataforma de Adobe Experience (o Administración de etiquetas de datos). En este caso, la ubicación se puede determinar incluyendo un elemento de datos estándar en el objeto Launch Platform Launch o DTM. O bien, puede utilizar una solución de GeoIP del lado del cliente. En este caso, Launch Platform Launch se puede situar en el código del lado del cliente. Tenga en cuenta que estas soluciones podrían implicar que el usuario navegue hasta el sitio localizado. Esto supone un riesgo de que el servidor de seguimiento global y la segunda página cuenten la primera página en China, lo que puede resultar en una visita doble. Siga las prácticas recomendadas para las soluciones GeoIP. Adobe no es responsable de la precisión de la solución GeoIP que utilice.

* Using site structure or the browser language (the `navigator.language / accept-language` header). La ventaja de este método es que reduce el coste y, posiblemente, mejora el rendimiento. La desventaja de este método es que los visitantes que hablan chino y que realizan la visita desde fuera de China están sujetos a velocidades deterioradas.
* Uso de una solución de alojamiento basada en China y configuración del servidor trackingserver a RDC China basado en su host. Esto también aumenta considerablemente la velocidad.

## Limitaciones actuales

Las limitaciones actuales de RDC China:

1. China RDC does not support first party SSL ([s.trackingServerSecure](https://helpx.adobe.com/analytics/kb/determining-data-center.html) in your JavaScript), or [Server-Side Forwarding](https://marketing.adobe.com/resources/help/en_US/reference/ssf.html) to Adobe Audience Manager.
2. A pesar de que [A4T](https://marketing.adobe.com/resources/help/en_US/target/a4t/a4t.html) y [ECID](https://marketing.adobe.com/resources/help/en_US/mcvid/) son compatibles, los dominios Target y Demdex no se encuentran actualmente en China continental, por lo que no tienen los mismos beneficios de velocidad y fiabilidad que aquellos que se encuentran en la RDC de China.

## Compromiso de Adobe con China

Adobe tiene previsto mantener de forma permanente la recopilación de datos regionales de China y, con el tiempo, añadir la compatibilidad con funciones como SSL de origen y de reenvío de servidor. Además, Adobe prevé proporcionar un dominio demdex (o equivalente) en China para admitir totalmente la recopilación de ECID y Audience Manager desde China. Los clientes que comiencen a utilizar la RDC de Adobe en China pueden seguir utilizando este extremo de recopilación de datos de manera indefinida.
