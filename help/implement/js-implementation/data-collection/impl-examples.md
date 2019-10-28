---
description: Las implementaciones aquí descritas usan adobe.com como ejemplo y hacen referencia a la misma cookie visid.
keywords: Implementación de Analytics
seo-description: Las implementaciones aquí descritas usan adobe.com como ejemplo y hacen referencia a la misma cookie visid.
seo-title: Ejemplo de implementación
solution: Analytics
title: Ejemplo de implementación
topic: Desarrollador e implementación
uuid: 17d8d2b2-2303-495a-b0f9-d8d3c05f3893
translation-type: ht
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Ejemplo de implementación

Las implementaciones aquí descritas usan adobe.com como ejemplo y hacen referencia a la misma cookie visid.

**Javascript:**

```js
var s_account="omniturecom" 
s.visitorNamespace="omniture" 
s.trackingServer="omniture.112.2o7.net"
```

**Solicitud de imagen codificada:**

```
<img border="0" alt="" src="https://omniture.112.2o7.net/b/ss/omniturecom/5?ns=omniture" width="1" height="1" /> 
```

**Appmeasurement:**

```js
s.account="omniturecom"; 
s.visitorNamespace="omniture"; 
s.trackingServer="omniture.112.2o7.net";
```

Y si se utilizan cookies de origen:

**Javascript:**

```js
var s_account="omniturecom" 
s.visitorNamespace"omniture" 
s.trackingServer="metrics.omniture.com"
```

**Solicitud de imagen codificada:**

```
<img border="0" alt="" src="https://metrics.omniture.com/b/ss/omniturecom/5" width="1" height="1" />
```

**Appmeasurement:**

```js
s.account="omniturecom"; 
s.visitorNamespace="omniture"; 
s.trackingServer="metrics.omniture.com";
```

