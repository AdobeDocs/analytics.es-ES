---
title: account
description: Utilice la variable de cuenta para determinar el grupo de informes al que se envían los datos.
translation-type: tm+mt
source-git-commit: f179292abae9cf7986d61da89a86e3e88111943e

---


# account

> [!IMPORTANT] Esta variable está retirada. Utilice la [`s.sa()`](../functions/sa-method.md) función si la implementación requiere que modifique el destino del grupo de informes.

En versiones anteriores de Adobe Analytics, la `account` variable determinaba el grupo de informes al que se desea enviar los datos. Se requiere un ID de grupo de informes para enviar datos a Adobe Analytics.

* Si utiliza Adobe Experience Platform Launch, los grupos de informes residen en el acordeón Administración [!UICONTROL de] biblioteca al configurar la extensión de Adobe Analytics.
* Si utiliza la `s_gi()` función para crear una instancia de un objeto de seguimiento de Analytics, la ID del grupo de informes ya existe como argumento requerido en la función.
