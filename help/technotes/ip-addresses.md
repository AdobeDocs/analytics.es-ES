---
title: Direcciones IP utilizadas por Adobe Analytics
description: Si el cortafuegos de su organización bloquea las direcciones IP que se originan en Adobe, utilice esta lista para actualizar la configuración del cortafuegos.
feature: Data Configuration and Collection
exl-id: e24a70e4-9ed4-4b87-8bab-4ed0aebedd1f
TQID: https://experienceleague.adobe.com/-4XZdprTBXpIaFnHeXBQsAr5YoZMW4ocnZRY50bHGUs
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 9e2c89f4188c723b4623a6e7859b74ede15e155b
workflow-type: tm+mt
source-wordcount: 204
ht-degree: 32%

---

# Direcciones IP utilizadas por Adobe Analytics

La configuración de algunos cortafuegos bloquea las direcciones IP que se originan de los servidores de recopilación de datos de Adobe o de los servidores responsables de acceder a datos. Puede utilizar esta lista de intervalos para modificar la configuración del cortafuegos de su organización y permitir el acceso y enviar datos desde su organización.

Todas las direcciones IP que usa Adobe Analytics forman parte de [las direcciones IP que usa CX Enterprise](https://experienceleague.adobe.com/es/docs/core-services/interface/data-collection/ip-addresses), a excepción del paquete de complementos para la optimización del rendimiento en China.

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
>[Direcciones IP utilizadas por CX Enterprise](https://experienceleague.adobe.com/es/docs/core-services/interface/data-collection/ip-addresses)
>
>[Dominios utilizados por Adobe Analytics](domains.md)
