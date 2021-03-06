---
title: Algoritmos de cifrado HTTPS admitidos
description: El 23 de junio de 2022, se eliminará la compatibilidad con cifrados TLS 1.2 que utilicen SHA1 o CBC para clientes con un nivel de seguridad cifrado establecido en "Alto".
feature: Regional Data Collection
source-git-commit: ce607610516a94e4d0fbbc53a1f8f53f5977a777
workflow-type: tm+mt
source-wordcount: '273'
ht-degree: 0%

---


# Algoritmos de cifrado HTTPS admitidos

Adobe ofrece dos niveles de seguridad de cifrado para satisfacer las distintas necesidades de seguridad de los clientes en la recopilación de datos de origen. Estos niveles determinan qué algoritmos de codificación se admiten para conexiones HTTPS con nuestros servidores. Los clientes toman el valor predeterminado &quot;Estándar&quot;, que solo admite algoritmos de codificación modernos. ‘High’ admite una lista más pequeña de algoritmos de codificación para clientes más preocupados por estas conexiones. Para ambos niveles de seguridad, Adobe actualiza regularmente el conjunto de algoritmos admitidos en función de las prácticas de seguridad actuales. Si desea cambiar la configuración de seguridad de cifrado, póngase en contacto con el Servicio de atención al cliente.

El 23 de junio de 2022, se eliminará la compatibilidad con cifrados TLS 1.2 que utilicen SHA1 o CBC para clientes con un nivel de seguridad cifrado establecido en &quot;Alto&quot;.  Este cambio afectará a la recopilación de datos segura para los usuarios finales en sistemas operativos más antiguos.

Ya no se admitirán los siguientes cifrados TLS 1.2:

* TLS_ECDHE_ECDSA_WITH_AES_128_CBC_SHA
* TLS_ECDHE_ECDSA_WITH_AES_256_CBC_SHA
* TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA
* TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA
* TLS_RSA_WITH_AES_128_CBC_SHA
* TLS_RSA_WITH_AES_256_CBC_SHA

Se sabe que los siguientes clientes se ven afectados por este cambio porque carecen de compatibilidad con los estándares de cifrado actuales:

* Windows 8.1 y versiones anteriores (última actualización en 2018)
* Windows Phone 8.1 y versiones anteriores (última actualización en 2016)
* OS X 10.10 y versiones anteriores (última actualización en 2017)
* iOS 8.4 y versiones anteriores (última actualización en 2015)

Los dispositivos Android no se ven afectados por este cambio.

Los clientes con un nivel de seguridad cifrado establecido en &quot;Estándar&quot; no se ven afectados por este cambio.

