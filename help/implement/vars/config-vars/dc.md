---
title: dc
description: Variable retirada que permite determinar qué centro de datos utilizar.
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# dc

> [!IMPORTANT] Esta variable está retirada. Use [`trackingServer`](trackingserver.md) en su lugar.

En las versiones anteriores de Adobe Analytics, Adobe requería que especificara a qué centro de datos quería enviar datos. Si se enviaban visitas al centro de datos incorrecto, se producía una pérdida de datos.

Adobe ha mejorado esta experiencia permitiendo que cualquier implementación envíe visitas a `sc.omtrdc.net`. Ya no es necesario especificar el centro de datos.
