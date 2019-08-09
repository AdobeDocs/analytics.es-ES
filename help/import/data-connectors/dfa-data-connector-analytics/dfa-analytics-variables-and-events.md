---
description: La integración de Data Connectors para DFA usa variables de Analytics para rastrear resultados de campañas DFA.
keywords: DFA
seo-description: La integración de Data Connectors para DFA usa variables de Analytics para rastrear resultados de campañas DFA.
seo-title: Variables y eventos de Analytics
solution: Analytics
title: Variables y eventos de Analytics
topic: Data Connectors
uuid: 8996 cb 58-c 793-4600-99 ef-af 3064642 b 29
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e96de98b3176a05654fdf697210f992b0fd4adb1

---


# Variables y eventos de Analytics{#analytics-variables-and-events}

La integración de Data Connectors para DFA usa variables de Analytics para rastrear resultados de campañas DFA.

Además de la variable de campaña, puede usar eVars y eventos de Analytics que sean útiles para usted. Tras haber identificado las eVars y el evento que se usa con esta integración de DFA, use la consola de administración de Analytics para habilitarlos. Las variables de integración deben habilitarse antes de activar la integración de DFA. La siguiente tabla describe las variables de Analytics que se necesitan para la integración de DFA.

| Variable | Nombre descriptivo | Método de obtención de datos | Descripción |
|---|---|---|---|
| s.campaign o eVar | Código de seguimiento de anuncios | Se completa automáticamente mediante Data Connector para campañas DFA. | Rastrea conversiones de pulsaciones para todas las campañas. |
| eVar* | Visualización | Se completa automáticamente mediante VISTA y DFA para campañas DFA. | Rastrea datos de visualización para los ID DFA. Esta eVar debe tener la misma caducidad que la variable *`s.campaign`* . Debe ser la misma variable de conversión que se identifique en el ID de proveedor de variable (consulte [Actualizar el código de recopilación de datos de su sitio web](../dfa-data-connector-analytics/dfa-integration/dfa-web-site-updates/dfa-update-data-collection-code.md#concept-8c108723ea0b4cc9a8c5cdc2d05894e3)). Asegúrese de que la eVar tenga subrelaciones completas habilitadas. El coste por habilitar esta función es parte de la tarifa por integración de Data Connectors. |
| eVar* | Errores de consulta DFA | (Opcional) Se completa mediante código de recopilación JavaScript. | Contiene uno de varios códigos de error devueltos desde DFA (consulte la tabla en [Configuración de la integración](../dfa-data-connector-analytics/dfa-integration/dfa-integration.md#concept-cf33e1051c73452cbd26e950d0293858) para ver un listado de estos códigos de error). |
| event* | Recuento de visualizaciones | Se completa automáticamente mediante Data Connector para campañas DFA. | Captura la cantidad de veces que los usuarios vieron un anuncio, no pulsaron, pero llegaron a su sitio. |
| event* | Impresiones | Se completa automáticamente mediante una fuente de datos de DFA. | Rastrea la cantidad de veces que se publicó un anuncio DFA específico. |
| event* | Clics | Se completa automáticamente mediante una fuente de datos de DFA. | Rastrea la cantidad de veces que los usuarios hicieron clic en un anuncio de tipo titular DFA específica. Esta métrica puede arrojar números diferentes en comparación con la métrica nativa de pulsaciones de Analytics por uno de varios motivos. Consulte [Reconciliación de discrepancias de métricas](../dfa-data-connector-analytics/dfa-reconciling-metric-discrepancies/dfa-reconciling-metric-discrepancies.md#concept-8c31ebe761ca4b3fab1e3a18ef5d098f) para obtener más información. |
| event* | Tiempos de espera de DFA | (Opcional) Se completa mediante código de recopilación JavaScript. | Cuenta la cantidad de veces que DFA no responde antes del *`s.maxDelay`* tiempo de espera. Esto puede ayudarlo a determinar si existe algún problema de implementación de DFA. |
| event* | Coste de medios de DFA | Se completa automáticamente mediante una fuente de datos de DFA. | Contiene las métricas de coste de medios que se han introducido en la interfaz de DFA. Esta función debe habilitarse en el DFA para que aparezcan dichas métricas. |

*Seleccione una eVar que no se haya utilizado o un evento personalizado.
