---
title: Algoritmos de cifrado HTTPS admitidos
description: Configuración de seguridad de cifrado TLS y tipos de certificado.
feature: Regional Data Collection
exl-id: f1cbb0cb-fd65-4f22-8594-0d97b6906698
source-git-commit: 1ca7f750387fd9ae034d10ebf3e47190cf33d4b7
workflow-type: tm+mt
source-wordcount: '282'
ht-degree: 25%

---

# Algoritmos de cifrado HTTPS admitidos

## Niveles de seguridad del cifrado

Adobe ofrece dos niveles de seguridad de cifrado para satisfacer las distintas necesidades de seguridad de los clientes en la recopilación de datos de origen. Estos niveles determinan qué algoritmos de codificación se admiten para conexiones HTTPS con servidores de Adobe. Adobe revisa y actualiza regularmente el conjunto de algoritmos compatibles en función de las prácticas de seguridad actuales. Si desea cambiar la configuración de seguridad de cifrado, póngase en contacto con el Servicio de atención al cliente.

&#39;Standard&#39; requiere TLS 1.2 o una versión posterior y al menos un cifrado de 128 bits. Está diseñado para proporcionar la mayor compatibilidad de dispositivos mientras se mantiene el cifrado seguro.

El nivel de seguridad de cifrado &quot;alto&quot; requiere TLS 1.2 o una versión posterior y ya no es compatible con cifrados más débiles. Está diseñado para los clientes que desean el cifrado más seguro y no se preocupan por la compatibilidad con dispositivos antiguos.

Se sabe que los siguientes clientes no pueden conectarse con el cifrado de seguridad establecido en &quot;Alto&quot;.

* Windows 8.1 y versiones anteriores (última actualización en 2018)
* Windows Phone 8.1 y versiones anteriores (última actualización en 2016)
* OS X 10.10 y versiones anteriores (última actualización en 2017)
* iOS 8.4 y versiones anteriores (última actualización en 2015)

## Tipos de certificados HTTPS compatibles

Adobe admite tipos de certificados RSA y ECC para satisfacer las distintas necesidades de los clientes. Los certificados RSA son más compatibles con los clientes, pero los certificados ECC utilizan menos procesamiento tanto en el servidor como en el cliente. Para los certificados administrados de Adobe, se proporcionan RSA y ECC. Para los certificados administrados por el cliente, se recomiendan RSA y ECC. Los clientes modernos admiten RSA y ECC. Se sabe que los siguientes clientes sólo admiten certificados RSA:

* Windows Vista y versiones anteriores (última actualización en 2012)
* Windows Phone 8.0 y versiones anteriores (última actualización en 2014)
* OS X 10.8 y versiones anteriores (última actualización en 2013)
* iOS 5.1 y versiones anteriores (última actualización en 2012)
* Android 4.3 y anteriores (última actualización en 2013)
