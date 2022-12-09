---
title: Exclusión en la administración de consentimiento
description: Ver de qué configuración de privacidad excluyó un visitante.
exl-id: 2bf4d22c-5b24-47fb-b489-49388fcca5b1
source-git-commit: dc9cd6bb45af0c992c37ffe20ea22eab67789ec5
workflow-type: tm+mt
source-wordcount: '254'
ht-degree: 5%

---

# Exclusión en la administración de consentimiento

La dimensión &quot;Exclusión de la administración de consentimiento&quot; muestra qué configuración de privacidad ha excluido explícitamente un visitante. Puede utilizar esta dimensión para filtrar los datos en función de la configuración de privacidad o ver las razones de exclusión de privacidad más comunes.

## Rellene esta dimensión con datos

Esta dimensión recopila datos de lo siguiente [Variables de datos de contexto](/help/implement/vars/page-vars/contextdata.md):

* `contextData.['cm.ssf']` cuando se configura como `1`. If `cm.ssf` es igual que `0` o está en blanco, esta variable no hace nada.
* `contextData.['opt.dmp']` cuando se configura como `N`. If `opt.dmp` es igual que `Y`, el [Inclusión en la administración de consentimiento](cm-opt-in.md) se rellena en su lugar.
* `contextData.['opt.sell']` cuando se configura como `N`. If `opt.sell` es igual que `Y`, el [Inclusión en la administración de consentimiento](cm-opt-in.md) se rellena en su lugar.

Su organización determina la lógica para implementar estas variables de datos de contexto. No persisten más allá de la visita en la que están configuradas, por lo que debe establecer cada variable de datos de contexto en cada página.

## Elementos de dimensión

Los elementos de Dimension incluyen los tres valores siguientes:

* **`SSF`**: El visitante no optó por [Reenvío del lado del servidor](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-server-side-forwarding/ssf.md). Este elemento de dimensión está presente cuando la variable de datos de contexto `cm.ssf` es igual que `1`. Consulte [Información general sobre la privacidad de datos](https://experienceleague.adobe.com/docs/audience-manager/user-guide/overview/data-privacy/data-privacy.html) en la guía del usuario del Audience Manager para obtener más información. La visita no se reenvía a Adobe Audience Manager.
* **`DMP`**: El visitante no optó por compartir en plataformas de administración de datos. Este elemento de dimensión está presente cuando la variable de datos de contexto `opt.dmp` es igual que `N`. Similar a `SSF`, la visita no se reenvía a Adobe Audience Manager.
* **`SELL`**: El visitante se excluyó del uso compartido o de la venta de los datos a terceros. Esta dimensión está presente cuando la variable de datos de contexto `opt.sell` es igual que `N`.
