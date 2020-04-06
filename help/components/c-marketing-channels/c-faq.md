---
description: Descubra las prácticas recomendadas y vea ejemplos de cómo rellenar las diversas reglas que puede configurar para sus canales de mercadotecnia.
title: Preguntas más frecuentes y ejemplos de Canales de marketing
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Preguntas más frecuentes y ejemplos de Canales de marketing

See [Create Marketing Channel Processing Rules](/help/components/c-marketing-channels/c-rules.md) for definitions of fields displayed on the [!UICONTROL Marketing Channel Processing Rules] page.

## Preguntas frecuentes {#faq}

Cada implementación de las reglas de procesamiento de canal de mercadotecnia puede variar según los códigos de seguimiento. La configuración de las reglas que proporcionan los resultados que busca puede requerir cierta creatividad para resolver problemas.

**Pregunta**: Mis códigos de seguimiento no siguen un patrón, y tengo miles que deben especificarse para mi canal de Afiliados.

* Utilizar el proceso de eliminación. Si los canales Correo electrónico y Afiliados utilizan el mismo parámetro de cadena de consulta, pero sólo tiene unos pocos códigos de seguimiento del correo electrónico, puede especificar los códigos de seguimiento del correo electrónico en un conjunto de reglas que defina el correo electrónico. Luego, clasifique todos los demás códigos de seguimiento con  *`affiliates.`*
* En su sistema de correo electrónico, agregue un parámetro de cadena de consulta a todas las direcciones URL de páginas de aterrizaje, como *`&ch=eml`*. Cree un conjunto de reglas que detecte si el parámetro de consulta ch es igual a *`eml`*. Si no contiene *`eml`*, entonces es un afiliado.

**Pregunta**: Los dominios de referencia contienen más datos de lo que tenía previsto.

* Los dominios de referencia pueden ser demasiado altos en la lista de la regla de procesamiento. Debe ser uno de los últimos conjuntos de reglas (o el último), ya que el orden de procesamiento es importante.

**Pregunta**: He creado una regla que coincide con un parámetro de cadena de consulta y que no funciona.

* Compruebe que el nombre del parámetro esté especificado en los campos del parámetro de la cadena de consulta (normalmente, un valor alfanumérico). Además, asegúrese de que el valor del parámetro se especifica después del operador, como se muestra en el siguiente ejemplo de una regla de correo electrónico.

   ![](assets/example_email.png)

**Pregunta**: ¿Por qué se atribuye todo mi tráfico de último toque a un dominio interno?

* Tiene una regla que coincide con el tráfico interno. Recuerde que estas reglas se procesan con cada visita que el visitante haga al sitio, y no solo con la primera visita. Si tiene alguna regla similar a  *`Page URL exists`* sin ningún otro criterio, con cada visita sucesiva a su sitio web, se encuentran coincidencias con ese canal, porque siempre existe una URL de página.

**Pregunta**: ¿Cómo se depura el tráfico que se muestra en Ningún Canal identificado en el informe?

* Las reglas se procesan en orden. Si no se ha cumplido ningún criterio específico, las visitas se dividen en una de las tres categorías:

1. Sin referente (visita directa).

2. Referente interno, en la primera página de la visita.

3. Problema técnico de procesamiento en la página.

Asegúrese de que tiene un canal para estas tres posibilidades. Por ejemplo, cree reglas que digan:

1. **[!UICONTROL Referrer]** y **[!UICONTROL Does Not Exist]** y **[!UICONTROL Is First Page of Visit]**. (Consulte [Directas.](/help/components/c-marketing-channels/c-faq.md))

2. **[!UICONTROL Referrer Matches Internal URL Filters]** y **[!UICONTROL Is First page of Visit]**. (Consulte [Internas](/help/components/c-marketing-channels/c-faq.md).)

3. **[!UICONTROL Referrer]** y **[!UICONTROL Exists]** y **[!UICONTROL Referrer Does Not Match Internal URL Filters]**.

Por último, cree el canal *Otros* para que capture las visitas restantes, tal como se describe en [No se ha identificado el canal](/help/components/c-marketing-channels/c-faq.md#no-channel-identified).

## No se ha identificado el canal  {#no-channel-identified}

Cuando las reglas no capturan datos o si las reglas no están configuradas correctamente, el informe muestra los datos en la [!UICONTROL No Channel Identified] fila del informe. Puede crear un conjunto de reglas denominado *Otro*, por ejemplo, al final del orden de procesamiento, que también identifique el tráfico interno.

![](assets/example_other.png)

This kind of rule serves as a catch-all to ensure that channel traffic always matches external traffic, and typically does not end up in **[!UICONTROL No Channel Identified]**. Tenga cuidado de no crear una regla que identifique también el tráfico interno. Setting the channel&#39;s value to **[!UICONTROL Referring Domain]** or to **[!UICONTROL Page URL]** are the most common, useful ways to create an effective Other rule.

>[!NOTE] Debería haber todavía algún tráfico de canal que podría caer en la categoría Ningún canal identificado. Por ejemplo: un visitante viene al sitio, crea un marcador de una página y en la misma visita, vuelve a la página a través del marcador. Dado que esta no es la primera página de la visita, no irá ni en el canal directo ni en el canal Otro porque no hay ningún dominio de referencia.

## Búsqueda de pago {#paid-search}

La búsqueda paga es una palabra o frase por la que se paga a un motor de búsqueda, para que la coloque en los resultados de la búsqueda. Para coincidir con las reglas de detección de búsqueda paga, el canal de mercadotecnia utiliza la configuración de la [!UICONTROL Paid Search Detection] página. ( **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** > **[!UICONTROL Edit Settings]** > **[!UICONTROL General]** > **[!UICONTROL Paid Search Detection]**). La dirección URL de destino coincide con la regla de detección de búsqueda paga existente para ese motor de búsqueda.

Para la regla de canal de mercadotecnia, los [!UICONTROL Paid Search] ajustes son los siguientes:

![](assets/example_paid_search.png)

Consulte Detección [de búsqueda](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/paid-search-detection/paid-search-detection.html) paga en Administración para obtener más información.

## Búsqueda natural  {#natural-search}

La búsqueda natural se produce cuando los visitantes encuentran su sitio Web a través de una búsqueda en la Web, donde el motor de búsqueda clasificó su sitio sin que usted haya pagado por la lista. Puede controlar la dirección URL de destino que utiliza el motor de búsqueda para establecer un vínculo con el sitio. Esta URL permite a Analytics identificar si una búsqueda es natural.

No hay detección de búsqueda natural en Analytics. Después de configurar la detección de búsqueda paga, el sistema sabe que, si un referente de búsqueda no es de búsqueda paga, tiene que ser de búsqueda natural. Para una búsqueda natural, la dirección URL de destino no coincide con la regla de detección de búsqueda paga existente para ese motor de búsqueda.

Para la regla de canal de mercadotecnia, la configuración de búsqueda natural es la siguiente:

![](assets/example_natural_search.png)

Consulte Detección [de búsqueda](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/paid-search-detection/paid-search-detection.html) paga en Administración para obtener más información.

## Afiliados  {#afilliates}

Las reglas de afiliados identifican a los visitantes que proceden de un conjunto específico de dominios de referencia. En la regla, puede realizar la lista de los dominios de los afiliados que desee rastrear, como se indica a continuación:

![](assets/example_affiliates.png)

## Redes sociales  {#social-networks}

Esta regla identifica a los visitantes que se originan en una red social como, por ejemplo, Facebook*. La configuración puede ser la siguiente:

![](assets/example_social.png)

## Mostrar  {#display}

Esta regla identifica a los visitantes que proceden de anuncios de banners. Se identifica con un parámetro de cadena de consulta en la dirección URL de destino, en este caso  *`Ad_01`*.

![](assets/example_display.png)

## Internas {#internal}

Esta regla identifica a los visitantes que proceden de un referente que coincide con los filtros de URL internos del grupo de informes.

![](assets/example_internal.png)

## Correo electrónico  {#email}

Para configurar esta regla, se indica el parámetro de cadena de consulta correspondiente a la campaña de correo electrónico. En este ejemplo, el parámetro es  *`eml`*:

![](assets/example_email.png)

Si la regla contiene códigos de seguimiento, escriba un valor en cada línea, de este modo:

![](assets/tracking_code.png)

## Directas  {#direct}

Esta regla identifica a los visitantes que no cuentan con un dominio de referencia. Esta regla incluye visitantes que llegan directamente a su sitio, como por ejemplo desde un vínculo Favoritos o pegando un vínculo en su explorador.

![](assets/example_direct.png)

