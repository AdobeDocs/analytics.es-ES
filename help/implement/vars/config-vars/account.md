---
title: account
description: Utilice la variable de cuenta para determinar el grupo de informes al que se envían los datos.
exl-id: 075d20be-6109-4024-84c4-1d048678d2bd
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '109'
ht-degree: 100%

---

# account

>[!IMPORTANT]
>
>Esta variable está retirada. Utilice la función [`s.sa()`](../functions/sa-method.md) si la implementación requiere que modifique el destino del grupo de informes.

En versiones anteriores de Adobe Analytics, la variable `account` determinaba el grupo de informes al que desee enviar los datos. Se requiere un ID de grupo de informes para enviar datos a Adobe Analytics.

* Si utiliza Adobe Experience Platform Launch, los grupos de informes residen en el acordeón de [!UICONTROL Administración de biblioteca] al configurar la extensión de Adobe Analytics.
* Si utiliza la función [`s_gi()`](../functions/s-gi.md) para crear una instancia de un objeto de seguimiento de Analytics, el ID del grupo de informes ya existe como argumento requerido en la función.
