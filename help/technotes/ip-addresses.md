---
title: Direcciones IP utilizadas por Adobe Analytics
description: Si el cortafuegos de su organización bloquea las direcciones IP que se originan en Adobe, utilice esta lista para actualizar la configuración del cortafuegos.
feature: Data Configuration and Collection
exl-id: e24a70e4-9ed4-4b87-8bab-4ed0aebedd1f
source-git-commit: 5ac6da2eb53d2748e8838ef2c6334a771abc26c9
workflow-type: tm+mt
source-wordcount: '186'
ht-degree: 35%

---

# Direcciones IP utilizadas por Adobe Analytics

La configuración de algunos cortafuegos bloquea las direcciones IP que se originan de los servidores de recopilación de datos de Adobe o de los servidores responsables de acceder a datos. Puede utilizar esta lista de intervalos para modificar la configuración del cortafuegos de su organización y permitir el acceso y enviar datos desde su organización.

Todas las direcciones IP que usa Adobe Analytics forman parte de [las direcciones IP que usa Adobe Experience Cloud](https://experienceleague.adobe.com/es/docs/core-services/interface/data-collection/ip-addresses), excepto el paquete de complementos de optimización del rendimiento de China.

## Direcciones IP de optimización de rendimiento de China

El paquete de complementos de optimización del rendimiento de China es un servicio de pago adicional que mejora el rendimiento de la recopilación de datos de AppMeasurement para los visitantes dentro de China. Póngase en contacto con el equipo de su cuenta de Adobe para obtener más información sobre el uso de esta función.

>[!IMPORTANT]
>
>La recopilación de datos regionales de China no está disponible para la recopilación de datos de Web SDK. Estos servidores solo se aplican a bibliotecas de AppMeasurement.

Los servidores de recopilación de datos regionales de China utilizan las siguientes direcciones IP:

| Ubicación | Host |
| --- | --- |
| China | `52.80.168.159` |
| China | `52.80.199.104` |
| China | `54.223.199.8` |

{style="table-layout:auto"}

>[!MORELIKETHIS]
>
>[Direcciones IP utilizadas por Adobe Experience Cloud](https://experienceleague.adobe.com/es/docs/core-services/interface/data-collection/ip-addresses)
>
>[Dominios utilizados por Adobe Analytics](domains.md)
