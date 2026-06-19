---
title: Variables de página
description: Configure los valores en una página individual.
feature: Appmeasurement Implementation
exl-id: 321d0db2-61a3-478e-ab51-8e06c7b2bb7b
role: Admin, Developer
TQID: https://experienceleague.adobe.com/mWfMumcPTklFPKUiGIOatDbC0WKW5RDYH56rXTFk3ZY
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: e7d92df1-c5ba-4e93-85df-f83171b889beid: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: d4db20e3498d54162806b3fdef0b34f45c93a6ff
workflow-type: tm+mt
source-wordcount: 148
ht-degree: 47%

---

# Información general sobre las variables de página

Las variables de página determinan los valores de las dimensiones y métricas en el sistema de informes.

Las siguientes listas son variables que se utilizan con frecuencia en las implementaciones:

* [`pageName`](pagename.md): Nombre de la página.
* [`campaign`](campaign.md): establezca esta variable en un parámetro de cadena de consulta para el seguimiento de campañas.
* [`events`](events/events-overview.md): complete las métricas para usarlas en el sistema de informes.
* [`products`](products.md): si tiene un sitio de comercio electrónico, configure esta variable cuando un visitante vista o compra un producto.

## Variables de página retiradas

Se retiran las siguientes variables de página. Están documentados aquí como referencia si los encuentra en una implementación heredada.

* **`hier`**: se implementaron variables de jerarquía (`hier1`-`hier5`) para capturar la estructura de un sitio para los informes. Se retira y no es una dimensión disponible en Analysis Workspace. En su lugar, use [eVars](evar.md) y clasificaciones.
* **`state`**: capturó el estado de EE. UU. en el que ingresó un visitante, generalmente a través de un formulario de envío o facturación. En su lugar, utilice la dimensión [[!UICONTROL Estados de EE. UU.]](/help/components/dimensions/us-states.md), que Adobe rellena automáticamente desde la ubicación geográfica del visitante.
