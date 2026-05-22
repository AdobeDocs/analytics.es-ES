---
title: account
description: (Retirado) Determine el grupo de informes al que se envían los datos.
feature: Appmeasurement Implementation
exl-id: 075d20be-6109-4024-84c4-1d048678d2bd
role: Admin, Developer
TQID: 'https://experienceleague.adobe.com/ICQkj-Eo29jve35GewuZUKOPIr01g-WjhbyztrAO0jI'
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 131
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
