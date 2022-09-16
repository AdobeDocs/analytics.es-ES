---
title: IP y dominios utilizados por Adobe Analytics
description: Si el cortafuegos de su organización bloquea las direcciones IP que se originan en Adobe, utilice esta lista para actualizar la configuración del cortafuegos.
feature: Data Configuration and Collection
exl-id: e24a70e4-9ed4-4b87-8bab-4ed0aebedd1f
source-git-commit: be8e4c3a25dccaf7bd591f487e1131288ba26f2a
workflow-type: tm+mt
source-wordcount: '400'
ht-degree: 79%

---

# IP y dominios utilizados por Adobe Analytics

La configuración de algunos cortafuegos bloquea las direcciones IP que se originan de los servidores de recopilación de datos de Adobe o de los servidores responsables de acceder a datos. Puede utilizar esta lista de intervalos para modificar la configuración del cortafuegos de su organización y permitir el acceso y enviar datos desde su organización. Esta página incluye tanto los sistemas entrantes (como la recopilación de datos) como los salientes (como las fuentes de datos) que utiliza el Adobe.

>[!IMPORTANT]
>
>Aunque Adobe hace todo lo posible por mantener actualizado este documento, no puede garantizar que la lista de intervalos de IP sea la misma. Los posibles cambios incluyen el crecimiento y la expansión del negocio, un registro de Internet requiere cambios en el espacio de direcciones IP del Adobe o un proveedor de servicio de Internet deja de funcionar.

## Permitir dominios de tecnología dependientes

Adobe Analytics utiliza los siguientes hosts para mejorar el rendimiento y la experiencia del producto. Adobe recomienda permitir que estos dominios pasen por el cortafuegos de su organización para disfrutar de una experiencia óptima con Adobe Analytics.

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

## Todos los bloqueos de direcciones IP de recopilación de datos de Adobe Analytics

La siguiente tabla abarca todos los servidores de recopilación de datos estándar y los servidores de recopilación de datos regionales para Adobe Analytics. No incluyen hosts de AWS individuales.

| Bloque IP (Notación CIDR) |
| --- |
| `63.140.32.0/19` |
| `66.117.16.0/20` |
| `66.235.128.0/19` |
| `130.248.0.0/16` |

## Bloques de direcciones IP de FTP y recopilación de datos

Si su organización prefiere permitir intervalos específicos de direcciones IP, puede utilizar la siguiente tabla. Todos los intervalos de esta sección se incluyen en la tabla anterior. Las conexiones FTP para fuentes de datos y Data Warehouse solo se originan en las ubicaciones de Londres, Oregón y Singapur.

| Ubicación | Intervalo IP (Notación CIDR) |
| --- | --- |
| Australia | `63.140.55.0/24` |
| Australia | `63.140.56.0/23` |
| California | `63.140.32.0/23` |
| California | `63.140.34.0/24` |
| India | `66.117.20.0/24` |
| India | `66.117.22.0/23` |
| Japón | `130.248.130.0/23` |
| Japón | `130.248.169.0/23` |
| Japón | `63.140.50.0/23` |
| Japón | `66.117.31.0/24` |
| Londres | `66.235.156.0/24` |
| Oregón | `66.235.132.0/22` |
| Singapur | `130.248.170.0/23` |
| Singapur | `130.248.240.0/24` |
| Singapur | `63.140.44.0/22` |
| Singapur | `63.140.48.0/23` |
| Singapur | `66.117.30.0/24` |
| Virginia | `63.140.38.0/23` |
| Virginia | `63.140.54.0/24` |

## Hosts de AWS

Adobe Analytics utiliza los servicios web de Amazon como parte de su proceso de recopilación de datos. La siguiente tabla incluye las direcciones de host IPv4 de AWS reservadas para el Adobe. Estos hosts **no** están incluidos en el intervalo de bloques acumulado anterior.

| Ubicación | Host |
| --- | --- |
| China | `52.80.83.220` |
| China | `71.132.16.253` |
| Francia | `13.36.218.177` |
| Francia | `15.188.95.229` |
| Francia | `15.236.176.210` |
| Irlanda | `54.74.170.177` |
| Irlanda | `54.195.254.128` |
| Irlanda | `54.220.133.225` |
| Oregón | `52.10.149.115` |
| Oregón | `52.40.172.46` |
| Oregón | `54.212.155.93` |
| Virginia | `3.216.131.23` |
| Virginia | `34.204.237.47` |
| Virginia | `54.163.234.74` |

La siguiente tabla incluye los bloques de direcciones IPv6 de AWS utilizados por el Adobe. Estos hosts **no** están incluidos en el intervalo de bloques acumulado anterior.

| Ubicación | Host |
| --- | --- |
| Australia | `2406:da1c:406:1a00::/56` |
| Australia | `2406:da1c:ce5:b400::/56` |
| California | `2600:1f1c:366:d900::/56` |
| India | `2406:da1a:f34:6a00::/56` |
| Irlanda | `2a05:d018:309:600::/56` |
| Japón | `2406:da14:b07:ab00::/56` |
| Oregón | `2600:1f14:1eb:7d00::/56` |
| Oregón | `2600:1f14:9d3:2b00::/56` |
| Singapur | `2406:da18:6e8:1e00::/56` |
| Virginia | `2600:1f18:1a20:e800::/56` |
| Virginia | `2600:1f18:4fd:6000::/56` |
| Virginia | `2600:1f18:b00:e100::/56` |
| Virginia | `2600:1f18:d1f:bd00::/56` |
