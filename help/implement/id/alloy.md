---
title: Identificación de visitantes mediante la biblioteca JavaScript de SDK web
description: Identifique correctamente a los visitantes al implementar la biblioteca JavaScript de Web SDK.
source-git-commit: 779ba5b0a1d71467aaaf3872fd707cc323ae8af2
workflow-type: tm+mt
source-wordcount: '145'
ht-degree: 0%

---

# Identificación de visitantes mediante la biblioteca JavaScript de SDK web

Adobe Experience Platform Web SDK (`alloy.js`) ofrece un enfoque unificado y moderno para la recopilación de datos de todas las aplicaciones de Adobe Experience Cloud, incluida Adobe Analytics. Los datos de identidad se pueden ampliar para admitir ID personalizados y varias áreas de nombres con `identityMap` de XDM. Adobe recomienda usar el servicio de Adobe Experience Cloud ID como identificador principal para Analytics mediante otras opciones de administración de identidades en escenarios avanzados.

Si su organización utiliza la biblioteca JavaScript de Web SDK para enviar datos a Adobe Analytics, se requiere una configuración mínima para la identificación del visitante. El servicio de ID de visitante se ha incorporado de forma nativa a la biblioteca, por lo que solo es necesario que establezca **[!UICONTROL Dominio de Edge]** en el comando `configure`. Si este campo se define con el valor deseado, la identificación del visitante funciona sin ninguna configuración adicional.
