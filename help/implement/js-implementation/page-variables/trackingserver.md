---
description: Las variables de página rellenan directamente un informe, como pageName, Props de lista, Variables de lista, etc.
keywords: Analytics Implementation
subtopic: Variables
title: Variables de página
topic: null
uuid: null
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# trackingServer

La variable se utiliza para la implementación de cookies de origen a fin de especificar el dominio en el cual se escriben la solicitud de imagen y la cookie.


<!-- 

trackingServer.xml

 -->

Se utiliza para páginas no seguras. If *`trackingServer`* is defined, nothing goes to 2o7.net. Si *`trackingServer`* no está definida (y dc no está definido), los datos se dirigen a 112.2o7.net.

| Tamaño máximo | Parámetro depurador | Informes rellenados | Valor predeterminado |
|---|---|---|---|
| N/D | N/D | N/D | "" |

[Aquí](https://helpx.adobe.com/analytics/kb/determining-data-center.html) podrá consultar una lista de centros de datos de Adobe.