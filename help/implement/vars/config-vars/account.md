---
title: account
description: Utilice la variable de cuenta para determinar el grupo de informes al que se envían los datos.
feature: Variables
exl-id: 075d20be-6109-4024-84c4-1d048678d2bd
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '135'
ht-degree: 47%

---

# account

>[!IMPORTANT]
>
>Esta variable está retirada. Utilice la función [`s.sa()`](../functions/sa-method.md) si la implementación requiere que modifique el destino del grupo de informes.

En versiones anteriores de Adobe Analytics, la variable `account` determinaba el grupo de informes al que desee enviar los datos. Se requiere un ID de grupo de informes para enviar datos a Adobe Analytics.

* Si utiliza el SDK web, los grupos de informes se encuentran en la configuración del servicio Adobe Analytics dentro del conjunto de datos al que el SDK web envía datos.
* Si utiliza la extensión de Adobe Analytics, los grupos de informes residen en el [!UICONTROL Administración de biblioteca] al configurar la extensión de Adobe Analytics.
* Si usa el [`s_gi()`](../functions/s-gi.md) para crear una instancia de un objeto de seguimiento de Analytics, los ID del grupo de informes ya existen como argumento requerido en la función.
