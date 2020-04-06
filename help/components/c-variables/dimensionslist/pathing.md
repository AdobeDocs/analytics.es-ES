---
description: Grupo de informes basado en la análisis de rutas. Técnicamente, las rutas significan pasar de un nombre de página a otro (de un valor a otro).
title: Control de rutas
topic: Reports
uuid: c4ff9fa8-e567-4039-9c86-322800a942da
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Control de rutas

Grupo de informes basado en la análisis de rutas. Técnicamente, las rutas significan pasar de un nombre de página a otro (de un valor a otro).

Utilice [Analysis Workspace Flow](https://marketing.adobe.com/resources/help/es_ES/analytics/analysis-workspace/flow.html) para disponer de opciones más flexibles de control de rutas.

>[!NOTE] Para habilitar las rutas, vaya a **[!UICONTROL Admin > Report Suites > Edit Settings > Traffic > Traffic Variables]**. Para habilitar el control de rutas en la sección del sitio y en los informes de servidor, póngase en contacto con el Servicio de atención al cliente.

Si necesita conocer el orden en que se recopilan los valores, debe habilitar las rutas para la variable que recopila dichos valores. El control de rutas está habilitado de forma predeterminada para las páginas. El control de rutas no está habilitado para ninguna propiedad de forma predeterminada, ya que solo es adecuado en determinados casos. Póngase en contacto con el Servicio de atención al cliente para habilitar las rutas en una propiedad.

>[!NOTE] En Ad Hoc Analysis, al habilitar las clasificaciones en una propiedad, las métricas de rutas estarán disponibles para todas las clasificaciones configuradas para la propiedad habilitada.

**Ejemplo: Rutas en secciones del sitio**

Si activa las rutas para la variable  *`s.channel`*, podrá rastrear cómo las visitas del sitio se desplazan de una sección a otra del sitio (a medida que va cambiando el valor).

![](assets/path_sections.png)

Las rutas están disponibles en varios informes de rutas, como [!UICONTROL Next Site Section Flow]el que muestra cómo los visitantes se desplazan a través de grupos de páginas o secciones del sitio.

![](assets/paths_report.png)

**Ejemplo: Rutas en búsquedas**

El mismo concepto de pasar de un valor a otro se aplica también a otras variables de tráfico, incluyendo términos de búsqueda interna  *`s.props`*. Por ejemplo: Si habilita las rutas para el término de búsqueda interna *`s.prop`*, puede ver la ruta que toman los visitantes a través de los términos de búsqueda.

**Ejemplo: Rutas por estado de inicio de sesión**

Es posible que desee saber cómo las personas recorren el sitio en función del estado de inicio de sesión de un visitante. Para ver esta información, no debe buscar el estado de inicio de sesión en los informes de rutas, ya que le mostrarían cómo los visitantes cambiaron los valores en ese informe o cómo los visitantes podrían haber cambiado de inicio de sesión a cierre de sesión. En cambio, concatene el valor de segmentos con la variable  *`s.pageName`* y luego enrute la variable resultante. El código siguiente es un ejemplo de rutas de páginas por estado de miembro:

```js
s.pageName="Home Page"; 
s.prop18="Gold"; // Member Status 
s.prop19=s.prop18 + ":" + s.pageName;
```

A continuación, active las rutas para  *`s.prop19`* a fin de ver qué rutas toman los miembros a través de las páginas.

>[!NOTE] Si realiza Ad Hoc Analysis, puede segmentar las rutas de páginas sin necesidad de concatenar valores de segmento y aplicar cualquier segmento a los informes de rutas.

