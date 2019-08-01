---
description: 'Adobe usa los siguientes términos al hablar de métricas relacionadas con la integración de DFA '
keywords: DFA
seo-description: 'Adobe usa los siguientes términos al hablar de métricas relacionadas con la integración de DFA '
seo-title: Definiciones de métricas
solution: Analytics
title: Definiciones de métricas
topic: Data Connectors
uuid: 062 f 6863-3 daa -4 e 8 a-b 6 ea -84279 d 49 c 388
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5e22d080398d74df29b1f849258e6500168cd5aa

---


# Definiciones de métricas{#metric-definitions}

Adobe usa los siguientes términos al hablar de métricas relacionadas con la integración de DFA:

**Impresiones**: las impresiones hacen referencia a la cantidad de veces que se vio un anuncio. Las impresiones se informan por anuncio, pero también se pueden agregar en grupos de anuncios u otras agrupaciones de varios anuncios. La métrica de impresiones en Analytics se importa desde DFA mediante una importación de fuentes de datos por la noche.

**Clics**: los clics hacen referencia a la cantidad de veces que se hizo clic en un anuncio, según lo que DFA informa. Los clics se registran en la página de redireccionamiento de DFA antes de que el visitante aterrice en el sitio web del cliente. Al igual que las impresiones, la métrica de clics en Analytics se importa desde DFA mediante una importación de fuentes de datos por la noche.

**Pulsaciones**: las pulsaciones hacen referencia a la cantidad de veces que el usuario llegó a la página de aterrizaje, después de hacer clic en un anuncio. Esta métrica puede diferir levemente con respecto a los clics.

**Visualizaciones**: Las visualizaciones hacen referencia a la cantidad de veces que un visitante llegó al sitio web del cliente después de ver un anuncio, pero SIN haber hecho clic en el anuncio. El visitante debe llegar al sitio dentro de la ventana de visualización que, de forma predeterminada, está configurada en 30 días. La impresión debe haber ocurrido posteriormente al último clic. Las visualizaciones se registran una vez por campaña, por visita y se cuentan cuando la integración rellena la eVar de visualización con el ID de campaña de DFA, y se establece el evento de visualización.
