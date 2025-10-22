---
title: Identificación de visitantes mediante la biblioteca JavaScript de SDK web
description: Identifique correctamente a los visitantes al implementar la biblioteca JavaScript de Web SDK.
source-git-commit: 98e9dc4932bd23d3e0b632705945f56c243750c5
workflow-type: tm+mt
source-wordcount: '188'
ht-degree: 0%

---

# Identificación de visitantes mediante la biblioteca JavaScript de SDK web

La biblioteca JavaScript de Adobe Experience Platform Web SDK (`alloy.js`) ofrece un enfoque unificado y moderno para la recopilación de datos de todas las aplicaciones de Adobe Experience Cloud, incluida Adobe Analytics. Aunque la mayoría de los clientes suelen implementar la [extensión de etiquetas Web SDK](web-sdk-extension.md), puede usar la biblioteca JavaScript de Web SDK por su cuenta o dentro de un sistema de administración de etiquetas de terceros. Consulte [Alloy](https://github.com/adobe/alloy) en GitHub para descargar la versión más reciente de la biblioteca.

Los datos de identidad se pueden ampliar para admitir ID personalizados y varias áreas de nombres con `identityMap` de XDM. Adobe recomienda usar el servicio de Adobe Experience Cloud ID como identificador principal para Analytics mediante otras opciones de administración de identidades en escenarios avanzados.

Si su organización utiliza la biblioteca JavaScript de Web SDK para enviar datos a Adobe Analytics, se requiere una configuración mínima para la identificación del visitante. El servicio de ID de visitante se ha incorporado de forma nativa a la biblioteca, por lo que solo es necesario que establezca **[!UICONTROL Dominio de Edge]** en el comando `configure`. Si este campo se define con el valor deseado, la identificación del visitante funciona sin ninguna configuración adicional.
