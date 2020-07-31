---
description: Las fuentes de tráfico ofrecen una descripción detallada sobre cómo los visitantes interactúan con el sitio web.
title: Informes de fuentes de tráfico
topic: Ad hoc analysis
uuid: 246afbdc-9f7b-4956-a44a-b7aad948f392
translation-type: ht
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: ht
source-wordcount: '1159'
ht-degree: 100%

---


# Informes de fuentes de tráfico

Las fuentes de tráfico ofrecen una descripción detallada sobre cómo los visitantes interactúan con el sitio web.

## Informes de fuentes de tráfico {#concept_0F1772141E1345C5BCF63BE7C544C0CB}

Las fuentes de tráfico ofrecen una descripción detallada sobre cómo los visitantes interactúan con el sitio web.

Los informes de fuentes de tráfico permiten:

* Analizar aspectos importantes del comportamiento de los visitantes.
* Monitorear y comprender los patrones de tráfico.
* Determinar qué contenido del sitio es el más visto.
* Segmentar a los visitantes según cualquier criterio que pueda medirse.

**Modo de persistencia común**

En las [!UICONTROL fuentes de tráfico], todos los valores de los informes permanecen y reciben crédito hasta que resulten sobrescritos o hasta que termine la visita (lo que suceda primero). Antes, solo persistían los valores de Palabras clave y Dominios de referencia. Por ejemplo, si un visitante busca en Google la palabra &quot;DVD&quot;, que les lleva al sitio, donde efectúan una compra de 100 $, el informe asigna un crédito de 100 $ a la palabra clave &quot;DVD&quot; y también al motor de búsqueda de Google. Este modo de funcionamiento es inalterable y no depende de la configuración de [!DNL Admin Console].

## Palabras clave de búsqueda {#concept_071FDCBD0A3B4242BA00744786D1C59C}

Muestran un desglose de palabras clave para todas las búsquedas, para las búsquedas pagas y para las búsquedas naturales.

<!-- 

c_reports_search_keyword.xml

 -->

**[!UICONTROL Palabras clave de búsqueda - Todas]**: muestra un desglose de todas las palabras clave de búsqueda que se han utilizado para encontrar el sitio. Para ordenar esta lista según las vistas de las páginas o las palabras clave de búsqueda, haga clic en el título de la columna que se encuentra sobre la lista. Haga clic en la lupa situada al lado de la palabra clave de búsqueda para ver los resultados de búsqueda correspondientes al sitio.

**[!UICONTROL Palabras clave de búsqueda: Pagado]**: muestra un desglose de cada palabra clave de búsqueda pagada que se utilizó para encontrar el sitio. Para ordenar esta lista según las vistas de las páginas o las palabras clave de búsqueda, haga clic en el título de la columna que se encuentra sobre la lista. Haga clic en la lupa situada al lado de la palabra clave de búsqueda para ver los resultados de búsqueda correspondientes al sitio.

**[!UICONTROL Palabras clave de búsqueda: Natural]**: muestra un desglose de cada palabra clave de búsqueda natural que se utilizó para encontrar el sitio. Para ordenar esta lista según las vistas de las páginas o las palabras clave de búsqueda, haga clic en el título de la columna que se encuentra sobre la lista. Haga clic en la lupa situada al lado de la palabra clave de búsqueda para ver los resultados de búsqueda correspondientes al sitio.

## Motores de búsqueda {#concept_351CDE4F5FC44371B6B657064E125134}

Muestran qué motores de búsqueda usan los visitantes, para todas las búsquedas, para las búsquedas de pago y para las búsquedas naturales.

<!-- 

c_reports_search_engines.xml

 -->

**[!UICONTROL Motores de búsqueda: Todos]**: muestra los motores de búsqueda que usan los visitantes para encontrar la página web. El gráfico muestra un desglose porcentual de los motores de búsqueda que se utilizan para encontrar el sitio.

**[!UICONTROL Motores de búsqueda: Pagado]**: muestra los motores de búsqueda de palabra clave paga que usan los visitantes para encontrar la página web. El gráfico muestra un desglose porcentual de los motores de búsqueda que se utilizan para encontrar el sitio.

**[!UICONTROL Motores de búsqueda: Natural]**: muestra los motores de búsqueda de palabra clave natural que usan los visitantes para encontrar la página web. El gráfico muestra un desglose porcentual de los motores de búsqueda que se utilizan para encontrar el sitio.

## Dominios de referencia {#concept_804614DF21C14C9FB542451B30F92788}

<!-- 

c_reports_ref_domains.xml

 -->

Muestra los dominios que atrajeron a aquellos clientes que repercutieron más sobre las métricas de éxito del sitio. Los referentes se dividen en dos categorías: dominios y direcciones URL. Los dominios se refieren al nombre de dominio y aparecen como el dominio base sin la cadena de consultas o los subdirectorios adjuntos. Las direcciones URL incluyen el nombre de dominio base, así como cualquier cadena de consulta o subdirectorio.

## Dominios de referencia originales {#concept_EB18251DF70343169B46BB59543A579A}

<!-- 

c_reports_original_ref_domains.xml

 -->

Muestra los referentes originales que llevaron a los clientes al sitio. Los clientes pueden visitar un sitio muchas veces y en cada visita el referente puede ser distinto. Este informe muestra de qué manera fueron conducidos la primera vez que llegaron al sitio. Con esta información podrá ver si siguieron utilizando el mismo referente y también observar patrones con respecto al modo en que los clientes llegan a su sitio. Se puede ver el número de visitantes generado por el referente original o descubrir la cantidad de ingresos que produjo cada referente original. Los informes de referentes se pueden rellenar cada vez que un visitante entra en el sitio, incluso si lo hace varias veces durante una sesión (antes de que la visita caduque).

## Referentes {#concept_40CF9C2D10B94E82819BC65A232F05C3}

Muestra el dominio o la dirección URL desde donde los visitantes llegaron al sitio, cómo encontraron el sitio web y la cantidad de visitas al sitio provenientes de esas ubicaciones referentes.

<!-- 

c_reports_referrers.xml

 -->

Por ejemplo, si un visitante llega al sitio haciendo clic en un vínculo desde el sitio A, y el sitio A no está definido como parte del dominio, entonces el sitio A es el sitio referente. Durante la implementación de los Reports and Analytics de marketing, un asesor de implementación puede ayudar a definir los dominios y las direcciones URL que forman parte del sitio web. (Este cambio se puede hacer después de la implementación).

Todo dominio o dirección URL que no forme parte de esos dominios y direcciones URL definidos se consideran referentes. Por ejemplo, supongamos que la página web A y la página web B se agregan al filtro de URL interno, pero la página web C no. En este caso, la página web C se considera referente.

Consulte [Filtros de URL internos](https://docs.adobe.com/content/help/es-ES/analytics/admin/admin-tools/internal-url-filter-admin.html) en la ayuda de [!DNL Admin Console] para obtener más información.

>[!NOTE]
>
>La función Marketing Reports and Analytics registra los dominios de referencia como correo electrónico cuando los visitantes llegan al sitio haciendo clic en un vínculo enviado por correo electrónico que contiene el protocolo [!DNL imap://] o [!DNL mail://]. Por ejemplo, todas las visitas procedentes de [!DNL https://mail.yahoo.com] no se cuentan como referente de correo electrónico, porque el protocolo es [!DNL https://]. Los mensajes de correo electrónico de Outlook se registran en la línea de direcciones escritas o marcadores, mientras que todos los referentes con protocolo HTTP cuyo dominio es un motor de búsqueda conocido se registran en la línea de motores de búsqueda.

## Tipo de referente {#concept_689E42D8F96C450DA41C7167C7388198}

Al realizar un seguimiento y registrar los sitios referentes de los visitantes permite averiguar, cómo descubrió el sitio el visitante en cada visita.

<!-- 

c_reports_ref_types.xml

 -->

La lista siguiente define los distintos tipos de referentes:

* Se registran como *otros referentes del sitio web* cuando los visitantes hacen clic en un vínculo ubicado en una página de otro sitio web (no definida como parte del sitio) y llegan al sitio web.
* Se registran como referentes de *motor de búsqueda* cuando los visitantes utilizan un motor de búsqueda para acceder al sitio.
* Se graban los referentes *escritos/en marcadores*

   * Si un visitante entra en su sitio través de un enlace que no proceda del explorador (por ejemplo, en un correo electrónico).
   * Si un visitante escribe la URL de su sitio directamente en el explorador.
   * Si un visitante hace clic en un enlace HTML en su disco duro personal.
   * Si un visitante accede a su sitio al seleccionar los marcadores del explorador.

**Definiciones**

Los siguientes artículos de línea podrían mostrarse cuando ejecute este informe:

**Dentro de su sitio**: estos artículos son direcciones URL que son etiquetadas por los filtros de URL internos. Estos elementos no se contabilizan como “instancias de referente” pero se pueden ver en los informes de otras métricas.

**Sin JavaScript**: no hay JavaScript, por lo que el tipo no se puede identificar (desconocido). Esto significa que un cliente, desde un explorador, no proporcionó información de referente y, por consiguiente, no se sabe si admite JavaScript. No se contabilizan como “instancias de referente” pero se pueden ver en los informes de otras métricas.

**USENET (grupos de noticias)**: significa que la dirección URL de un referente empezaba por `news://`. Por lo tanto, el vínculo de referente se publicó en un grupo de noticias Usenet, en vez de en una página web.

>[!NOTE]
>
>La lógica del tipo de referente coincide con otros informes de fuentes de tráfico (por ejemplo, [!UICONTROL Referentes] y [!UICONTROL Dominios de referencia]). Esto debería reducir o eliminar la aparición de artículos de línea Dentro del sitio y Sin JavaScript en el informe de [!UICONTROL tipo de referente].

