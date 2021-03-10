---
title: 'Integración de DFA: información de fin de vida útil'
description: ¿Por qué el fin de vida útil del Adobe del conector de datos DFA y qué alternativas existen?
translation-type: tm+mt
source-git-commit: 6669f678c1327b6af4a5b67c8033a9b7d8c9dbcf
workflow-type: tm+mt
source-wordcount: '649'
ht-degree: 1%

---


# Integración de DFA: información de fin de vida útil

Adobe anunció recientemente [sus planes para finalizar el servicio de Data Connector](https://experienceleague.adobe.com/docs/analytics/import/dataconnectors/data-connectors-eol.html), un conjunto de herramientas heredado para integrar datos de terceros (por ejemplo, ESP, VOC, etc.) con Adobe Analytics.

## ¿Por qué los Data Connectors llegan al final de su vida útil?

La plataforma admitida para la integración de socios es [Adobe Exchange](https://exchange.adobe.com/experiencecloud), que está diseñada para facilitar la integración de la aplicación Adobe Digital Experience, la integración de CXM de terceros y para admitir los distintos requisitos de datos de clientes y socios en el futuro. Muchos socios que habían creado sus integraciones mediante Data Connectors ya han migrado esas integraciones a Adobe Exchange, y más socios tienen previsto hacerlo.

## ¿Por qué la integración de DFA va al final de su vida útil?

En [enero de 2020, Google anunció](https://blog.chromium.org/2020/01/building-more-private-web-path-towards.html) que eliminará gradualmente las cookies de terceros en Chrome para 2022. Esto sigue a los estándares del sector que Apple y Mozilla han establecido para sus navegadores Safari y Firefox, respectivamente. La integración de DFA depende en gran medida de cookies de terceros y, por lo tanto, se volverá ineficaz y obsoleta con la eliminación de cookies de terceros en los tres exploradores de Internet principales. Google [reforzó esta postura en marzo de 2021](https://blog.google/products/ads-commerce/a-more-privacy-first-web) al anunciar que no lanzarán una solución alternativa.

Desafortunadamente, es poco probable que Google, que posee la integración de DFA, lo duplique en la plataforma de intercambio de Adobe. Por lo tanto, avanzamos bajo el supuesto de que, una vez que Data Connectors se desconecte, la integración existente dejará de funcionar y no tendrá un reemplazo productivo.

Un factor importante y adicional es la capacidad de &quot;visualizaciones&quot; de la integración de DFA. Permite a Adobe Analytics rastrear casos en los que un usuario vio un anuncio en pantalla, no hizo clic, pero luego visitó el sitio web. Las &quot;visualizaciones&quot; se basan en cookies de terceros, que se seguirán eliminando gradualmente a lo largo de 2021. Se trata de una cuestión de mercado, no sólo de Adobe. A partir de ahora, no existen alternativas para replicar estos datos.

## ¿Qué alternativas existen para usted?

Para los clientes interesados en integrar datos de anuncios en pantalla (sin &quot;visualizaciones&quot;) en Adobe Analytics, actualmente tenemos las siguientes opciones:

* Los clientes de Adobe Advertising Cloud DSP pueden aprovechar la [integración de productos con Adobe Analytics](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/integrations/ad-cloud/introduction-to-the-analytics-for-advertising-cloud-dsp-integration.html?lang=en#integrations) para establecer los datos de anuncios en pantalla de Google en Adobe Analytics. Esta integración es nuestra mejor alternativa y sería nuestra recomendación para los clientes. La DSP de Ad Cloud permite a los clientes ofrecer experiencias conectadas en todos los canales publicitarios, incluidos la búsqueda de pago, la visualización, el vídeo y otros. Obtenga más información [aquí](https://experienceleague.adobe.com/docs/advertising-cloud/dsp/introduction/dsp-about.html?lang=en#introduction). Sin embargo, la DSP de Ad Cloud también se verá afectada por la pérdida de cookies de terceros.
* Adobe Experience Platform y [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-landing.html?lang=en), que proporcionan funcionalidades para la integración de anuncios en pantalla con otras fuentes de datos. Los clientes pueden descargar los datos de visualización de su proveedor de búsquedas de pago y cargarlos al Experience Platform. A continuación, llevan los datos directamente a CJA para analizarlos junto con sus otros conjuntos de datos.
* Los asesores de Adobe (arquitectos de ingeniería) pueden crear una solución personalizada para introducir métricas de anuncios en pantalla en Adobe Analytics. Esta solución sigue en desarrollo y cualquier cliente interesado en unirse a la versión beta puede participar. A medida que estén disponibles, se proporcionarán más detalles sobre características, disponibilidad y coste.
* Puede administrar su propia integración de anuncios en pantalla mediante la funcionalidad de fuentes de datos, así como las clasificaciones en Adobe Analytics. Importe manualmente los datos de búsqueda y visualización de pago mediante Fuentes de datos y clasificaciones [tal como se describe aquí](https://experienceleague.adobe.com/docs/analytics/import/use-cases/paid-search-metrics.html?lang=en#use-cases). (Nota: este documento hace referencia a la búsqueda de pago, pero el caso de uso y el concepto son los mismos y se pueden aplicar a la visualización).

Para obtener más preguntas o asistencia, póngase en contacto con el [Servicio de atención al cliente de Adobe](https://helpx.adobe.com/es/contact/enterprise-support.ec.html).