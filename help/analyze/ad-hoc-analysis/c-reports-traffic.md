---
description: Las fuentes de tráfico ofrecen una descripción detallada sobre cómo los visitantes interactúan con el sitio web.
title: Informes de fuentes de tráfico
topic: Ad hoc analysis
uuid: 246afbdc-9f7b-4956-a44a-b7aad948f392
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Informes de fuentes de tráfico

Las fuentes de tráfico ofrecen una descripción detallada sobre cómo los visitantes interactúan con el sitio web.

## Informes de fuentes de tráfico {#concept_0F1772141E1345C5BCF63BE7C544C0CB}

Las fuentes de tráfico ofrecen una descripción detallada sobre cómo los visitantes interactúan con el sitio web.

Los informes de fuentes de tráfico permiten:

* Analizar aspectos críticos del comportamiento de visitante.
* Monitorear y comprender los patrones de tráfico.
* Determinar el contenido popular del sitio.
* visitantes de segmento según cualquier criterio que se pueda medir.

**Persistencia común**

En [!UICONTROL Traffic Sources], todos los valores del informe persisten y reciben crédito hasta que se sobrescriben o hasta que finaliza la visita, lo que suceda primero. Anteriormente, solo persistían las palabras clave y los dominios de referencia. Por ejemplo, si un visitante busca en Google la palabra  &quot;DVD&quot;, que les lleva al sitio, donde efectúan una compra de 100 $, el informe asigna un crédito de 100 $ a la palabra clave &quot;DVD&quot; y también al motor de búsqueda de Google. Este modo de funcionamiento es inalterable y no depende de la configuración de [!DNL Admin Console].

## Palabras clave de búsqueda {#concept_071FDCBD0A3B4242BA00744786D1C59C}

Muestra un desglose de palabras clave para Todas las búsquedas, Paga y Natural.

<!-- 

c_reports_search_keyword.xml

 -->

**[!UICONTROL Search Keywords - All]**:: Muestra un desglose de cada palabra clave de búsqueda que se ha utilizado para encontrar el sitio. Puede ordenar esta lista por vistas de página o palabras clave de búsqueda haciendo clic en el título de la columna encima del listado. Haga clic en la lupa al lado de una palabra clave de búsqueda para ver los resultados de búsqueda del sitio.

**[!UICONTROL Search Keywords - Paid]**:: Muestra un desglose de cada palabra clave de búsqueda paga que se utilizó para encontrar el sitio. Puede ordenar esta lista por vistas de página o palabras clave de búsqueda haciendo clic en el título de la columna encima del listado. Haga clic en la lupa al lado de una palabra clave de búsqueda para ver los resultados de búsqueda del sitio.

**[!UICONTROL Search Keywords - Natural]**:: Muestra un desglose de cada palabra clave de búsqueda natural que se utilizó para encontrar el sitio. Puede ordenar esta lista por vistas de página o palabras clave de búsqueda haciendo clic en el título de la columna encima del listado. Haga clic en la lupa al lado de una palabra clave de búsqueda para ver los resultados de búsqueda del sitio.

## Motores de búsqueda {#concept_351CDE4F5FC44371B6B657064E125134}

Muestran qué motores de búsqueda usan los visitantes, para todas las búsquedas, para las búsquedas de pago y para las búsquedas naturales.

<!-- 

c_reports_search_engines.xml

 -->

**[!UICONTROL Search Engines - All]**:: Muestra los motores de búsqueda utilizados para encontrar la página web. El gráfico muestra un desglose porcentual de los motores de búsqueda que se utilizan para encontrar el sitio.

**[!UICONTROL Search Engines - Paid]**:: Muestra los motores de búsqueda de palabras clave pagas que utilizan las personas para encontrar la página web. El gráfico muestra un desglose porcentual de los motores de búsqueda que se utilizan para encontrar el sitio.

**[!UICONTROL Search Engines - Natural]**:: Muestra los motores de búsqueda de palabras clave naturales utilizados para encontrar la página web. El gráfico muestra un desglose porcentual de los motores de búsqueda que se utilizan para encontrar el sitio.

## Dominios de referencia {#concept_804614DF21C14C9FB542451B30F92788}

<!-- 

c_reports_ref_domains.xml

 -->

Muestra los dominios que atrajeron a aquellos clientes que repercutieron más sobre las métricas de éxito del sitio. Los Remitentes del reenvío se dividen en dos categorías principales: Dominios y direcciones URL. Los dominios hacen referencia al nombre de dominio y aparecen como el dominio base sin la cadena de consulta o los subdirectorios adjuntos. Las direcciones URL incluyen el nombre de dominio base, así como cualquier cadena de consulta o subdirectorio.

## Dominios de referencia originales  {#concept_EB18251DF70343169B46BB59543A579A}

<!-- 

c_reports_original_ref_domains.xml

 -->

Muestra los remitentes del reenvío originales que produjeron los clientes en el sitio. Los clientes pueden visitar el sitio varias veces y tener un remitente del reenvío diferente para cada visita. Este informe muestra cómo fueron remitidos la primera vez que llegaron al sitio. Esto puede ayudarle a ver si siguieron utilizando el mismo remitente del reenvío y patrones de vista en la forma en que los clientes son remitidos a su sitio. Puede realizar la vista del número de visitantes generados por un remitente del reenvío original o averiguar cuántos ingresos generó cada remitente del reenvío original. Los informes de referentes se pueden rellenar cada vez que un visitante entra en el sitio, incluso si lo hace varias veces durante una sesión (antes de que la visita caduque).

## Referentes {#concept_40CF9C2D10B94E82819BC65A232F05C3}

Muestra el dominio o la dirección URL de donde provienen los visitantes antes de llegar al sitio, los métodos que utilizan los visitantes para encontrar el sitio web y el número de visitas al sitio provenientes de estas ubicaciones de referencia.

<!-- 

c_reports_referrers.xml

 -->

Por ejemplo: si un visitante hace clic en un vínculo del Sitio A y llega a su sitio, el Sitio A es el remitente del reenvío si no se define como parte de su dominio. Durante la implementación de informes y análisis de marketing, el consultor de implementación puede ayudarle a definir los dominios y las direcciones URL que forman parte del sitio web. (Este cambio se puede realizar después de la implementación).

Los dominios o las direcciones URL que no forman parte de esos dominios y direcciones URL definidos se consideran remitentes del reenvío. Por ejemplo, la página web A y la página web B se agregan al filtro interno de la dirección URL, pero la página web C no. En este caso, la página web C se considera un remitente del reenvío.

Consulte [Filtros de URL internos](https://docs.adobe.com/content/help/es-ES/analytics/admin/admin-tools/internal-url-filter-admin.translate.html) en la ayuda de [!DNL Admin Console] para obtener más información.

>[!NOTE] La función Marketing Reports and Analytics registra los dominios de referencia como correo electrónico cuando los visitantes llegan al sitio haciendo clic en un vínculo enviado por correo electrónico que contiene el protocolo [!DNL imap://] o [!DNL mail://]. Por ejemplo, todas las visitas procedentes de [!DNL https://mail.yahoo.com] no se cuentan como referente de correo electrónico, porque el protocolo es [!DNL https://]. Los mensajes de correo electrónico de Outlook se registran en la línea de direcciones escritas o marcadores, mientras que todos los referentes con protocolo HTTP cuyo dominio es un motor de búsqueda conocido se registran en la línea de motores de búsqueda.

## Tipo de referente {#concept_689E42D8F96C450DA41C7167C7388198}

Al realizar un seguimiento y registrar los sitios referentes de los visitantes permite averiguar, cómo descubrió el sitio el visitante en cada visita.

<!-- 

c_reports_ref_types.xml

 -->

La lista siguiente define los distintos tipos de referentes:

* *Otros remitentes del reenvío* del sitio web se registran cuando los visitantes hacen clic en un vínculo ubicado en una página de otro sitio web (no definido como parte del sitio) y llegan al sitio web.
* *Los remitentes del reenvío del motor* de búsqueda se registran cuando los visitantes utilizan un motor de búsqueda para acceder al sitio.
* *Se registran los remitentes del reenvío escritos o marcadores*

   * Si un visitante ingresa al sitio a través de un vínculo que no sea del explorador (por ejemplo, en un mensaje de correo electrónico).
   * Si un visitante escribe la URL de su sitio directamente en el explorador.
   * Si un visitante hace clic en un vínculo HTML de su disco duro personal.
   * Si un visitante accede al sitio seleccionando los marcadores del explorador.

**Definiciones**

Los siguientes elementos de línea podrían mostrarse al ejecutar este informe:

**Dentro de su sitio**: estos artículos son direcciones URL que son etiquetadas por los filtros de URL internos. Estos elementos no se contabilizan como “instancias de referente” pero se pueden ver en los informes de otras métricas.

**Sin JavaScript**: No había JavaScript, por lo que el tipo no se podía identificar (desconocido). Esto significa que un cliente no proporcionó información de remitente del reenvío en un explorador, lo cual no indica que sea capaz de admitir JavaScript. No se cuentan como &quot;instancias de remitente del reenvío&quot;, pero se pueden ver cuando se sistema de informes otras métricas.

**USENET (grupos de noticias)**: significa que la dirección URL de un referente empezaba por `news://`. Por lo tanto, el vínculo de referente se publicó en un grupo de noticias Usenet, en vez de en una página web.

>[!NOTE] La lógica de tipo de Remitente del reenvío coincide con otros informes de fuentes de tráfico (como [!UICONTROL Referrers] y [!UICONTROL Referring Domains]). This should reduce or eliminate the occurrences of the Inside Your Site and No JavaScript line items in the [!UICONTROL Referrer Type] report.

