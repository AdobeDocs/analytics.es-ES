---
title: IP y dominios utilizados por Adobe Analytics
description: Si el cortafuegos de su organización bloquea las direcciones IP que se originan en Adobe, utilice esta lista para actualizar la configuración del cortafuegos.
feature: Data Configuration and Collection
exl-id: e24a70e4-9ed4-4b87-8bab-4ed0aebedd1f
source-git-commit: ea859717c6a40b4eeeb9eca54b95718859af9c7b
workflow-type: tm+mt
source-wordcount: '232'
ht-degree: 32%

---

# IP y dominios utilizados por Adobe Analytics

Algunas configuraciones de cortafuegos bloquean los dominios en los que Adobe Analytics depende para su interfaz de producto. Puede utilizar esta lista de dominios para modificar la configuración de red de su organización y permitir el acceso a los productos desde su organización.

## Permitir dominios de tecnología dependientes

Adobe Analytics utiliza los siguientes hosts para mejorar el rendimiento y la experiencia del producto. Adobe recomienda permitir estos dominios a través del cortafuegos de su organización para una experiencia óptima con Adobe Analytics.

| Tecnología | Dominio |
| --- | --- |
| Dominios de Adobe Analytics | `adobe.com`, `adobe.net`, `adobe.io` |
| Dominio heredado de Adobe Analytics | `omniture.com` |
| Amazon AWS | `aaui-879784980514.s3.us-east-2.amazonaws.com` |
| Amazon CloudFront | `d30ln29764hddd.cloudfront.net` |
| Gainsight | `esp.aptrinsic.com`, `esp-m.aptrinsic.com` |
| LaunchDarkly | `app.launchdarkly.com` |
| Almacenamiento de Microsoft Azure Blob | `awaascicdprodva7.blob.core.windows.net` |
| CDN de Microsoft Azure | `aauicdnva7.azureedge.net` |

{style="table-layout:auto"}

## Bloqueos de direcciones IP de Adobe Experience Cloud

Además de los dominios anteriores, Adobe Analytics se basa en varios bloques de direcciones IP para la recopilación de datos y la exportación de informes.

Consulte Direcciones IP de Adobe Experience Cloud para obtener la lista completa de intervalos de IP.

## Direcciones IP de optimización de rendimiento de China

El paquete de complementos para la optimización del rendimiento de China es un servicio de pago adicional que mejora el rendimiento de la recopilación de datos de AppMeasurement para los visitantes de China. Póngase en contacto con el equipo de cuenta de Adobe para obtener más información sobre el uso de esta función.

>[!IMPORTANT]
>
>La RDC de China no está disponible para la recopilación de datos del SDK web. Estos servidores solo se aplican a bibliotecas de AppMeasurement.

Los servidores de recopilación de datos regionales de China utilizan las siguientes direcciones IP:

| Ubicación | Host |
| --- | --- |
| China | `52.80.168.159` |
| China | `52.80.199.104` |
| China | `54.223.199.8` |

{style="table-layout:auto"}
