---
title: Excluir por dirección IP
description: Impida que los datos generados por ciertas direcciones IP aparezcan en los informes.
exl-id: 315a3000-f043-434b-a677-d111aeed7971
source-git-commit: d198e8ef0ec8415a4a555d3c385823baad6104fe
workflow-type: tm+mt
source-wordcount: '223'
ht-degree: 82%

---

# Excluir por dirección IP

Se pueden excluir datos de las direcciones IP específicas, por ejemplo, las actividades de sitio web internas, las pruebas del sitio y el uso por parte de los empleados, de los informes. La exclusión de datos elimina los datos de las direcciones IP para conseguir mayor precisión en los informes. También es posible eliminar datos de ataques de negación de servicio u otros eventos dañinos que pueden distorsionar los datos de los informes. Puede configurar la exclusión o utilizar el cortafuegos.

**[!UICONTROL Analytics]**  >  **[!UICONTROL Administración]**  >  **[!UICONTROL Todos los administradores]**  >  **[!UICONTROL Excluir por dirección IP]**

>[!NOTE]
>
>Las visitas excluidas por dirección IP se facturan como [llamadas al servidor](https://docs.adobe.com/content/help/es-ES/analytics/technotes/terms.html).

Pueden utilizarse indicadores comodín (*) para excluir un intervalo de direcciones. Por ejemplo, `[!DNL 0.0.*.0]` excluiría todas las direcciones IP entre `[!DNL 0.0.0.0]` y `[!DNL 0.0.255.0]`. Puede excluir hasta 50 direcciones IP diferentes.

>[!TIP]
>
>No es necesario excluir las direcciones IP privadas. Solo las direcciones IP externas llegan a los servidores de recopilación de datos de Adobe. Las direcciones privadas incluyen `10.*.*.*`, `192.168.*.*`, `172.[16-31].*.*` y `169.254.*.*`.

## Influencia de la confusión de IP {#section_51B7529FFF16449CA016FDC51D87E2CA}

Si la confusión de la IP está habilitada, la exclusión de la IP se produce antes de que la dirección IP se confunda, por lo que los clientes no necesitan cambiar nada cuando habilitan la confusión de la IP.

Si se elimina el último octeto, será antes del filtrado de la IP. Como tal, el último octeto se sustituye por un 0 y las reglas de exclusión de la IP se deben actualizar para coincidir con las direcciones de IP que tengan un cero al final. Un * coincidente debe corresponder a un 0.
