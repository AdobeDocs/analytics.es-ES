---
title: Excluir por dirección IP
description: Impida que los datos generados por ciertas direcciones IP aparezcan en los informes.
exl-id: 315a3000-f043-434b-a677-d111aeed7971
feature: Admin Tools
role: Admin
source-git-commit: 4b4febd839682d88164b2f505245441d18ef2543
workflow-type: tm+mt
source-wordcount: '318'
ht-degree: 31%

---

# Excluir por dirección IP

Se pueden excluir datos de las direcciones IP específicas, por ejemplo, las actividades de sitio web internas, las pruebas del sitio y el uso por parte de los empleados, de los informes. La exclusión de datos elimina los datos de las direcciones IP para conseguir mayor precisión en los informes. Además, puede eliminar datos de ataques de denegación de servicio u otros eventos malintencionados que puedan distorsionar los datos de los informes.

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
>* Los datos de las visitas capturadas antes del momento en que se realizaron cambios en la dirección IP no se ven afectados. La exclusión de la IP solo se aplica a los datos que se producen a partir de ahora.
>* Las visitas excluidas siguen visibles en [Fuentes de datos](/help/export/analytics-data-feed/data-feed-overview.md) (marcadas como `exclude_hit = 4`).

Para configurar exclusiones por dirección IP:

1. En Adobe Analytics, seleccione **[!UICONTROL Administrador]** > **[!UICONTROL Todos los administradores]**.

1. En la página Administración, seleccione **[!UICONTROL Excluir por dirección IP]**.

## Influencia de la confusión de IP con exclusión de IP

El impacto de usar [confusión de IP](/help/admin/tools/manage-rs/edit-settings/general/general-acct-settings-admin.md) junto con la exclusión de IP depende de la configuración de confusión de IP de cada grupo de informes:

* **Confusión de IP (último octeto)**: la IP se confunde parcialmente ANTES de que se ejecute la exclusión de IP. Asegúrese de que las reglas de exclusión de IP siempre esperen `0` como último octeto (los caracteres comodín son válidos porque incluyen `0`).
* **Confusión de IP (eliminar IP)**: la IP se confunde completamente DESPUÉS de que se ejecute la exclusión de IP. No es necesario ajustar las reglas de exclusión de IP.
