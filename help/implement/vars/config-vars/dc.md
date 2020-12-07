---
title: dc
description: Variable retirada que permite determinar qué centro de datos utilizar.
translation-type: tm+mt
source-git-commit: dfe2b09b2ee287219d18099c51b6fbd7c86bab21
workflow-type: tm+mt
source-wordcount: '71'
ht-degree: 100%

---


# dc

>[!IMPORTANT]
>
>Esta variable está retirada. Utilice [`trackingServer`](trackingserver.md) en su lugar.

En las versiones anteriores de Adobe Analytics, Adobe requería que especificara a qué centro de datos quería enviar datos. Si se enviaban visitas al centro de datos incorrecto, se producía una pérdida de datos.

Adobe ha mejorado esta experiencia permitiendo que cualquier implementación envíe visitas a `sc.adobedc.net`. Ya no es necesario especificar el centro de datos.
