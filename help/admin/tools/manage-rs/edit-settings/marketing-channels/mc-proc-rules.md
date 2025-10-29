---
title: Reglas de procesamiento de canales de marketing
description: Utilice reglas para determinar a qué canal de marketing pertenece una visita.
feature: Marketing Channels
exl-id: 825f70a5-cce3-4b1c-bb42-828388348216
role: Admin
source-git-commit: e934de3938f013067d6bbd6b516b0444b0c9f782
workflow-type: tm+mt
source-wordcount: '819'
ht-degree: 3%

---

# Reglas de procesamiento de canal de marketing

_Esta página hace referencia a reglas de procesamiento que asignan un canal de marketing a una visita. Consulte [Reglas de procesamiento](../general/processing-rules/pr-overview.md) para ver la característica que le permite ajustar el modo en que se recopilan los datos._

Las reglas de procesamiento de canales de mercadotecnia permiten crear lógica que determina el valor de las dimensiones [Canal de mercadotecnia](/help/components/dimensions/marketing-channel.md) y [Detalle del canal de mercadotecnia](/help/components/dimensions/marketing-detail.md). Use [Administrador de canales de mercadotecnia](c-channels.md) para determinar qué canales de mercadotecnia usa y luego use reglas de procesamiento para determinar cómo se establece cada canal.

![Bloques de canales de marketing](assets/buckets_2.png)

**[!UICONTROL Analytics]** > **[!UICONTROL Administrador]** > **[!UICONTROL Grupos de informes]** > **[!UICONTROL Editar configuración]** > **[!UICONTROL Canales de marketing]** > **[!UICONTROL Reglas de procesamiento de canal de marketing]**

Una vez que se ejecuta la [configuración automática](/help/components/c-marketing-channels/c-getting-started-mchannel.md), se crea una regla para cada canal generado durante la configuración.

![Reglas predeterminadas](assets/marketing_channel_rules.png)

Puede utilizar varias reglas para definir un único canal de marketing. El uso de varias reglas para un solo canal puede resultar beneficioso si desea configurar los detalles del canal de forma diferente en función de las condiciones de las reglas. También puede utilizar varias condiciones para definir una sola regla.

## Definiciones de reglas

Cada regla contiene una condición y una asignación:

* **[!UICONTROL Si alguna/todas las condiciones siguientes son verdaderas]**: Si agrega varias condiciones a una sola regla, puede determinar si se deben cumplir todas las condiciones o cualquiera de las condiciones para establecer el canal y el valor asociado.
* **Condiciones de regla**: especifique una o varias condiciones de regla que deben cumplirse. Normalmente, especifica una dimensión con la que debe coincidir una visita para optar al canal de marketing.
* **[!UICONTROL A continuación, haga lo siguiente]**: Cuando coincidan las condiciones de regla, establezca [Canal de marketing](/help/components/dimensions/marketing-channel.md) ([!UICONTROL Identifique el canal como]) y [Detalle del canal de marketing](/help/components/dimensions/marketing-detail.md) ([!UICONTROL Establezca el valor del canal]).

## Condiciones de regla

Las siguientes opciones están disponibles al configurar condiciones de regla.

>[!NOTE]
>
>Todos los campos de texto se evalúan como **sin distinción de mayúsculas y minúsculas**. Por ejemplo, si utiliza una condición de regla en la que el parámetro de cadena de consulta `cmp` es igual a `abc123`, tanto el parámetro de cadena de consulta como el valor pueden utilizar cualquier combinación de mayúsculas y minúsculas.

**Las condiciones detectadas por Adobe** no contienen ninguna opción o campo para escribir texto.

| condición detectada por Adobe | Descripción |
|---|---|
| **[!UICONTROL Coincide Con Las Reglas De Detección De Búsqueda De Pago]** | La visita se originó a partir de un motor de búsqueda reconocido y coincidió con [reglas de detección de búsqueda de pago](../general/paid-search-detection/paid-search-detection.md). |
| **[!UICONTROL Coincide Con Las Reglas De Detección De Búsqueda Natural]** | La visita se originó a partir de un motor de búsqueda reconocido y no coincide con las reglas de detección de búsqueda de pago. |
| **[!UICONTROL El referente coincide con los filtros de URL internos]** | La visita contenía un [referente](/help/components/dimensions/referrer.md) que coincidía con [filtros de URL internos](../general/internal-url-filter-admin.md). |
| **[!UICONTROL El referente no coincide con los filtros de URL internos]** | La visita contenía un referente que no coincidía con los filtros de URL internos. |
| **[!UICONTROL Es la primera visita individual de la visita]** | El resultado fue el primero de una visita. |
| **[!UICONTROL El Referente Es Una Red Social]** | El [tipo de referente](/help/components/dimensions/referrer-type.md) es &quot;Redes sociales&quot;. |
| **[!UICONTROL El Referente No Es Una Red Social]** | El tipo de referente no es &quot;Redes sociales&quot;. |
| **[!UICONTROL El referente es inteligencia artificial aplicada a la conversación]** | El tipo de referente es &quot;IA conversacional&quot;. |
| **[!UICONTROL El referente no es inteligencia artificial aplicada a la conversación]** | El tipo de referente no es &quot;IA conversacional&quot;. |

**Atributos de visita** le permiten especificar una dimensión, un operador coincidente y un valor que buscar.

| Condición de atributo de visita | Descripción |
|---|---|
| **[!UICONTROL Página]** | La dimensión [Página](/help/components/dimensions/page.md). |
| **[!UICONTROL Dominio de página]** | El dominio de la dirección URL. Por ejemplo, `products.example.com`. |
| **[!UICONTROL Dominio Y Ruta De Página]** | Dominio y ruta de la dirección URL. Por ejemplo, `products.example.com/mens/pants/overview.html`. |
| **[!UICONTROL Dominio raíz de página]** | Dominio raíz de la dirección URL. Por ejemplo, `example.co.uk`. |
| **[!UICONTROL URL de la página]** | Dirección URL de la página completa. |
| **[!UICONTROL Parámetro de cadena de consulta]** | Un parámetro de cadena de consulta individual en la dirección URL de la página. Utilice un parámetro de cadena de consulta por cada condición de regla. Si desea incluir varios parámetros de cadena de consulta en una regla, utilice varias condiciones de regla. |
| **[!UICONTROL Referente]** | La dimensión [Referente](/help/components/dimensions/referrer.md). |
| **[!UICONTROL Dominio de referencia]** | La dimensión [Dominio de referencia](/help/components/dimensions/referring-domain.md). |
| **[!UICONTROL Dominio Y Ruta De Referencia]** | Una concatenación del dominio de referencia y la ruta URL del referente. Por ejemplo, `www.example.com/products/id/12345` o `ad.example.com/foo`. |
| **[!UICONTROL Parámetro de referencia]** | Un parámetro de cadena de consulta dentro del referente. |
| **[!UICONTROL Dominio raíz de referencia]** | El dominio raíz de referencia. |
| **[!UICONTROL Motor de búsqueda]** | La dimensión [Motor de búsqueda](/help/components/dimensions/search-engine.md). |
| **[!UICONTROL Palabra(s) clave(s) de búsqueda]** | Dimensión [Search keyword](/help/components/dimensions/search-keyword.md). |
| **[!UICONTROL Motor de búsqueda + Palabra(s) clave(s) de búsqueda]** | Una concatenación de motor de búsqueda y palabra clave de búsqueda. |
| **[!UICONTROL ID de AMO]** | El código de seguimiento principal utilizado por las integraciones de Adobe Advertising y Advertising Analytics. Cuando se habilita una de estas integraciones, se puede usar el prefijo del código de seguimiento para identificar canales específicos de Advertising. Los valores que comienzan por &quot;AL&quot; son para Search y Social. Los valores que comienzan por &quot;AC&quot; son para visualización. Cuando se utiliza el ID de AMO en los canales de marketing, las métricas de clics, costes e impresiones se pueden atribuir al canal correcto. |
| **[!UICONTROL ID. DE EF DE AMO]** | El código de seguimiento secundario utilizado por Adobe Advertising. Sirve como clave para devolver datos a Advertising. Se puede utilizar para identificar las visualizaciones de clics y las visualizaciones de visualizaciones como dos canales de marketing independientes. Para ello, establezca que la lógica del canal de marketing para &quot;AMO EF ID&quot; termine con `:d` para las visualizaciones de pulsaciones o que &quot;AMO EF ID&quot; termine con `:i` para las visualizaciones de visualizaciones. Si no desea dividir la visualización en dos canales, utilice la dimensión de ID de AMO en su lugar. |

**Las variables de conversión** le permiten especificar un eVar personalizado, un operador coincidente y un valor que buscar.

| Condición de variable de conversión | Descripción |
|---|---|
| **eVar 1-250** | La dimensión [eVar](/help/components/dimensions/evar.md) asociada. |
