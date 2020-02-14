---
description: Descubra las prácticas recomendadas y vea ejemplos de cómo rellenar las diversas reglas que puede configurar para sus canales de mercadotecnia.
title: Preguntas más frecuentes y ejemplos de canales de mercadotecnia
translation-type: tm+mt
source-git-commit: 21f4b9df688776f7a1db96f76e258031ae3abb3d

---


# Preguntas más frecuentes y ejemplos de canales de mercadotecnia

See [Create Marketing Channel Processing Rules](/help/components/c-marketing-channels/c-rules.md) for definitions of fields displayed on the [!UICONTROL Marketing Channel Processing Rules] page.

## Preguntas frecuentes {#faq}

Cada implementación de las reglas de procesamiento de canal de mercadotecnia podría diferir, según sus códigos de seguimiento. La configuración de las reglas que proporcionen los resultados que necesita podría requerir cierta creatividad para resolver los problemas.

**Pregunta**: mis códigos de seguimiento no se rigen por ningún patrón y tengo que especificar miles de ellos para el canal Afiliados.

* Utilice el proceso de eliminación. Si los canales Correo electrónico y Afiliados utilizan el mismo parámetro de cadena de consulta pero solamente tiene unos cuantos códigos de seguimiento de correo electrónico, puede especificar los códigos de seguimiento de correo electrónico en un conjunto de reglas que definan el correo electrónico. Luego, clasifique todos los demás códigos de seguimiento con *`affiliates.`*
* En su sistema de correo electrónico, agregue un parámetro de cadena de consulta a todas las direcciones URL de páginas de aterrizaje, como *`&ch=eml`*. Cree un conjunto de reglas que detecte si el parámetro de consulta ch es igual a *`eml`*. Si no contiene *`eml`*, entonces es un afiliado.

**Pregunta**: Los dominios de referencia contienen más datos de lo que tenía previsto.

* Es posible que los dominios de referencia estén demasiado arriba en la lista de reglas de procesamiento. Dicho conjunto de reglas debería ser uno de los últimos (o el último): el orden de procesamiento es importante.

**Pregunta**: he creado una regla que concuerda con un parámetro de cadena de consulta y que no funciona.

* Compruebe que el nombre del parámetro esté especificado en los campos del parámetro de la cadena de consulta (normalmente, un valor alfanumérico). Asegúrese, también, de que el valor del parámetro se especifica después del operador, como se muestra en el siguiente ejemplo de regla de correo electrónico.

   ![](assets/example_email.png)

**Pregunta**: ¿por qué se atribuye todo mi tráfico de último toque a un dominio interno?

* Hay una regla que concuerda con el tráfico interno. Recuerde que estas reglas se procesan con cada visita que el visitante haga al sitio, y no solo con la primera visita. Si tiene alguna regla similar a *`Page URL exists`* sin ningún otro criterio, con cada visita sucesiva a su sitio web, se encuentran coincidencias con ese canal, porque siempre existe una URL de página.

**Pregunta**: ¿cómo se depura el tráfico que se muestra en No se ha identificado el canal, en el informe?

* Las reglas se procesan en orden. Si no se encuentra ninguna concordancia con un criterio específico, las visitas caen en una de estas tres categorías:

1. Sin referente (visita directa).

2. Referente interno, en la primera página de la visita.

3. Problema técnico de procesamiento en la página.

Asegúrese de tener un canal para estas tres posibilidades. Por ejemplo, cree reglas como estas:

1. **[!UICONTROL Referrer]** y **[!UICONTROL Does Not Exist]** y **[!UICONTROL Is First Page of Visit]**. (Consulte [Directas.](/help/components/c-marketing-channels/c-faq.md))

2. **[!UICONTROL Referrer Matches Internal URL Filters]** y **[!UICONTROL Is First page of Visit]**. (Consulte [Internas](/help/components/c-marketing-channels/c-faq.md).)

3. **[!UICONTROL Referrer]** y **[!UICONTROL Exists]** y **[!UICONTROL Referrer Does Not Match Internal URL Filters]**.

Por último, cree el canal *Otros* para que capture las visitas restantes, tal como se describe en [No se ha identificado el canal](/help/components/c-marketing-channels/c-faq.md#no-channel-identified).

## No se ha identificado el canal {#no-channel-identified}

When your rules do not capture data, or if rules are not configured correctly, the report displays the data in the [!UICONTROL No Channel Identified] row on the report. Por ejemplo, puede crear un conjunto de reglas denominado *Otro* al final del orden de procesamiento, que también identifique el tráfico interno.

![](assets/example_other.png)

This kind of rule serves as a catch-all to ensure that channel traffic always matches external traffic, and typically does not end up in **[!UICONTROL No Channel Identified]**. Tenga cuidado de no crear una regla que identifique también el tráfico interno. Setting the channel&#39;s value to **[!UICONTROL Referring Domain]** or to **[!UICONTROL Page URL]** are the most common, useful ways to create an effective Other rule.

> [!NOTE] Debería haber todavía algún tráfico de canal que podría caer en la categoría Ningún canal identificado. Por ejemplo: un visitante viene al sitio, crea un marcador de una página y en la misma visita, vuelve a la página a través del marcador. Debido a que esta no es la primera página de la visita, irá al canal Directo o al canal Otros porque no hay dominio de referencia.

## Búsqueda de pago {#paid-search}

La búsqueda paga es una palabra o frase por la que se paga a un motor de búsqueda, para que la coloque en los resultados de la búsqueda. To match paid search detection rules, the marketing channel uses settings configured on the [!UICONTROL Paid Search Detection] page. ( **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** > **[!UICONTROL Edit Settings]** > **[!UICONTROL General]** > **[!UICONTROL Paid Search Detection]**). La dirección URL de destino coincide con la regla de detección de búsqueda paga existente para dicho motor de búsqueda.

For the marketing channel rule, the [!UICONTROL Paid Search] settings are as follows:

![](assets/example_paid_search.png)

Consulte [Detección de búsqueda paga](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/paid-search-detection/paid-search-detection.html) en Administración para obtener más información.

## Búsqueda natural {#natural-search}

Las búsquedas naturales tienen lugar cuando los visitantes encuentran su sitio web a través de una búsqueda en Internet en la que el motor de búsqueda clasifica su sitio sin que usted haya pagado específicamente para ello. Puede controlar la URL de destino que el motor de búsqueda utiliza para establecer el vínculo a su sitio. Esta URL permite a Analytics identificar si una búsqueda es natural.

No hay detección de búsquedas naturales en Analytics. Después de configurar la detección de búsqueda paga, el sistema sabe que, si un referente de búsqueda no es de búsqueda paga, tiene que ser de búsqueda natural. En la búsqueda natural, la dirección URL de destino no coincide con la regla de detección de búsqueda paga de ese motor de búsqueda.

En la regla de canal de mercadotecnia, la configuración de búsqueda natural es la siguiente:

![](assets/example_natural_search.png)

Consulte [Detección de búsqueda paga](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/paid-search-detection/paid-search-detection.html) en Administración para obtener más información.

## Afiliados {#afilliates}

Las reglas de afiliados identifican a los visitantes que proceden de un conjunto específico de dominios de referencia. En la regla, se enumeran los dominios de los afiliados de los que desee hacer un seguimiento, de este modo:

![](assets/example_affiliates.png)

## Redes sociales {#social-networks}

Esta regla identifica a los visitantes que se originan en una red social como, por ejemplo, Facebook*. La configuración puede ser así:

![](assets/example_social.png)

## Mostrar {#display}

Esta regla identifica a los visitantes que proceden de anuncios de banners. Se identifica con un parámetro de cadena de consulta en la dirección URL de destino, en este caso *`Ad_01`*.

![](assets/example_display.png)

## Internas {#internal}

Esta regla identifica a los visitantes que proceden de un referente que coincide con los filtros de URL internos del grupo de informes.

![](assets/example_internal.png)

## Correo electrónico {#email}

Para configurar esta regla, se indica el parámetro de cadena de consulta correspondiente a la campaña de correo electrónico. En este ejemplo, el parámetro es *`eml`*:

![](assets/example_email.png)

Si la regla contiene códigos de seguimiento, escriba un valor en cada línea, de este modo:

![](assets/tracking_code.png)

## Directas {#direct}

Esta regla identifica a los visitantes que no cuentan con un dominio de referencia. Esto incluye a los visitantes que llegan a su sitio directamente como, por ejemplo, con un vínculo de Favoritos, o que han pegado el vínculo en el navegador.

![](assets/example_direct.png)

