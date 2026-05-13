---
title: Plantilla de CDA Workspace
description: Describe cada campo de la plantilla CDA de Analysis Workspace.
exl-id: 293001ff-bf7b-4de8-b175-7c2c17d1794d
feature: CDA
role: Admin
TQID: https://experienceleague.adobe.com/Zui1m27pi3eQnm-dac2akfGRF01IbPaQ0SwLD01iDAE
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32id: c153fd90-23e1-4614-81d3-3cc7571227f7
subfeature_v2: id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06id: b3a8b8a0-1cc2-48a8-ac82-ffd9c66ccab4id: e38cbddc-1633-4cd5-bed5-9f289f2a6029id: ef60b66e-5984-4336-ba72-6d978b1b6f87id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: bcc5edb5-84c3-4940-9f84-ed88b6c16274
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 391
ht-degree: 92%

---

# Plantilla de CDA Workspace

{{available-existing-customers}}

Adobe ofrece una plantilla para ver datos de rendimiento vitales entre dispositivos.

1. Vaya a [experiencecloud.adobe.com](https://experiencecloud.adobe.com) e inicie sesión con sus credenciales de Adobe ID.
1. Haga clic en el icono de 9 cuadrículas en la parte superior y, a continuación, haga clic en Analytics.
1. Haga clic en [!UICONTROL Workspace] en la parte superior y, a continuación, en [!UICONTROL “Crear nuevo proyecto”].
1. Localice la plantilla Análisis entre dispositivos y, a continuación, haga clic en [!UICONTROL Crear].
1. Si se le solicita, cambie el grupo de informes a uno que admita CDA.

Se crea un proyecto de Analysis Workspace que contiene varios paneles. En la parte superior, se muestra una tabla de contenido e introducción, lo que permite el contexto del informe y la navegación hacia informes individuales. Haga clic en un vínculo dentro de la tabla de contenido o expanda el acordeón de un panel para ver dichos informes.

<!--The content below is mirrored in /help/analyze/analysis-workspace/build-workspace-project/starter-projects.md-->

* **Identificación de los usuarios**: muestra la frecuencia con la que se identifican los visitantes del sitio mediante métodos basados en el análisis entre dispositivos.
* **Medición del tamaño del público**: muestra una comparación de &#39;Dispositivos únicos&#39; con &#39;Personas&#39;. La proporción de estos dos números se conoce como &#39;compresión entre dispositivos&#39;, una métrica calculada visible en este panel. Esta métrica de compresión depende de varios factores:
   * Velocidad de inicio de sesión: Cuantos más usuarios inicien sesión en el sitio, más podrá Adobe identificar y unir a los visitantes entre dispositivos. Los sitios con una tasa de inicio de sesión baja también tienen tasas de compresión bajas.
   * Cobertura del Experience Cloud ID: Solo se pueden vincular los visitantes con un ECID. Un porcentaje menor de visitantes a su sitio que utilizan un ECID se correlaciona con tasas de compresión más bajas.
   * Uso de varios dispositivos: Si los visitantes del sitio no utilizan varios dispositivos, puede ver tasas de compresión más bajas.
   * Granularidad de informes: La compresión por día suele ser menor que la compresión por mes o año. Las posibilidades de que un individuo utilice varios dispositivos se reducen en un solo día en comparación con todo un mes. Segmentar, filtrar o utilizar dimensiones de desglose también puede mostrar una tasa de compresión más baja.
* **Segmentos basados en personas**: contiene una lista desplegable de segmentos que le permite ver datos específicos del dispositivo. Este panel promueve la experimentación con segmentos para ver cómo la inclusión o la exclusión de tipos de dispositivos afectan los informes.
* **Análisis del viaje entre dispositivos**: proporciona informes de flujo y visitas en el orden previsto en función del tipo de dispositivo.
* **Atribución entre dispositivos**: combine las características del análisis entre dispositivos y la atribución.
* **Otros consejos y trucos**: temas útiles en torno a CDA que le permite aprovecharlo al máximo.
