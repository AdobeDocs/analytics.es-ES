---
title: Inclusión en la administración de consentimiento
description: Ver a qué configuración de privacidad optó un visitante.
source-git-commit: 49b2c144fea5786564ccb6dc70adead3bc669596
workflow-type: tm+mt
source-wordcount: '182'
ht-degree: 7%

---

# Inclusión en la administración de consentimiento

La dimensión &quot;Inclusión de administración de consentimiento&quot; muestra qué configuración de privacidad ha elegido un visitante. Puede utilizar esta dimensión para filtrar los datos en función de la configuración de privacidad o ver los motivos de inclusión de privacidad más comunes.

## Rellene esta dimensión con datos

Esta dimensión recopila datos de lo siguiente [Variables de datos de contexto](/help/implement/vars/page-vars/contextdata.md):

* `contextData.['opt.dmp']` cuando se configura como `Y`. If `opt.dmp` es igual que `N`, el [Exclusión de la administración de consentimiento](cm-opt-out.md) se rellena en su lugar.
* `contextData.['opt.sell']` cuando se configura como `Y`. If `opt.sell` es igual que `N`, el [Exclusión de la administración de consentimiento](cm-opt-out.md) se rellena en su lugar.

Su organización determina la lógica para implementar estas variables de datos de contexto. No persisten más allá de la visita en la que están configuradas, por lo que debe establecer cada variable de datos de contexto en cada página.

## Elementos de dimensión

Los elementos de Dimension incluyen los dos valores siguientes:

* **`DMP`**: El visitante optó por compartir en plataformas de administración de datos. Este elemento de dimensión está presente cuando la variable de datos de contexto `opt.dmp` es igual que `Y`.
* **`SELL`**: El visitante optó por compartir o vender los datos a terceros. Esta dimensión está presente cuando la variable de datos de contexto `opt.sell` es igual que `Y`.
