---
description: La integración de Data Connectors para DFA usa variables de Analytics para rastrear resultados de campañas DFA.
keywords: DFA
title: Variables y eventos de Analytics
topic: Data connectors
uuid: 8996cb58-c793-4600-99ef-af3064642b29
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Variables y eventos de Analytics{#analytics-variables-and-events}

La integración de Data Connectors para DFA usa variables de Analytics para rastrear resultados de campañas DFA.

Además de la variable de campaña, puede usar eVars y eventos de Analytics que sean útiles para usted. Tras haber identificado las eVars y el evento que se usa con esta integración de DFA, use la consola de administración de Analytics para habilitarlos. Las variables de integración deben habilitarse antes de activar la integración de DFA. La siguiente tabla describe las variables de Analytics que se necesitan para la integración de DFA.

| Variable | Nombre descriptivo | Método de obtención de datos | Descripción |
|---|---|---|---|
| s.campaign o eVar | Código de seguimiento de anuncios | Se completa automáticamente mediante Data Connector para campañas DFA. | Rastrea conversiones de pulsaciones para todas las campañas. |
| eVar* | Visualización | Se completa automáticamente mediante VISTA y DFA para campañas DFA. | Rastrea datos de visualización para los ID DFA. Esta eVar debe tener la misma caducidad que la variable *`s.campaign`* campaign. Debe ser la misma variable de conversión identificada en la ID de proveedor de variable. Asegúrese de que la eVar tenga subrelaciones completas habilitadas. El coste por habilitar esta función es parte de la tarifa por integración de Data Connectors. |
| eVar* | Errores de consulta DFA | (Opcional) Se completa mediante código de recopilación JavaScript. | Contiene uno de varios códigos de error devueltos por DFA. |
| evento* | Recuento de visualizaciones | Se completa automáticamente mediante Data Connector para campañas DFA. | Captura la cantidad de veces que los usuarios vieron un anuncio, no pulsaron, pero llegaron a su sitio. |
| evento* | Impresiones | Se completa automáticamente mediante una fuente de datos de DFA. | Rastrea la cantidad de veces que se publicó un anuncio DFA específico. |
| evento* | Clics | Se completa automáticamente mediante una fuente de datos de DFA. | Rastrea la cantidad de veces que los usuarios hicieron clic en un anuncio de tipo titular DFA específica. Esta métrica puede arrojar números diferentes en comparación con la métrica nativa de pulsaciones de Analytics por uno de varios motivos. Consulte [Reconciliación de discrepancias de métricas](/help/import/data-connectors/dfa-data-connector-analytics/dfa-reconciling-metric-discrepancies.md) para obtener más información. |
| evento* | Tiempos de espera de DFA | (Opcional) Se completa mediante código de recopilación JavaScript. | Cuenta la cantidad de veces que DFA no responde antes del *`s.maxDelay`* tiempo de espera. Esto puede ayudarlo a determinar si existe algún problema de implementación de DFA. |
| evento* | Coste de medios de DFA | Se completa automáticamente mediante una fuente de datos de DFA. | Contiene las métricas de coste de medios que se han introducido en la interfaz de DFA. Esta función debe habilitarse en el DFA para que aparezcan dichas métricas. |

*Seleccione una eVar que no se haya utilizado o un evento personalizado.
