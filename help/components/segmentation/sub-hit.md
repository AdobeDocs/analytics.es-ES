---
title: Análisis de subvisita
description: Descubra cómo el análisis de subvisitas le permite filtrar productos individuales dentro de una visita en Adobe Analytics, lo que elimina el sangrado de atribución en los informes de productos.
feature: Segmentation
feature_v2: id: c153fd90-23e1-4614-81d3-3cc7571227f7
subfeature_v2: id: a544b409-2610-410d-a842-474ac1d0d54e
source-git-commit: 0168cf33d647c5edb367094d57ad9ea3ee253844
workflow-type: tm+mt
source-wordcount: 576
ht-degree: 0%

---

# Análisis de subvisitas

{{release-limited-testing}}

El análisis de subvisitas le permite analizar los datos de productos en un nivel más granular que el nivel de visita. En lugar de filtrar visitas individuales completas, puede segmentar productos individuales dentro de las visitas. Por ejemplo, segmentar una categoría de producto específica sin incluir todos los demás productos comprados en el mismo pedido.

En Adobe Analytics, el análisis de visitas secundarias se aplica específicamente a la variable **[!UICONTROL Products]**. La variable **[!UICONTROL Products]** es el único objeto de varios valores en Adobe Analytics que admite el análisis de visitas secundarias.

En Adobe Analytics, la variable [Products](/help/components/dimensions/product.md) puede capturar varios productos con una sola visita. Sin el análisis de subvisitas, la segmentación en un atributo de producto devuelve todas las visitas en las que cualquier producto de una visita coincide con el atributo de producto. El resultado es una atribución incorrecta y métricas de ingresos infladas. El análisis de visitas secundarias establece el ámbito del filtro para filas de producto individuales dentro de una visita y resuelve estos problemas.

En el análisis de subvisitas, la lógica de exclusión se comporta de forma diferente a la exclusión estándar en el nivel de visita con la variable Products. Cuando excluye atributos de producto dentro del contenedor [!UICONTROL Productos], el segmento devuelve visitas que **tienen productos** pero no coinciden con los criterios de exclusión. El segmento no devuelve visitas sin ningún producto.

## Ejemplo

Desea medir sólo los ingresos en línea de la categoría Hombres. Sin el análisis de visitas secundarias, la aplicación de un segmento para Hombres incluye los ingresos de cada producto en cualquier pedido (visita) que contenga al menos un producto con la categoría Hombres. Con el análisis de visitas secundarias, se establece el ámbito del filtro en el nivel de producto y se devuelven solo los ingresos de los productos de la categoría Hombres.

También desea medir los ingresos en línea de todas las demás categorías, excepto la categoría Hombres.

>[!BEGINTABS]

>[!TAB Análisis de visitas]

En el generador de segmentación o como parte de un **[!UICONTROL segmento rápido]**, especificas **[!UICONTROL Incluir]** el **[!UICONTROL Dimension]** **[!UICONTROL Comercio minorista: categoría de producto de moda]** **[!UICONTROL es igual a]** **[!UICONTROL Hombres]** en el contenedor de **[!UICONTROL Visitas]**.

![Panel que muestra la segmentación en el nivel de visita para la categoría de producto Hombres](./assets/product-category-segmentation-hits.png)

Como resultado, se tienen en cuenta todos los pedidos que contienen al menos **[!UICONTROL Men]** **[!UICONTROL Retail: Fashion Product Category]**, y los ingresos de otros productos de esos pedidos se incluyen en la métrica **[!UICONTROL Ingresos en línea]**.Cuando se informa sobre categorías, se informa de todos los demás valores de **[!UICONTROL Venta minorista: Categoría de productos de moda]** que formaban parte de un pedido que incluía un producto con la **[!UICONTROL Categoría de productos de moda]** para hombres **[!UICONTROL Venta minorista]**.

>[!TAB Análisis de subvisitas]

En el generador de segmentación o como parte de un **[!UICONTROL segmento rápido]**, especificas **[!UICONTROL Incluir]** el **[!UICONTROL Dimension]** **[!UICONTROL Comercio minorista: categoría de producto de moda]** **[!UICONTROL es igual a]** **[!UICONTROL Hombres]** en el contenedor de **[!UICONTROL Productos]**.

![Panel que muestra la segmentación en el nivel de subvisita para la categoría de productos Hombres](./assets/product-category-segmentation-sub-hits.png)

Como resultado, se tienen en cuenta todos los pedidos que contienen al menos **[!UICONTROL Men]** **[!UICONTROL Retail: Fashion Product Category]**, y solo se incluyen los ingresos de productos que pertenecen a **[!UICONTROL Men]** **[!UICONTROL Retail: Fashion Product Category]** para la métrica **[!UICONTROL Online Revenue]**.Cuando se informa sobre categorías, solo se informa sobre **[!UICONTROL Hombres]** **[!UICONTROL Comercio minorista: categoría de producto de moda]**.

>[!TAB Análisis de subvisitas (excluir)]

En el generador de segmentación o como parte de un **[!UICONTROL segmento rápido]**, especificas **[!UICONTROL Excluir]** el **[!UICONTROL Dimension]** **[!UICONTROL Comercio minorista: categoría de producto de moda]** **[!UICONTROL es igual a]** **[!UICONTROL Hombres]** en el contenedor de **[!UICONTROL Productos]**.

![Panel que muestra la segmentación en el nivel de subvisita para excluir la categoría de productos Hombres](./assets/product-category-segmentation-sub-hits-exclude.png)

Para excluir en el nivel de producto, se incluyen las visitas que contienen al menos un producto y, a continuación, la exclusión en el nivel de subvisita se aplica dentro de ese ámbito. Esta exclusión difiere de la exclusión de nivel de visita, que excluye toda la visita.

>[!ENDTABS]
