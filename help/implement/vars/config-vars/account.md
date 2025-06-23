---
title: account
description: (Retirado) Determine el grupo de informes al que se envían los datos.
feature: Appmeasurement Implementation
exl-id: 075d20be-6109-4024-84c4-1d048678d2bd
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '131'
ht-degree: 38%

---

# account

>[!IMPORTANT]
>
>Esta variable está retirada. Utilice la función [`s.sa()`](../functions/sa-method.md) si la implementación requiere que modifique el destino del grupo de informes.

En versiones anteriores de Adobe Analytics, la variable `account` determinaba el grupo de informes al que desee enviar los datos. Se requiere un ID de grupo de informes para enviar datos a Adobe Analytics.

* Si utiliza Web SDK, los grupos de informes se encuentran en la configuración del servicio Adobe Analytics dentro del conjunto de datos al que Web SDK envía los datos.
* Si usa la extensión de Adobe Analytics, los grupos de informes residen en el acordeón [!UICONTROL Administración de biblioteca] al configurar la extensión de Adobe Analytics.
* Si usa la función [`s_gi()`](../functions/s-gi.md) para crear una instancia de un objeto de seguimiento de Analytics, los identificadores del grupo de informes ya existen como argumento requerido en la función.
