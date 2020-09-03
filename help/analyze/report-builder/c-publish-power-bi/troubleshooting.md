---
description: Problemas comunes al usar Report Builder con Power BI.
title: Solución de problemas de integración de Power BI
uuid: c1e7e164-4bc6-4513-9332-92c53be021cc
translation-type: tm+mt
source-git-commit: 3aae3b00db1d7f720641ed5ccbefd8acc03460e3
workflow-type: tm+mt
source-wordcount: '370'
ht-degree: 51%

---


# Solución de problemas de integración de Power BI

Investigue y resuelva problemas comunes al usar Report Builder con Power BI.

## Error al publicar en Power BI

Los libros programados que requieren la publicación en Power BI dependen de los servicios de Power BI para funcionar y ejecutarse. Dos de los principales motivos de error en la publicación son:

* Los servicios de Power BI pueden estar caídos.
* El usuario que programó el libro ya no dispone de credenciales en una cuenta Microsoft válida.

Cada tarea programada de Report Builder intenta ejecutarse hasta tres veces:

* Tras el primer intento fallido se recibe este mensaje: &quot;No ha sido posible publicar este libro programado en Microsoft Power BI. Se intentará de nuevo en breve.&quot;
* Tras el segundo intento fallido no se recibe ningún mensaje.
* Tras el tercer intento fallido se recibe este mensaje: &quot;No ha sido posible publicar este libro en Power BI&quot;.

## Errores en las visualizaciones en Power BI

Estas son las principales razones que pueden provocar errores en las visualizaciones al publicar en Power BI solicitudes de Report Builder:

* Se editó una solicitud en Report Builder (p. ej., se cambiaron métricas o dimensiones) y después se volvió a publicar en Power BI. Editar las solicitudes puede provocar errores en las visualizaciones.
* Se eliminó una solicitud empleada en una visualización.

## Es necesario autorizar al Report Builder para que acceda a los recursos de su organización. Este acceso sólo lo puede otorgar un administrador. Pida a un administrador que le conceda permiso.

Haga que el administrador de Microsoft revise la configuración &quot;Los usuarios pueden registrar la aplicación&quot; que se encuentra en: **[!UICONTROL Microsoft Azure]** > **[!UICONTROL Azure Active Directory]** > Configuración **[!UICONTROL de usuario permite opciones]**. Si esta opción está establecida en No, ese administrador puede registrar estos tipos de aplicaciones.

Los usuarios pueden otorgar acceso mediante el siguiente [vínculo](https://login.microsoftonline.com/common/oauth2/authorize?response_type=code&amp;prompt=logint&amp;client_id=8d84f6d8-29a4-4484-a670-589b32400278&amp;redirect_uri=https%3a%2f%2fmy.omniture.com%2fsc15%2farb%2flogin.html&amp;resource=https%3a%2f%2fanalysis.windows.net%2fpowerbi%2fapi&amp;locale=en_US).

Los administradores concedieron acceso a cada uno mediante el siguiente [vínculo](https://login.microsoftonline.com/common/oauth2/authorize?response_type=code&amp;prompt=admin_consent&amp;client_id=8d84f6d8-29a4-4484-a670-589b32400278&amp;redirect_uri=https%3a%2f%2fmy.omniture.com%2fsc15%2farb%2flogin.html&amp;resource=https%3a%2f%2fanalysis.windows.net%2fpowerbi%2fapi&amp;locale=en_US).
