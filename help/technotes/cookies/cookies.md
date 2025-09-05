---
title: Adobe Analytics y cookies de explorador
description: Descubra cómo las medidas de prevención de seguimiento afectan a las cookies de terceros y de origen configuradas por Adobe Analytics.
feature: Data Configuration and Collection
exl-id: c4a4751e-49fc-40c3-aa39-f0f0b20bda1b
role: Admin
source-git-commit: fcc165536d77284e002cb2ba6b7856be1fdb3e14
workflow-type: tm+mt
source-wordcount: '1908'
ht-degree: 100%

---

# Adobe Analytics y cookies de explorador

Este documento explica cómo las medidas de prevención del seguimiento de los exploradores principales afectan a las cookies de terceros y de origen configuradas por Adobe Analytics. Incluye información sobre el programa Intelligent Tracking Prevention (ITP) de Apple, así como las limitaciones de Chrome en las cookies de terceros a través del atributo SameSite.

## ¿Cómo han limitado los exploradores el uso de cookies?

>[!NOTE]
>[Cross-Device Analytics](/help/components/cda/overview.md#cda) y [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html?lang=es#comparing-cja-to-traditional-adobe-analytics) pueden unir las cookies mediante un ID de persona, como un ID de inicio de sesión con hash, si hay uno disponible.

### Limitaciones de cookies de terceros

Las cookies utilizadas en un contexto de terceros están en desuso. Firefox y Safari comenzaron a bloquear las cookies de terceros de forma predeterminada a partir de 2019 y 2020, respectivamente. Chrome ha anunciado que planea dejar de admitir cookies de terceros en algún momento en 2023. Cuando lo hagan, las cookies de terceros no se podrán utilizar de forma eficaz.

Además, Chrome actualmente solo permite que las cookies funcionen en un contexto de terceros si tienen el atributo SameSite establecido en Ninguno y las están etiquetadas como seguras, lo que significa que solo pueden utilizarse en HTTPS. Encontrará más información en la sección [Qué es el atributo de cookie SameSite y cómo afecta a Analytics](#samesite-effect).

#### ¿Qué cookies de terceros de Adobe se ven afectadas?

El servicio de ID de visitante utiliza la cookie [demdex.net](https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html?lang=es) para proporcionar un identificador persistente para los visitantes en los distintos dominios de los clientes. En el servicio de ID de Analytics heredado, la cookie &quot;s_vi&quot;, se establece como una cookie de terceros para implementaciones que no utilizan un dominio de colección CNAME personalizado.

En los exploradores en los que están bloqueadas las cookies de terceros, el seguimiento entre dominios no está disponible.

### Limitaciones de cookies de origen {#limitations-first-party-cookies}

Las cookies de origen están permitidas en todos los exploradores principales. Sin embargo, Apple limita la duración de las cookies de origen configuradas por Adobe a través de su Intelligent Tracking Program (ITP). Esto afecta a Safari, así como a todos los exploradores de iOS y iPadOS.

Las cookies de origen de Adobe están limitadas a una caducidad de 7 días o, para los clics que Apple determina que provienen de rastreadores, a una caducidad de 24 horas. Con una caducidad de 7 días, si un usuario visita su sitio y regresa en un plazo de siete días, la fecha de caducidad de la cookie se amplía otros siete días. Sin embargo, si un usuario visita su sitio y regresa en ocho días, se trata como un nuevo usuario en la segunda visita.

Actualmente, las políticas de ITP se aplican a todas las cookies de origen configuradas por Adobe, tanto si utiliza el servicio de ID de visitante como el ID de Analytics heredado (cookie &quot;s_vi&quot;). En un momento dado, estas políticas se aplicaban únicamente a las cookies configuradas del lado del cliente y no a las cookies configuradas del lado del servidor mediante una implementación CNAME. Sin embargo, en noviembre de 2020, ITP se actualizó para aplicarse también a implementaciones CNAME.

#### Cronología de los cambios más importantes en la directiva de ITP {#ITP-timeline}

* Febrero de 2019 con [ITP 2.1](https://webkit.org/blog/8613/intelligent-tracking-prevention-2-1/): Las cookies del lado del cliente se limitaron a una caducidad de siete días
* Abril de 2019 con [ITP 2.2](https://webkit.org/blog/8828/intelligent-tracking-prevention-2-2/): Las cookies del lado del cliente estaban limitadas a 24 horas en el caso de los clics de publicidad cuando el dominio de referencia estaba: a) involucrado en el seguimiento entre sitios y b) la dirección URL final contenía una cadena de consulta o un identificador de fragmento.
* Noviembre de 2020 con [CNAME Cloaking and Bounce Tracking Defense](https://webkit.org/blog/11338/cname-cloaking-and-bounce-tracking-defense/): Las limitaciones de ITP se ampliaron a las implementaciones de CNAME.

Las políticas de ITP evolucionan con frecuencia. Para ver las políticas más recientes, consulte [Tracking Prevention de Apple en Webkit](https://webkit.org/tracking-prevention).

#### ¿Qué cookies de origen de Adobe se ven afectadas?

Todas las cookies de origen configuradas por Adobe y las bibliotecas de JavaScript relacionadas se ven afectadas por las políticas de ITP:

* [cookies &quot;AMCV&quot;](https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html?lang=es) establecidas por la biblioteca del servicio de ECID (Adobe Experience Cloud ID)
* La [cookie &quot;s_vi&quot;](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-analytics.html?lang=es) heredada de Analytics cuando se configura con la recopilación de datos de origen mediante un CNAME
* La cookie [&quot;s_fid&quot; heredada de Analytics](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-analytics.html?lang=es), que es la cookie de reserva que se usa cuando &quot;s_vi&quot; no se puede configurar

#### ¿Cuál es el impacto de ITP en Safari para Analytics?

El impacto de las limitaciones de ITP puede variar significativamente, según el comportamiento de los usuarios. Solo se ven afectados los visitantes que utilizan un explorador afectado por el ITP (por ejemplo, Safari) y regresan después de una ausencia de siete días. Si los visitantes no utilizan un explorador de ITP o regresan en un plazo de siete días, no se verán afectados. Es importante revisar sus propios datos en Analytics para comprender el alcance de esta limitación. Para obtener sugerencias sobre cómo medir el impacto en sus sitios, consulte [¿Cómo puedo determinar si los cambios de Safari afectan a mi negocio?](#measure-itp-effect).

Si estas limitaciones afectan a sus datos, verá esto:

1. El aumento en el recuento de visitantes como visitantes que vuelven y se tratan como nuevos visitantes porque sus cookies han caducado. Las métricas basadas en la métrica Visitante (como Ventas por Visitante) también se ven afectadas.
2. Cambios en la atribución. La atribución depende de que el mismo visitante vincule eventos de conversión a actividades anteriores. Una vez que caduca una cookie, los eventos posteriores se asocian con un visitante nuevo. Las actividades del nuevo visitante no se pueden asociar a las actividades del visitante anterior.

>[!NOTE]
>
>Actualmente, las tecnologías de ITP no se aplican a los exploradores incrustados en aplicaciones móviles.

## ¿Qué diferencia hay entre las cookies de terceros y las cookies de origen?

### Cookies de terceros

Los sitios web que visitan los usuarios no crean cookies de terceros.

Aunque los exploradores tratan todas las cookies de terceros de la misma manera y las almacenan en consecuencia, las cookies de terceros pueden comportarse de manera diferente e importante. Con la implementación de cookies de terceros de Analytics de un cliente, los navegadores almacenan el ID de Adobe [demdex.net](https://experienceleague.adobe.com/docs/audience-manager/user-guide/reference/demdex-calls.html?lang=es) como una cookie de terceros, pero el cliente solo realiza llamadas de Adobe y no a dominios de terceros desconocidos o sospechosos. Esta cookie proporciona identificadores persistentes entre dominios y permite el uso de contenido seguro (https). Para obtener más información, consulte [Cookies y el servicio de identidad de Experience Platform](https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html?lang=es).

Dentro de las implementaciones de Analytics, las cookies de terceros se utilizan para el seguimiento entre dominios y para casos de uso de publicidad, incluida la resegmentación de anuncios. Las cookies de terceros le permiten identificar a los visitantes a medida que visitan diferentes dominios de su propiedad o a medida que se muestran anuncios en sitios que no son de su propiedad.<!--  Without these cookies, you cannot identify visitors as they visit different domains that you own or as they are shown ads on sites that you do not own unless your implementation can stitch other types of cookies and   -->

### Cookies de origen

Las cookies de origen son específicas del dominio y las crean los sitios web de los clientes y se almacenan en los exploradores de los clientes a medida que los usuarios visitan los sitios web. Por lo general, todos los exploradores aceptan cookies de origen, aunque [Safari limita la caducidad de algunos tipos de cookies de origen](#limitations-first-party-cookies).

Dentro de las implementaciones de Analytics, las cookies de origen se utilizan para identificar a los usuarios cuando están en el sitio y, por lo tanto, admiten todo el análisis de la actividad del usuario. No necesita cookies de terceros para comprender la actividad en el sitio.

Para obtener más información, consulte [Acerca de las cookies de origen](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-first-party.html?lang=es).

![Comparación de cookies](/help/technotes/assets/cookies2.png)

## ¿Qué es el atributo de cookie SameSite y cómo afecta a las cookies de Analytics?  {#samesite-effect}

Con el lanzamiento del explorador Chrome 80 en febrero de 2020 (y las versiones sucesivas de Firefox y los exploradores Edge), el atributo de cookie SameSite fuerza la especificación de tres valores diferentes que rigen si las cookies se pueden usar en un contexto de terceros:

* `None`: esta configuración habilita el acceso entre sitios y permite que las cookies se pasen en un contexto de terceros. Para especificar este atributo, también debe especificar `Secure` y todas las solicitudes del explorador deben seguir HTTPS. Por ejemplo, al configurar la cookie, empareja los valores del atributo de la siguiente manera: `Set-Cookie: example_session=test12; SameSite=None; Secure`. Si no se etiquetan correctamente, las cookies no se pueden utilizar en los exploradores más recientes y se rechazarán.

* `Lax`: permite que las solicitudes entre sitios se envíen con cookies del mismo sitio únicamente para las navegaciones de nivel superior con métodos HTTP *seguros* (solo de lectura como `GET`).

* `Strict`: la cookie del mismo sitio no se envía para ninguna solicitud de sitio web de terceros. La cookie solo se envía si el sitio de la cookie coincide con el sitio de la barra URL.

El comportamiento predeterminado en estas versiones del explorador es tratar las cookies que no tienen un `SameSite` atributo especificado de la misma manera que `SameSite=Lax`.

### ¿Cómo administra Analytics los atributos de cookies de SameSite?

Para los clientes que utilizan el servicio de ID de visitante, las cookies tienen las propiedades `SameSite=None` y `secure` configuradas de forma predeterminada, lo que permite que estas cookies admitan casos de uso de terceros.

Para los clientes que utilizan identificadores heredados de Analytics (`s_vi` y cookies `s_fid`), también se establecen cookies para habilitar casos de uso de terceros con dominios de colección estándar: `adobedc.net`, `2o7.net` y `omtrdc.net`. Para los clientes que utilizan una implementación CNAME, Analytics establece `SameSite=Lax`.

>[!NOTE]
>
>Sin embargo, si es propietario de varios dominios y utiliza el mismo CNAME para la recopilación de datos en todos los dominios, este se trata como una cookie de terceros en esos otros dominios. Si utiliza los identificadores de Analytics heredados, es posible que desee actualizar la configuración a `SameSite=None` para que estas cookies se puedan compartir en sus sitios. Consulte [Cambiar el valor de SameSite cuando utilice un CNAME para varios dominios](#samesite-one-cname) en la siguiente sección para obtener más información.

En el caso de los exploradores que Google ha identificado como cookies mal gestionadas cuando `SameSite` se establece en `None`, `SameSite` no se configurará.

La siguiente tabla resume los atributos SameSite de las cookies de Analytics:

![Tabla de cookies](/help/technotes/assets/cookies1.png)

### ¿Cómo puedo cumplir los requisitos de dirección del sitio para el atributo SameSite?

#### Proporcione todas las páginas del sitio con HTTPS

Confirme que la configuración de JavaScript utiliza HTTPS para todas las llamadas a los servicios de Adobe.

Si su sitio utiliza el servicio de ID de visitante de Experience Cloud, el servicio redirige las llamadas HTTP de terceros a su extremo HTTPS, lo que puede aumentar la latencia, pero significa que no es necesario que cambie la configuración.

#### Cambie el valor SameSite cuando utilice un CNAME para varios dominios {#samesite-one-cname}

>[!NOTE]
>
>La siguiente información pertenece únicamente a los sitios que no utilizan el servicio de ID de visitante de Experience Cloud.

Si tiene una implementación CNAME configurada en el mismo dominio que su sitio web, la cookie se crea en un contexto de origen y no necesita hacer cambios.

Sin embargo, si es propietario de varios dominios y utiliza el mismo CNAME para la recopilación de datos en todos los dominios, esta cookie se trata como una cookie de terceros en esos otros dominios. Con Chrome 80 y versiones posteriores, ya no es visible en estos otros dominios. Para que el comportamiento sea más similar entre los exploradores, Analytics establece explícitamente el valor `SameSite` de esta cookie `Lax`. Si utiliza esta cookie en un contexto de terceros sencillo, deberá tener la cookie configurada con el valor `SameSite=None`, lo que también significa que siempre debe utilizar HTTPS. Si aún no lo ha hecho, póngase en contacto con el Servicio de atención al cliente de Adobe para que se cambie el valor SameSite para sus CNAME seguros.

## ¿Cómo puedo determinar si los cambios de Safari afectan a mi empresa?  {#measure-itp-effect}

Adobe recomienda que los clientes midan el impacto dentro de su propia compañía antes de cambiar la recopilación de datos. Puede usar Analysis Workspace para medir el impacto de la prevención del seguimiento de ITP en su compañía individual:

* Mida el porcentaje de tráfico de los exploradores controlados por ITP:

   1. Cree un segmento para ver cuántos visitantes utilizan una plataforma de ITP.

      >[!NOTE]
      >
      >Los exploradores específicos afectados por ITP dependen de si estaba utilizando una implementación CNAME. Consulte [Cronología de los cambios más importantes en la directiva de ITP](#ITP-timeline) para obtener más información.

      ![Segmento para visitantes de ITP](/help/technotes/assets/itp-visitor-segment.png)

   2. Aplique el segmento al número de visitas para comprender el uso relativo de Safari en su base de usuarios. Esto permite crear una tabla como esta:

      ![Porcentaje de visitas de visitantes de ITP](/help/technotes/assets/visits-vs-safari-visits.png)

* Mida el porcentaje de visitantes que utilizan exploradores que no son de Safari y que no regresan en un plazo de siete días. Si los visitantes regresan repetidamente en un plazo de siete días, es posible que el tráfico de Safari no se vea afectado de manera significativa.

   1. Cree un segmento como el siguiente para el tráfico que no sea de Safari.

      ![Segmento para visitantes que regresan después de siete días](/help/technotes/assets/visits-after-seven-days.png)

   2. Aplique el segmento al número de visitas para comprender el uso relativo de Safari en su base de usuarios. Esto permite crear una tabla como esta:

      ![Porcentaje de visitantes que regresan después de siete días](/help/technotes/assets/percent-visits-after-seven-days.png)

### Formas de ajustar los datos durante la creación de informes

Si su empresa se ve afectada por la prevención del seguimiento de ITP, puede considerar las siguientes medidas para ajustar sus datos durante la creación de informes.

* Cree un segmento para filtrar los usuarios de ITP.

  ![Segmento para visitantes que no son de ITP](/help/technotes/assets/non-itp-visitor-segment.png)

* Cree una métrica calculada para ajustar la inflación de visitantes conocida.

  ![Métrica calculada para ajustar la inflación de visitantes](/help/technotes/assets/estimated-itp-visitors-metric.png)

>[!MORELIKETHIS]
>
>[Opciones para mitigar el efecto de las limitaciones de cookies del explorador](cookieless.md)
>>[El impacto del nuevo marco de trabajo de transparencia de seguimiento de aplicaciones de Apple en Adobe Analytics](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-discussions/the-impact-of-apple-s-new-app-tracking-transparency-framework-on/td-p/401833?profile.language=es)
