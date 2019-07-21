---
description: Al seguir estas directrices se usan los mismos dominios de cookies, lo que permite realizar el seguimiento de las visitas en diferentes tipos de implementaciones.
keywords: Implementación de Analytics
seo-description: Al seguir estas directrices se usan los mismos dominios de cookies, lo que permite realizar el seguimiento de las visitas en diferentes tipos de implementaciones.
seo-title: Directrices de implementación
solution: Analytics
title: Directrices de implementación
topic: Desarrollador e implementación
uuid: 2917 f 4 af -19 bd -4666-ae 4 b -056 e 7 e 33 f 642
translation-type: tm+mt
source-git-commit: 76d0ce11d9b560e0df866be9e753804b6fa4bb3d

---


# Directrices de implementación

Al seguir estas directrices se usan los mismos dominios de cookies, lo que permite realizar el seguimiento de las visitas en diferentes tipos de implementaciones.

* **RSID:** [!UICONTROL ID del grupo de informes]
* **VNS:** Espacio de nombres de visitantes, subdominio de [!DNL 2o7.net] o [!DNL omtrdc.net] usado para almacenar la cookie de [!UICONTROL ID de visitante]
* **COOKIEDOMAIN:** Su VNS + trackingServer. En función de la configuración RDC y del centro de datos, estas pueden variar considerablemente. [Póngase en contacto con el Servicio](https://helpx.adobe.com/contact/enterprise-support.ec.html#analytics) de atención al cliente si no está seguro de su dominio de recopilación de datos.

## Javascript

```javascript
var s_account="RSID" 
s.visitorNamespace="VNS" 
s.trackingServer="VNS.COOKIEDOMAIN.net" 
```

## AppMeasurement

```javascript
var s_account="RSID" 
s.visitorNamespace="VNS" 
s.trackingServer="VNS.COOKIEDOMAIN.net" 
```

## Solicitud de imagen codificada

```javascript
<img border="0" alt="" src="https://VNS.COOKIEDOMAIN.net/b/ss/RSID/5?ns=VNS" width="1" height="1" /> 

<!-- Note that the visitor namespace is defined twice in hardcoded image requests; once in the http subdomain, and another using the ns= query string parameter! -->
```

Si utiliza una implementación de cookie de origen, `VNS.COOKIEDOMAIN.net` se puede sustituir por el dominio de cookie de origen utilizado. Por ejemplo, las cookies de origen en `adobe.com` se sustituirían por algo similar a `metrics.adobe.com`.
