---
title: account
description: Utilice la variable de cuenta para determinar el grupo de informes al que se envían los datos.
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# account

> [!IMPORTANT] Esta variable está retirada. Utilice la [`s.sa()`](../functions/sa-method.md) función si la implementación requiere que modifique el destino del grupo de informes.

En versiones anteriores de Adobe Analytics, la `account` variable determinaba el grupo de informes al que se desea enviar los datos. Se requiere un ID de grupo de informes para enviar datos a Adobe Analytics.

* Si utiliza Adobe Experience Platform Launch, los grupos de informes residen bajo el [!UICONTROL Library Management] acordeón al configurar la extensión de Adobe Analytics.
* Si utiliza la [`s_gi()`](../functions/s-gi.md) función para crear una instancia de un objeto de seguimiento de Analytics, la ID del grupo de informes ya existe como argumento requerido en la función.
