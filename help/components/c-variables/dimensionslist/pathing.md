---
description: Grupo de informes basado en el análisis de rutas. Técnicamente, las rutas suponen el paso de un nombre de página a otro (de un valor a otro).
title: Control de rutas
topic: Reports
uuid: c4ff9fa8-e567-4039-9c86-322800a942da
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Control de rutas

Grupo de informes basado en el análisis de rutas. Técnicamente, las rutas suponen el paso de un nombre de página a otro (de un valor a otro).

Utilice [Analysis Workspace Flow](https://marketing.adobe.com/resources/help/en_US/analytics/analysis-workspace/flow.html) para disponer de opciones más flexibles de control de rutas.

> [!NOTE] Para habilitar el control de rutas, vaya a **[!UICONTROL Administración &gt; Grupos de informes &gt; Editar configuración &gt; Tráfico &gt; Variables de tráfico]**. Para habilitar el control de rutas en la sección del sitio y en los informes de servidor, póngase en contacto con el Servicio de atención al cliente.

Si necesita saber el orden en que se recopilan los valores, deberá habilitar el control de rutas para la variable que recopila dichos valores. El control de rutas está habilitado de forma predeterminada para las páginas. No está habilitado para cualquier propiedad de manera predeterminada porque únicamente es adecuado en determinados casos. Para habilitar el control de rutas en una propiedad, el usuario debe ponerse en contacto con el Servicio de atención al cliente.

> [!NOTE] En Ad Hoc Analysis, al habilitar las clasificaciones en una propiedad, las métricas de rutas estarán disponibles para todas las clasificaciones configuradas para la propiedad habilitada.

**Ejemplo: Rutas en secciones del sitio**

Si activa las rutas para la variable  *`s.channel`*, podrá rastrear cómo las visitas del sitio se desplazan de una sección a otra del sitio (a medida que va cambiando el valor).

![](assets/path_sections.png)

Las rutas estarán entonces disponibles en varios informes de rutas, como [!UICONTROL Flujo de sección de sitio siguiente], cómo los visitantes se desplazan a través de los grupos de páginas o secciones del sitio.

![](assets/paths_report.png)

**Ejemplo: Rutas en búsquedas**

El mismo concepto de pasar de un valor a otro se aplica también a otras variables de tráfico, incluyendo términos de búsqueda interna  *`s.props`*. Por ejemplo: Si habilita las rutas para el término de búsqueda interna *`s.prop`*, puede ver la ruta que toman los visitantes a través de los términos de búsqueda.

**Ejemplo: Rutas por estado de inicio de sesión**

Es posible que desee conocer la ruta de los visitantes a través del sitio en función del estado de inicio de sesión de un visitante. Para conocer esta información no se recomienda acudir a los informes de rutas para obtener el estado de inicio de sesión, ya que le mostrarían el cambio de valores de los visitantes en ese informe o el cambio de estado de sesión de los visitantes. En cambio, concatene el valor de segmentos con la variable  *`s.pageName`* y luego enrute la variable resultante. El código siguiente es un ejemplo de rutas de páginas por estado de miembro:

```js
s.pageName="Home Page"; 
s.prop18="Gold"; // Member Status 
s.prop19=s.prop18 + ":" + s.pageName;
```

A continuación, active las rutas para  *`s.prop19`* a fin de ver qué rutas toman los miembros a través de las páginas.

> [!NOTE] Si realiza Ad Hoc Analysis, puede segmentar las rutas de páginas sin necesidad de concatenar valores de segmento y aplicar cualquier segmento a los informes de rutas.

