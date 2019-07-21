---
description: El indicador de anulación se puede configurar dentro de doPlugins para hacer que no se envíe la llamada de seguimiento actual.
keywords: Implementación de Analytics
seo-description: El indicador de anulación se puede configurar dentro de doPlugins para hacer que no se envíe la llamada de seguimiento actual.
seo-title: Indicador s.abort
solution: Analytics
title: Indicador s.abort
topic: Desarrollador e implementación
uuid: 0 c 6 ec 8 c 7-d 136-4851-8 cb 6-6 cb 1 b 7 f 6 f 0 dc
translation-type: tm+mt
source-git-commit: ee0cb9b64a3915786f8f77d80b55004daa68cab6

---


# Indicador s.abort

El indicador de anulación se puede configurar dentro de doPlugins para hacer que no se envíe la llamada de seguimiento actual.

El indicador de anulación se restablece con cada llamada de seguimiento, así que si también se tiene que cancelar una llamada de seguimiento posterior, de nuevo se tendrá que configurar el indicador dentro de doPlugins.

```js
s.doPlugins = function(s) { 
     s.campaign = s.getQueryParam("cid"); 
     if ((!s.campaign) && (!s.events)) { 
          s.abort = true; 
     } 
};
```

Esto permite centralizar la lógica utilizada para identificar la actividad que no se quiere seguir, por ejemplo algunos vínculos personalizados o vínculos externos para mostrar anuncios.
