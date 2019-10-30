---
description: El indicador de anulación se puede configurar dentro de doPlugins para hacer que no se envíe la llamada de seguimiento actual.
keywords: Implementación de Analytics
seo-description: El indicador de anulación se puede configurar dentro de doPlugins para hacer que no se envíe la llamada de seguimiento actual.
seo-title: Indicador s.abort
solution: Analytics
title: Indicador s.abort
topic: Desarrollador e implementación
uuid: 0c6ec8c7-d136-4851-8cb6-6cb1b7f6f0dc
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

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
