---
title: Excluir por dirección IP
description: Impida que los datos generados por ciertas direcciones IP aparezcan en los informes.
exl-id: 315a3000-f043-434b-a677-d111aeed7971
feature: Admin Tools
role: Admin
source-git-commit: e09234ca27fbf923e026aa1f2ed0ebfed636bf7c
workflow-type: tm+mt
source-wordcount: '299'
ht-degree: 62%

---

# Excluir por dirección IP

Se pueden excluir datos de las direcciones IP específicas, por ejemplo, las actividades de sitio web internas, las pruebas del sitio y el uso por parte de los empleados, de los informes. La exclusión de datos elimina los datos de las direcciones IP para conseguir mayor precisión en los informes. Además, se pueden eliminar datos de ataques de negación de servicio u otros eventos dañinos que puedan distorsionar los datos de los informes.

Para excluir datos por dirección IP, puedes configurar las exclusiones como se describe a continuación, o puedes [configurar tu firewall](/help/technotes/ip-addresses.md).

## Configuración de exclusiones por dirección IP

>[!NOTE]
>
>Al configurar exclusiones por dirección IP, tenga en cuenta lo siguiente:
>
>* Las visitas excluidas por dirección IP se facturan como [llamadas al servidor](/help/technotes/terms.md).
>* No es necesario excluir las direcciones IP privadas. Solo las direcciones IP externas llegan a los servidores de recopilación de datos de Adobe. Las direcciones privadas incluyen `10.*.*.*`, `192.168.*.*`, `172.[16-31].*.*` y `169.254.*.*`.
>* Puede usar indicadores comodín (&#42;) para excluir un rango de direcciones. Por ejemplo, `[!DNL 0.0.*.0]` excluiría todas las direcciones IP entre `[!DNL 0.0.0.0]` y `[!DNL 0.0.255.0]`. Puede excluir hasta 50 direcciones IP diferentes.
>* Los datos de una dirección IP excluida se excluyen para cualquier nueva visita que llegue al sistema en los 5 minutos siguientes a la exclusión establecida.
>* Los datos de las visitas capturadas antes del momento en que se realizaron cambios en la dirección IP no se ven afectados.
>

Para configurar exclusiones por dirección IP:

1. En Adobe Analytics, seleccione **[!UICONTROL Administrador]** > **[!UICONTROL Todos los administradores]**.

1. En la página Administración, seleccione **[!UICONTROL Excluir por dirección IP]**.




## Influencia de la confusión de IP {#section_51B7529FFF16449CA016FDC51D87E2CA}

Si la confusión de la IP está habilitada, la exclusión de la IP se produce antes de que la dirección IP se confunda, por lo que los clientes no necesitan cambiar nada cuando habilitan la confusión de la IP.

Si se elimina el último octeto, será antes del filtrado de la IP. Como tal, el último octeto se sustituye por un 0 y las reglas de exclusión de la IP se deben actualizar para coincidir con las direcciones de IP que tengan un cero al final. Un coincidente &#42; debe corresponder a un 0.
