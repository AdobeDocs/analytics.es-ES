---
title: IP y dominios utilizados por Adobe Analytics
description: Si el cortafuegos de su organización bloquea las direcciones IP que se originan en Adobe, utilice esta lista para actualizar la configuración del cortafuegos.
exl-id: e24a70e4-9ed4-4b87-8bab-4ed0aebedd1f
source-git-commit: 4460850971fe822ff8a0ebf3e3269d0e573fa1db
workflow-type: tm+mt
source-wordcount: '408'
ht-degree: 98%

---

# IP y dominios utilizados por Adobe Analytics

La configuración de algunos cortafuegos bloquea las direcciones IP que se originan de los servidores de recopilación de datos de Adobe o de los servidores responsables de acceder a datos. Puede utilizar esta lista de intervalos para modificar la configuración del cortafuegos de su organización y permitir el acceso y enviar datos desde su organización.

>[!IMPORTANT]
>
>A pesar del esfuerzo que realiza por mantener actualizado este documento, Adobe no puede garantizar que la lista de intervalos de IP sea la misma. Los posibles cambios incluyen el crecimiento y la expansión del negocio, un registro de Internet requiere cambios en el espacio de direcciones IP del Adobe o un proveedor de servicio de Internet deja de funcionar.

## Permitir dominios de tecnología dependientes

Adobe Analytics utiliza los siguientes hosts para mejorar el rendimiento y la experiencia del producto. Adobe recomienda añadir estos dominios a la lista de permitidos del cortafuegos para una experiencia óptima con Adobe Analytics.

| Tecnología | Dominio |
| --- | --- |
| Dominios de Adobe Analytics | `adobe.com`, `adobe.net`, `adobe.io` |
| Dominio heredado de Adobe Analytics | `omniture.com` |
| Amazon AWS | `aaui-879784980514.s3.us-east-2.amazonaws.com` |
| Amazon CloudFront | `d30ln29764hddd.cloudfront.net` |
| Gainsight | `esp.aptrinsic.com` |
| LaunchDarkly | `app.launchdarkly.com` |
| Almacenamiento de Microsoft Azure Blob | `awaascicdprodva7.blob.core.windows.net` |
| CDN de Microsoft Azure | `aauicdnva7.azureedge.net` |

## Todos los bloques de direcciones IP de recopilación de datos de Adobe Analytics

La siguiente tabla abarca todos los servidores de recopilación de datos estándar y los servidores de recopilación de datos regionales para Adobe Analytics. No incluyen hosts de AWS individuales.

| Bloque IP (Notación CIDR) |
| --- |
| `63.140.32.0/19` |
| `66.117.16.0/20` |
| `66.235.128.0/19` |
| `130.248.0.0/16` |
| `172.82.192.0/18` |
| `185.34.188.0/22` |
| `192.243.224.0/19` |
| `205.219.231.0/24` |
| `208.67.40.0/22` |
| `208.77.136.0/22` |

## Bloques de direcciones IP de FTP y recopilación de datos

Si su organización prefiere permitir intervalos específicos de direcciones IP, puede utilizar la siguiente tabla. Todos los intervalos de esta sección se incluyen en la tabla anterior.

| Ubicación | Intervalo IP (Notación CIDR) |
| --- | --- |
| Ámsterdam | `66.117.28.0/23` |
| Dallas | `205.219.231.0/24` |
| Dallas | `66.235.152.0/22` |
| Dallas | `66.235.140.0/22` |
| Dallas | `63.140.32.0/21` |
| Dallas | `172.82.208.0/22` |
| RAE de Hong Kong de China | `66.117.24.0/22` |
| Londres | `66.235.156.0/24` |
| Londres | `66.235.148.0/23` |
| Londres | `63.140.40.0/22` |
| Londres | `208.67.41.0/24` |
| Londres | `192.243.254.0/23` |
| Londres | `192.243.244.0/22` |
| Londres | `185.34.188.0/23` |
| Londres | `130.248.152.0/21` |
| Londres | `172.82.224.0/21` |
| Londres | `172.82.232.0/21` |
| Oregón | `192.243.240.0/22` |
| Oregón | `192.243.232.0/21` |
| Oregón | `192.243.224.0/21` |
| Oregón | `130.248.160.0/21` |
| Oregón | `130.248.148.0/22` |
| Oregón | `172.82.192.0/21` |
| Oregón | `172.82.216.0/21` |
| París | `208.67.40.0/24` |
| Singapur | `66.235.150.0/24` |
| Singapur | `66.235.130.0/23` |
| Singapur | `63.140.44.0/22` |
| Singapur | `208.67.43.0/24` |
| Singapur | `172.82.240.0/22` |
| Singapur | `172.82.246.0/23` |
| Singapur | `172.82.248.0/21` |
| San Jose | `66.117.20.0/24` |
| San José | `66.235.132.0/22` |
| San José | `130.248.128.0/22` |
| San José | `192.243.248.0/23` |
| San José | `172.82.200.0/22` |
| San José | `66.235.136.0/22` |
| San José | `208.91.175.0/24` |
| San José | `208.91.174.0/24` |
| San José | `208.91.169.0/24` |
| Sídney | `216.104.216.0/23` |
| Tokio | `66.235.159.0/24` |
| Tokio | `66.117.21.0/24` |
| Tokio | `63.140.52.0/24` |
| Tokio | `63.140.50.0/23` |
| Virginia | `66.235.144.0/22` |
| Virginia | `208.77.138.0/23` |
| Virginia | `208.77.136.0/23` |
| Virginia | `192.243.250.0/23` |
| Virginia | `130.248.144.0/22` |
| Virginia | `172.82.204.0/22` |
| Virginia | `172.82.212.0/22` |
| Virginia | Consulte los hosts de AWS |

## Hosts de AWS

Adobe Analytics utiliza los servicios web de Amazon como parte de su proceso de recopilación de datos. La siguiente tabla incluye hosts de AWS reservados para Adobe. Estos hosts **no** están incluidos en el intervalo de bloques acumulado anterior.

| Ubicación | Host |
| --- | --- |
| Australia | `13.54.219.183` |
| Australia | `52.62.137.88` |
| Australia | `54.79.162.112` |
| China | `52.81.111.133` |
| China | `140.179.22.22` |
| Francia | `13.36.218.177` |
| Francia | `15.188.95.229` |
| Francia | `15.236.176.210` |
| India | `65.0.114.116` |
| India | `65.0.115.179` |
| India | `65.0.25.111` |
| India | `13.233.180.137` |
| India | `65.0.111.130` |
| India | `52.66.172.181` |
| Irlanda | `18.202.158.78` |
| Irlanda | `54.72.205.114` |
| Irlanda | `54.78.36.71` |
| Irlanda | `54.220.133.225` |
| Irlanda | `54.74.170.177` |
| Irlanda | `54.195.254.128` |
| Oregón | `44.233.255.254` |
| Oregón | `44.237.54.118` |
| Oregón | `44.238.157.95` |
| Oregón | `54.212.155.93` |
| Oregón | `52.10.149.115` |
| Oregón | `52.40.172.46` |
| Singapur | `52.220.116.94` |
| Singapur | `52.76.68.91` |
| Singapur | `54.179.114.68` |
| Singapur | `54.255.88.178` |
| Singapur | `52.220.235.10` |
| Singapur | `3.1.237.132` |
| Tokio | `18.182.161.178` |
| Tokio | `54.168.58.167` |
| Tokio | `54.178.61.109` |
| Tokio | `3.113.78.189` |
| Tokio | `13.115.137.161` |
| Tokio | `54.178.162.114` |
| Virginia | `3.213.168.181` |
| Virginia | `3.219.249.186` |
| Virginia | `3.220.129.153` |
| Virginia | `18.206.109.10` |
| Virginia | `18.211.197.67` |
| Virginia | `34.227.41.189` |
| Virginia | `34.228.124.176` |
| Virginia | `54.90.190.103` |
| Virginia | `54.174.149.161` |
