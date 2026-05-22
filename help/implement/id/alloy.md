---
title: Identificación de visitantes mediante la biblioteca JavaScript de SDK web
description: Identifique correctamente a los visitantes al implementar la biblioteca JavaScript de Web SDK.
exl-id: e650d6b1-6e29-4a9c-98dd-8482f50968d1
TQID: 'https://experienceleague.adobe.com/k9u260HKJg6hhs7REAQ3-uE4pHvrUPBv6x8yLjZ5tvc'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: e4f5f438-eabb-4c54-9133-b817e3d125f5
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 301a0341e725ca15f1700046528ea5f42969add4
workflow-type: tm+mt
source-wordcount: 192
ht-degree: 2%

---

# Identificación de visitantes mediante la biblioteca JavaScript de SDK web

La biblioteca JavaScript de Adobe Experience Platform Web SDK (`alloy.js`) ofrece un enfoque unificado y moderno para la recopilación de datos de todas las aplicaciones empresariales de Adobe CX, incluida Adobe Analytics. Aunque la mayoría de los clientes suelen implementar la [extensión de etiquetas Web SDK](web-sdk-extension.md), puede usar la biblioteca JavaScript de Web SDK por su cuenta o dentro de un sistema de administración de etiquetas de terceros. Consulte [Alloy](https://github.com/adobe/alloy) en GitHub para descargar la versión más reciente de la biblioteca.

Los datos de identidad se pueden ampliar para admitir ID personalizados y varias áreas de nombres con `identityMap` de XDM. Adobe recomienda usar el servicio de Adobe Experience Cloud ID como identificador principal para Analytics mediante otras opciones de administración de identidades en escenarios avanzados.

Si su organización utiliza la biblioteca JavaScript de Web SDK para enviar datos a Adobe Analytics, se requiere una configuración mínima para la identificación del visitante. El servicio de ID de visitante se ha incorporado de forma nativa a la biblioteca, por lo que solo es necesario que establezca **[!UICONTROL Dominio de Edge]** en el comando `configure`. Si este campo se define con el valor deseado, la identificación del visitante funciona sin ninguna configuración adicional.
