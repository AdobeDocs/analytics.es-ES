---
title: Adobe Analytics y cookies de explorador
description: Descubra cómo las medidas de prevención de seguimiento afectan a las cookies de terceros y de origen configuradas por Adobe Analytics.
translation-type: tm+mt
source-git-commit: 07c76cea1f6fd64957fd4fd20bc5187976f3c14c
workflow-type: tm+mt
source-wordcount: '1887'
ht-degree: 7%

---


# Adobe Analytics y cookies de explorador

Este documento explica cómo las medidas de prevención del seguimiento de los exploradores principales afectan a las cookies de terceros y de origen configuradas por Adobe Analytics. Incluye información sobre el programa Intelligent Tracking Prevention (ITP) de Apple, así como las limitaciones de Chrome en las cookies de terceros a través del atributo SameSite.

## ¿Cómo han limitado los exploradores el uso de cookies?

### Limitaciones de cookies de terceros

Las cookies utilizadas en un contexto de terceros están en desuso. Firefox y Safari comenzaron a bloquear las cookies de terceros de forma predeterminada a partir de 2019 y 2020, respectivamente. Chrome ha anunciado que planea dejar de admitir cookies de terceros en algún momento de 2022. Cuando lo hacen, las cookies de terceros no se pueden utilizar de forma eficaz.

Además, Chrome actualmente solo permite que las cookies funcionen en un contexto de terceros si tienen el atributo &quot;SameSite&quot; establecido en None y las están etiquetadas como seguras, lo que significa que solo pueden utilizarse en HTTPS. Encontrará más información en la sección &quot;[Qué es el atributo de cookie SameSite y cómo afecta a Analytics?](#samesite-effect)&quot;

#### ¿Qué cookies de terceros de Adobe se ven afectadas?

El servicio de ID de visitante utiliza la cookie [`demdex.net`](https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html) para proporcionar un identificador persistente para los visitantes entre distintos dominios de clientes. En los exploradores en los que están bloqueadas las cookies de terceros, el seguimiento entre dominios no está disponible.

### Limitaciones de cookies de origen {#limitations-first-party-cookies}

Las cookies de origen están permitidas en todos los exploradores principales. Sin embargo, Apple limita la duración de las cookies de origen configuradas por Adobe a través de su Programa de seguimiento inteligente (ITP). Esto incluye Safari en MacOS y todos los navegadores en iOS y iPadOS.

Las cookies de origen de Adobe están limitadas a una caducidad de 7 días o de 24 horas para las pulsaciones que Apple determina que provienen de los rastreadores. En el caso de una caducidad de 7 días, si un usuario visita su sitio y luego regresa dentro de esos siete días, la fecha de caducidad de la cookie se amplía otros siete días. Sin embargo, si un usuario visita su sitio y luego regresa en ocho días, se trata como un nuevo usuario en la segunda visita.

Actualmente, las políticas de ITP se aplican a todas las cookies de origen configuradas por Adobe, tanto si utiliza el servicio de ID de visitante como el ID de Analytics heredado (cookie &quot;s_vi&quot;). En un momento dado, estas políticas se aplicaban únicamente a las cookies configuradas del lado del cliente y no a las cookies configuradas del lado del servidor mediante una implementación CNAME. Sin embargo, en noviembre de 2020, ITP se actualizó para aplicarse también a implementaciones CNAME.

#### Cronología de los cambios más importantes en la política de ITP

* Febrero de 2019 con [ITP 2.1](https://webkit.org/blog/8613/intelligent-tracking-prevention-2-1/): Las cookies del lado del cliente se limitaron a una caducidad de siete días
* Abril de 2019 con [ITP 2.2](https://webkit.org/blog/8828/intelligent-tracking-prevention-2-2/): Las cookies del lado del cliente estaban limitadas a 24 horas para los clics de publicidad cuando el dominio de referencia estaba a) involucrado en el seguimiento entre sitios y b) la dirección URL final contenía una cadena de consulta y/o un identificador de fragmento.
* Noviembre de 2020 con [CNAME Cloaking and Bounce Tracking Defence](https://webkit.org/blog/11338/cname-cloaking-and-bounce-tracking-defense/): Las limitaciones de ITP se ampliaron a las implementaciones de CNAME.

Las políticas de ITP evolucionan con frecuencia. Para ver las políticas más recientes, consulte [Prevención de seguimiento en Webkit](https://webkit.org/tracking-prevention).

#### ¿Qué cookies de origen de Adobe se ven afectadas?

Todas las cookies de origen configuradas por Adobe y las bibliotecas de JavaScript relacionadas se ven afectadas por las políticas de ITP:

* [`AMCV` ](https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html) cookies establecidas por la biblioteca del servicio de ID de visitante (ECID) de Adobe Experience Cloud
* La cookie [`s_vi` heredada de Analytics](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-analytics.html) cuando se configura con recopilación de datos de origen mediante un CNAME
* La cookie [`s_fid` heredada de Analytics](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-analytics.html), que es la cookie de reserva que se usa cuando `s_vi` no se puede configurar

#### ¿Cuál es el impacto de ITP en Safari para Analytics?

El impacto de las limitaciones de ITP variará significativamente, según el comportamiento de los usuarios. Solo se ven afectados los visitantes que utilizan un explorador afectado por ITP (es decir, Safari) y regresan después de una ausencia de siete días. Si los visitantes no utilizan un explorador ITP o regresan en un plazo de siete días, no se verán afectados. Es importante revisar sus propios datos en Analytics para comprender el alcance de esta limitación. Para obtener sugerencias sobre cómo medir el impacto en sus sitios, consulte &quot;[¿Cómo puedo determinar si los cambios de Safari afectan a mi negocio?](#measure-itp-effect)&quot;

Si estas limitaciones afectan a sus datos, verá:

1. El aumento en el recuento de visitantes como visitantes que retornan se tratan como nuevos visitantes porque sus cookies han caducado. Las métricas basadas en la métrica Visitante (como Ventas por Visitante) también se ven afectadas.
2. Cambios en la atribución. Los eventos de conversión están vinculados a las actividades anteriores por el mismo visitante. Una vez que caduca una cookie, los eventos futuros se asocian con un visitante nuevo y las conversiones no se pueden asociar al visitante original.

>[!NOTE]
>
>Actualmente, las tecnologías ITP no se aplican a los navegadores incrustados en aplicaciones móviles.

## ¿Qué diferencia hay entre las cookies de terceros y las cookies de origen?

### Cookies de terceros

Los sitios web que visitan los usuarios no crean cookies de terceros.

Aunque los exploradores tratan todas las cookies de terceros de la misma manera y las almacenan en consecuencia, las cookies de terceros pueden comportarse de diferentes maneras. Con la implementación de cookies de terceros de Analytics de un cliente, los navegadores almacenan el ID de Adobe [demdex.net](https://experienceleague.adobe.com/docs/audience-manager/user-guide/reference/demdex-calls.html) como una cookie de terceros, pero el cliente solo realiza llamadas de Adobe y no a dominios de terceros desconocidos o sospechosos. Esta cookie proporciona identificadores persistentes entre dominios y permite el uso de contenido seguro (HTTPS). Para obtener más información, consulte [Cookies y el servicio de identidad de Experience Platform](https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html).

Dentro de las implementaciones de Analytics , las cookies de terceros se utilizan para el seguimiento entre dominios y para casos de uso de publicidad, incluida la reorientación de anuncios. Las cookies de terceros le permiten identificar a los visitantes a medida que visitan diferentes dominios de su propiedad o a medida que se muestran anuncios en sitios que no es de su propiedad.<!--  Without these cookies, you cannot identify visitors as they visit different domains that you own or as they are shown ads on sites that you do not own unless your implementation can stitch other types of cookies and   -->

### Cookies de origen

Las cookies de origen son específicas del dominio y las crean los sitios web de los clientes y se almacenan en los navegadores de los clientes a medida que los usuarios visitan los sitios web. Por lo general, todos los exploradores aceptan cookies de origen, aunque [Safari limita la caducidad de algunos tipos de cookies de origen](#limitations-first-party-cookies).

Dentro de las implementaciones de Analytics, las cookies de origen se utilizan para identificar a los usuarios cuando están en el sitio y, por lo tanto, admiten todo el análisis de la actividad del usuario. No necesita cookies de terceros para comprender la actividad en el sitio.

Para obtener más información, consulte [Acerca de las cookies de origen](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-first-party.html).

![Comparación de cookies](/help/technotes/assets/cookies2.png)

## ¿Qué es el atributo de cookie SameSite y cómo afecta a las cookies de Analytics? {#samesite-effect}

Con el lanzamiento del explorador Chrome 80 en febrero de 2020 (y las versiones sucesivas de Firefox y los exploradores Edge), el atributo de cookie SameSite fuerza la especificación de tres valores diferentes para controlar el comportamiento de las solicitudes entre sitios:

* `None`: esta configuración habilita el acceso entre sitios y permite que las cookies se pasen en un contexto de terceros. Para especificar este atributo, también debe especificar `Secure` y todas las solicitudes del explorador deben seguir HTTPS. Por ejemplo, al configurar la cookie, empareja los valores del atributo de la siguiente manera: `Set-Cookie: example_session=test12; SameSite=None; Secure`. Si no se etiquetan correctamente, las cookies no se pueden utilizar en los exploradores más recientes y se rechazan.

* `Lax`: Permite que las solicitudes entre sitios se envíen con cookies del mismo sitio solo para la navegación de nivel superior con métodos HTTP  *seguros*  (solo lectura, como  `GET`).

* `Strict`: la cookie del mismo sitio no se envía para ninguna solicitud de sitio web de terceros. La cookie solo se envía si el sitio de la cookie coincide con el sitio de la barra URL.

El comportamiento predeterminado en estas versiones del explorador es tratar las cookies que no tienen un `SameSite` atributo especificado de la misma manera que `SameSite=Lax`.

### ¿Cómo administra Analytics los atributos de cookies de SameSite?

Todas las actualizaciones de cookies de Adobe se gestionan mediante servidores de Adobe, y los servidores Edge de Adobe establecen los atributos de cookies adecuados. Todas las cookies de terceros se actualizaron en el servidor con los atributos adecuados. Sus sitios no necesitan actualizaciones de JavaScript.

Esta actualización por parte de los servidores Edge de Adobe se produjo automáticamente cuando los usuarios visitaron cualquier sitio web donde se usara la cookie. Para la mayoría de los productos de Adobe, las cookies tenían los indicadores adecuados cuando Chrome 80 se lanzó en 2020. La excepción eran las implementaciones de Adobe Analytics que usan recopilación de datos de terceros y no usan el servicio de ID de visitante de Experience Cloud. Para este tipo de implementación, debe solicitar al Servicio de atención al cliente que cambie los indicadores; consulte &quot;[Cambiar el valor SameSite cuando utilice un CNAME para varios dominios](#samesite-one-cname)&quot; en la siguiente sección para obtener más información. Hasta que se cambie el indicador, estos clientes podrán experimentar un pequeño aumento temporal de nuevos visitantes que, de lo contrario, se etiquetarían como visitantes que repiten.

En el caso de los exploradores que Google ha identificado como cookies mal gestionadas cuando `SameSite` está configurado en `None`, `SameSite` no se ha configurado correctamente.

La siguiente tabla resume los atributos SameSite de las cookies de Analytics:

![Tabla de cookies](/help/technotes/assets/cookies1.png)

### ¿Cómo puedo cumplir los requisitos de dirección del sitio para el atributo SameSite?

#### Proporcione todas las páginas del sitio con HTTPS

Confirme que la configuración de JavaScript utiliza HTTPS para todas las llamadas a los servicios de Adobe.

Si su sitio utiliza el servicio de ID de visitante de Experience Cloud, el servicio redirige las llamadas HTTP de terceros a su extremo HTTPS, lo que puede aumentar la latencia pero significa que no es necesario que cambie la configuración.

#### Cambie el valor SameSite cuando utilice un CNAME para varios dominios {#samesite-one-cname}

>[!NOTE]
>
>La siguiente información pertenece únicamente a los sitios que no utilizan el servicio de ID de visitante de Experience Cloud.

Si tiene una implementación CNAME configurada en el mismo dominio que su sitio web, la cookie se crea en un contexto de origen y no necesita realizar cambios.

Sin embargo, si es propietario de varios dominios y utiliza el mismo CNAME para la recopilación de datos en todos los dominios, la cookie se trata como una cookie de terceros en esos otros dominios. Con Chrome 80 y versiones posteriores, ya no es visible en estos otros dominios. Para que el comportamiento sea más similar en todos los navegadores, Analytics ha establecido explícitamente el valor `SameSite` de esta cookie como `Lax`. Si utiliza esta cookie en un contexto de terceros sencillo, debe tener la cookie configurada con el valor `SameSite=None` , lo que también significa que siempre debe utilizar HTTPS. Si aún no lo ha hecho, póngase en contacto con el Servicio de atención al cliente de Adobe para que se cambie el valor SameSite para sus CNAME seguros.

## ¿Cómo puedo determinar si los cambios de Safari afectan a mi negocio? {#measure-itp-effect}

Adobe recomienda que los clientes midan el impacto dentro de su propia empresa antes de cambiar la recopilación de datos. Puede usar Analysis Workspace para medir el impacto de la prevención del seguimiento de ITP en su negocio individual:

* Mida el porcentaje de tráfico de los navegadores controlados por ITP:

   1. Cree un segmento para ver cuántos visitantes utilizan una plataforma ITP.

      ![Segmento para visitantes de ITP](/help/technotes/assets/itp-visitor-segment.png)

   2. Aplique el segmento al número de visitas para comprender el uso relativo de Safari en su base de usuarios. Esto le permite crear una tabla como esta:

      ![Porcentaje de visitas de visitantes de ITP](/help/technotes/assets/visits-vs-safari-visits.png)

* Mida el porcentaje de visitantes que utilizan navegadores que no son de Safari y que no regresan en un plazo de siete días. Si los visitantes que no son de Safari regresan repetidamente en un plazo de siete días, es posible que el tráfico de Safari no se vea afectado de manera significativa.

   1. Cree un segmento como el siguiente para el tráfico que no sea de Safari.

      ![Segmento para visitantes que regresan después de siete días](/help/technotes/assets/visits-after-seven-days.png)

   2. Aplique el segmento al número de visitas para comprender el uso relativo de Safari en su base de usuarios. Esto le permite crear una tabla como esta:

      ![Porcentaje de visitantes que regresan después de siete días](/help/technotes/assets/percent-visits-after-seven-days.png)

### Formas de ajustar los datos durante el sistema de informes

Si su negocio se ve afectado por la prevención del seguimiento de ITP, puede considerar las siguientes medidas para ajustar sus datos durante el sistema de informes.

* Cree un segmento para filtrar los usuarios de ITP.

   ![Segmento para visitantes que no son de ITP](/help/technotes/assets/non-itp-visitor-segment.png)

* Cree una métrica calculada para ajustar la inflación de visitantes conocida.

   ![Métrica calculada para ajustar la inflación de visitantes](/help/technotes/assets/estimated-itp-visitors-metric.png)

>[!MORELIKETHIS]
>
>[Opciones para mitigar el efecto de las limitaciones de cookies del explorador](cookieless.md)
>[El impacto del nuevo marco de transparencia de seguimiento de aplicaciones de Apple en Adobe Analytics](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-discussions/the-impact-of-apple-s-new-app-tracking-transparency-framework-on/td-p/401833)
