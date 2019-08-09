---
description: 'null'
keywords: DFA
seo-description: 'null'
seo-title: Actualice su parámetro de cadena de consulta de DFA
solution: Analytics
title: Actualice su parámetro de cadena de consulta de DFA
topic: Data Connectors
uuid: adf 585 ac -84 ff -44 c 1-a 48 d-b 072726 c 8494
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e96de98b3176a05654fdf697210f992b0fd4adb1

---


# Actualizar el parámetro de cadena de consulta de DFA{#update-your-dfa-query-string-parameter}

Si ya ha estado rastreando campañas de publicidad con Adobe Analytics antes de la integración de DFA, es posible que todas las campañas (correo electrónico, búsqueda o titular) usen el mismo parámetro de cadena de consulta para identificar el ID de campaña de referencia en la página de aterrizaje.

Para comprender cuándo se deben solicitar datos de visualizaciones y pulsaciones desde datos de DFA para sus campañas de publicidad de DFA, Data Connectors necesita identificar cuándo un visitante ha hecho clic en un anuncio de titular de campaña de DFA. Para hacer esto posible, debe agregar un parámetro de cadena de consulta diferenciado a la dirección URL de la página de aterrizaje de la campaña de publicidad de DFA. De esta manera, Data Connectors podrá distinguir entre páginas de campañas de publicidad de DFA y entre otras páginas de campañas de publicidad que usted podría tener en el sitio web. El `dfa_overrideParam` complemento JavaScript (consulte [Actualizar el código de recopilación de datos del sitio Web](../../../dfa-data-connector-analytics/dfa-integration/dfa-web-site-updates/dfa-update-data-collection-code.md#concept-8c108723ea0b4cc9a8c5cdc2d05894e3)) utilizado para DFA.

>[!CAUTION]
>
>Aunque la variable Campaign puede utilizarse para otras campañas, no la use para campañas DFA. Si establece la variable de Campaña en una página de aterrizaje de campaña de DFA, Adobe no puede unir las impresiones y los clics con pulsaciones de campaña de DFA. Una vez por visita, los servidores de recopilación de Adobe comprueban en servidores DFA si hay una pulsación o visualización previa. Debido a esto, incluya el código de complemento de DFA (consulte [Actualice el código de la recopilación de datos de su sitio web](../../../dfa-data-connector-analytics/dfa-integration/dfa-web-site-updates/dfa-update-data-collection-code.md#concept-8c108723ea0b4cc9a8c5cdc2d05894e3)) solamente en páginas de aterrizaje comunes para evitar redireccionamientos innecesarios que pueden ralentizar los tiempos de carga de las páginas, particularmente para usuarios con conexiones a Internet más lentas.

