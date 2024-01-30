---
title: IP y dominios utilizados por Adobe Analytics
description: Si el cortafuegos de su organización bloquea las direcciones IP que se originan en Adobe, utilice esta lista para actualizar la configuración del cortafuegos.
feature: Data Configuration and Collection
exl-id: e24a70e4-9ed4-4b87-8bab-4ed0aebedd1f
source-git-commit: e4f8467e9c2e3f461857b4ea3d4e5cbe643d57a0
workflow-type: tm+mt
source-wordcount: '393'
ht-degree: 67%

---

# IP y dominios utilizados por Adobe Analytics

La configuración de algunos cortafuegos bloquea las direcciones IP que se originan de los servidores de recopilación de datos de Adobe o de los servidores responsables de acceder a datos. Puede utilizar esta lista de intervalos para modificar la configuración del cortafuegos de su organización y permitir el acceso y enviar datos desde su organización. Esta página incluye sistemas entrantes (como la recopilación de datos) y salientes (como las fuentes de datos) que utiliza el Adobe.

>[!IMPORTANT]
>
>Aunque Adobe hace todo lo posible para mantener este documento actualizado, no puede garantizar que la lista de intervalos de IP sea la misma. Los posibles cambios incluyen el crecimiento y la expansión del negocio, un registro de Internet requiere cambios en el espacio de direcciones IP del Adobe o un proveedor de servicio de Internet deja de funcionar.

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

## Todos los bloques de direcciones IP de Adobe Analytics

La siguiente tabla abarca todas las direcciones IP de propiedad del Adobe utilizadas para Adobe Analytics. No incluyen todos los servicios alojados en nubes públicas.

| Bloque IP (Notación CIDR) |
| --- |
| `63.140.32.0/19` |
| `66.117.16.0/20` |
| `66.235.128.0/19` |
| `130.248.0.0/16` |
| `185.34.188.0/22` |

## Bloques de direcciones IP de FTP y recopilación de datos

Si su organización prefiere permitir intervalos específicos de direcciones IP, puede utilizar la siguiente tabla. Todos los intervalos de esta sección se incluyen en la tabla anterior. Las conexiones FTP para fuentes de datos y Data Warehouse solo se originan en las ubicaciones de Londres, Oregón y Singapur.

| Ubicación | Intervalo IP (Notación CIDR) |
| --- | --- |
| Australia | `63.140.55.0/24` |
| Australia | `63.140.56.0/23` |
| California | `63.140.32.0/23` |
| California | `63.140.34.0/24` |
| Francia | `63.140.62.0/23` |
| India | `66.117.20.0/24` |
| India | `66.117.22.0/23` |
| Japón | `130.248.169.0/23` |
| Japón | `63.140.50.0/23` |
| Japón | `66.117.31.0/24` |
| Londres | `66.235.156.0/24` |
| Londres | `185.34.188.0/22` |
| Londres | `130.248.152.0/22` |
| Londres | `130.248.244.0/23` |
| Oregón | `66.235.132.0/22` |
| Oregón | `130.248.130.0/23` |
| Oregón | `130.248.150.0/24` |
| Oregón | `130.248.160.0/21` |
| Oregón | `192.243.242.0/24` |
| Singapur | `130.248.170.0/23` |
| Singapur | `130.248.240.0/24` |
| Singapur | `63.140.44.0/22` |
| Singapur | `63.140.48.0/23` |
| Singapur | `66.117.30.0/24` |
| Virginia | `63.140.38.0/23` |
| Virginia | `63.140.54.0/24` |

## Hosts de AWS

Adobe Analytics utiliza los servicios web de Amazon como parte de su proceso de recopilación de datos. En la tabla siguiente se incluyen las direcciones de host IPv4 de AWS reservadas para el Adobe. Estos hosts **no** están incluidos en el intervalo de bloques acumulado anterior.

| Ubicación | Host |
| --- | --- |
| China | `52.80.168.159` |
| China | `52.80.199.104` |
| China | `54.223.199.8` |

En la tabla siguiente se incluyen los bloques de direcciones IPv6 de AWS que utiliza el Adobe. Estos hosts **no** están incluidos en el intervalo de bloques acumulado anterior.

| Ubicación | Host |
| --- | --- |
| Australia | `2406:da1c:406:1a00::/56` |
| Australia | `2406:da1c:ce5:b400::/56` |
| California | `2600:1f1c:366:d900::/56` |
| Francia | `2a05:d012:706:d000::/56` |
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
