---
title: Inclusión en la administración de consentimiento
description: Ver qué configuración de privacidad eligió un visitante.
exl-id: b2768180-b763-41fb-8cba-665fac047e29
feature: Dimensions
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '182'
ht-degree: 91%

---

# Inclusión en la administración de consentimiento

La dimensión [dimensión](overview.md) de &#39;Inclusión en la administración de consentimiento&#39; muestra a qué configuración de privacidad se ha suscrito un visitante. Puede utilizar esta dimensión para filtrar los datos en función de la configuración de privacidad o ver los motivos de inclusión de privacidad más comunes.

## Rellene esta dimensión con datos

Esta dimensión recopila datos de las siguientes [variables de datos de contexto](/help/implement/vars/page-vars/contextdata.md):

* `contextData.['opt.dmp']` cuando se establece como `Y`. Si `opt.dmp` es igual a `N`, la dimensión [Exclusión en la administración de consentimiento](cm-opt-out.md) se rellena en su lugar.
* `contextData.['opt.sell']` cuando se establece como `Y`. Si `opt.sell` es igual a `N`, la dimensión [Exclusión en la administración de consentimiento](cm-opt-out.md) se rellena en su lugar.

Su organización determina la lógica para implementar estas variables de datos de contexto. No se mantienen más allá de la visita en la que están configuradas, por lo que debe establecer cada variable de datos de contexto en cada página.

## Elementos de dimensión

Los elementos de dimensión incluyen los dos valores siguientes:

* **`DMP`**: el visitante optó por compartir en plataformas de administración de datos. Este elemento de dimensión está presente cuando la variable de datos de contexto `opt.dmp` es igual a `Y`.
* **`SELL`**: el visitante optó por compartir o vender los datos a terceros. Esta dimensión está presente cuando la variable de datos de contexto `opt.sell` es igual a `Y`.
