---
title: Inclusión en la administración de consentimiento
description: Ver qué configuración de privacidad eligió un visitante.
exl-id: b2768180-b763-41fb-8cba-665fac047e29
feature: Dimensions
source-git-commit: 811e321ce96aaefaeff691ed5969981a048d2c31
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Inclusión en la administración de consentimiento

La dimensión “Inclusión en la administración de consentimiento” muestra qué configuración de privacidad ha elegido un visitante. Puede utilizar esta dimensión para filtrar los datos en función de la configuración de privacidad o ver los motivos de inclusión de privacidad más comunes.

## Rellene esta dimensión con datos

Esta dimensión recopila datos de las siguientes [variables de datos de contexto](/help/implement/vars/page-vars/contextdata.md):

* `contextData.['opt.dmp']` cuando se establece como `Y`. Si `opt.dmp` es igual a `N`, la dimensión [Exclusión en la administración de consentimiento](cm-opt-out.md) se rellena en su lugar.
* `contextData.['opt.sell']` cuando se establece como `Y`. Si `opt.sell` es igual a `N`, la dimensión [Exclusión en la administración de consentimiento](cm-opt-out.md) se rellena en su lugar.

Su organización determina la lógica para implementar estas variables de datos de contexto. No se mantienen más allá de la visita en la que están configuradas, por lo que debe establecer cada variable de datos de contexto en cada página.

## Elementos de dimensión

Los elementos de dimensión incluyen los dos valores siguientes:

* **`DMP`**: el visitante optó por compartir en plataformas de administración de datos. Este elemento de dimensión está presente cuando la variable de datos de contexto `opt.dmp` es igual a `Y`.
* **`SELL`**: el visitante optó por compartir o vender los datos a terceros. Esta dimensión está presente cuando la variable de datos de contexto `opt.sell` es igual a `Y`.
