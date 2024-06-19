---
title: account
description: (Retirado) Determine el grupo de informes al que se envían los datos.
feature: Variables
exl-id: 075d20be-6109-4024-84c4-1d048678d2bd
role: Admin, Developer
source-git-commit: 75ae77c1da1b578639609888e794e13d965ef669
workflow-type: tm+mt
source-wordcount: '131'
ht-degree: 38%

---

# account

>[!IMPORTANT]
>
>Esta variable está retirada. Utilice la función [`s.sa()`](../functions/sa-method.md) si la implementación requiere que modifique el destino del grupo de informes.

En versiones anteriores de Adobe Analytics, la variable `account` determinaba el grupo de informes al que desee enviar los datos. Se requiere un ID de grupo de informes para enviar datos a Adobe Analytics.

* Si utiliza el SDK web, los grupos de informes se encuentran en la configuración del servicio Adobe Analytics dentro del conjunto de datos al que el SDK web envía datos.
* Si utiliza la extensión de Adobe Analytics, los grupos de informes residen en el [!UICONTROL Administración de biblioteca] al configurar la extensión de Adobe Analytics.
* Si usa el [`s_gi()`](../functions/s-gi.md) para crear una instancia de un objeto de seguimiento de Analytics, los ID del grupo de informes ya existen como argumento requerido en la función.
