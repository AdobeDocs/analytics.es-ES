---
title: Información general de dimensiones
description: Obtenga información sobre las dimensiones y cómo se utilizan en Adobe Analytics.
feature: Dimensions
exl-id: dc00e06a-fdb5-40e3-82e2-269bad3b3677
TQID: https://experienceleague.adobe.com/WypIneraYlrSyIpXv3UQWIFn42A-Dxi0SxeJ2VbeubQ
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
subfeature_v2:
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: d4db20e3498d54162806b3fdef0b34f45c93a6ff
workflow-type: tm+mt
source-wordcount: 436
ht-degree: 37%

---

# Información general de dimensiones

Las dimensiones son variables en Adobe Analytics que generalmente contienen valores de cadena. Las dimensiones comunes incluyen [Página](page.md), [Dominio de referencia](referring-domain.md) o una [eVar](evar.md). Por el contrario, las [métricas](../metrics/overview.md) contienen valores numéricos que se vinculan a una dimensión. Un informe básico muestra filas de valores de cadena (dimensión) frente a una columna de valores numéricos (métrica).

Por ejemplo, si ha combinado la dimensión **[!UICONTROL Página]** con la métrica **[!UICONTROL Visitas]**, obtendrá un informe de clasificación que muestra las páginas más visitadas:

| Página | Visitas |
| --- | ---: |
| Página de inicio | 800 |
| Página de producto | 500 |
| Página de compra | 100 |

{style="table-layout:fixed"}

Cada dimensión representa una parte o faceta diferente del sitio. Puede combinar una o más de estas dimensiones con una o más métricas para crear un informe deseado.

## Agregar descripciones de dimensión

Los administradores de Analytics pueden añadir descripciones para dimensiones y otros componentes tanto dentro del grupo de informes como directamente dentro de Analysis Workspace. Para obtener información acerca de cómo añadir descripciones a dimensiones, consulte [Adición de descripciones de componentes](/help/analyze/analysis-workspace/components/add-component-descriptions.md).

## Dimensiones retiradas

Se retiran las siguientes dimensiones. La mayoría eran informes de Reports &amp; Analytics que no están disponibles en Analysis Workspace. Se documentan aquí como referencia si los encuentra en informes heredados o datos históricos.

* **Jerarquía**: Una dimensión personalizada (`hier1`-`hier5`) que se usa para capturar la estructura jerárquica de un sitio para los informes. Se ha retirado y no está disponible en Analysis Workspace. En su lugar, use [eVars](evar.md) y clasificaciones.
* **Página principal**: Un indicador que indica si la página actual era la página principal del explorador del visitante. Es una dimensión heredada sin equivalente moderno debido a las prácticas modernas de privacidad del explorador.
* **Compatibilidad con JavaScript**: Indica si el explorador del visitante admite JavaScript. Dimensión heredada que ya no es significativa para la medición moderna.
* **Versión de JavaScript**: Se informó de la versión de JavaScript que admitía el explorador del visitante. Una dimensión heredada que ya no se recopila.
* **Página siguiente**: Una dimensión de rutas que muestra la página siguiente que vio un visitante. Utilice la [visualización de flujo](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md) en Analysis Workspace para las dimensiones de rutas actuales.
* **Página anterior**: Una dimensión de rutas que muestra la página anterior que vio un visitante. Utilice la [visualización de flujo](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md) en Analysis Workspace para las dimensiones de rutas actuales.
* **Zona horaria**: La zona horaria del visitante, derivada del desplazamiento de la marca de tiempo en las solicitudes de imagen de AppMeasurement. Web SDK recopila la zona horaria mediante [`placeContext`](https://experienceleague.adobe.com/en/docs/experience-platform/collection/js/commands/configure/context).
* **Dominio de nivel superior**: Dominio de nivel superior del punto de acceso del visitante. Un informe heredado de Reports &amp; Analytics; use la dimensión [Dominio](domain.md) en su lugar.
* **Número de página de visita**: El número de página dentro de una visita. Un informe heredado de Reports &amp; Analytics; use la dimensión [Profundidad de visita](hit-depth.md) en su lugar.
* **Estado del visitante**: Informó del estado de EE. UU. desde la variable `s.state`. Se sustituye por la dimensión [Estados de EE. UU.](us-states.md), que utiliza la segmentación geográfica.
