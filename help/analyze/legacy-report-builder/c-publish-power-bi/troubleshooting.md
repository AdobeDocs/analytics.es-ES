---
description: Problemas comunes al utilizar Report Builder con Power BI.
title: Solución de problemas de integración de Power BI
feature: Report Builder
role: User, Admin
exl-id: adb13a0e-99fb-48f5-add2-204d155e467f
source-git-commit: 73c0210ac931f3e7f823e033a3bffdc22e159ddb
workflow-type: tm+mt
source-wordcount: '320'
ht-degree: 66%

---

# Solución de problemas de integración de Power BI

{{legacy-arb}}

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

>[!IMPORTANT]
>
>Report Builder requiere un administrador para autorizar el acceso a los recursos de su organización. Si necesita acceso, pida a un administrador que le conceda permiso.
> Un administrador de Microsoft puede revisar la configuración *Los usuarios pueden registrar la aplicación* que se encuentra en: **[!UICONTROL Microsoft Azure]** > **[!UICONTROL Azure Active Directory]** > **[!UICONTROL Configuración de usuario permite opciones]**. Si esta opción se establece en **No**, el administrador puede registrar este tipo de aplicaciones.

Los usuarios pueden conceder acceso iniciando sesión en su [cuenta de Microsoft Power BI](https://login.microsoftonline.com/common/oauth2/authorize?response_type=code&amp;prompt=logint&amp;client_id=8d84f6d8-29a4-4484-a670-589b32400278&amp;redirect_uri=https%3a%2f%2fmy.omniture.com%2fsc15%2farb%2flogin.html&amp;resource=https%3a%2f%2fanalysis.windows.net%2fpowerbi%2fapi&amp;locale=en_US).

Los administradores pueden conceder acceso a cada uno iniciando sesión en su [cuenta de Microsoft Power BI del administrador](https://login.microsoftonline.com/common/oauth2/authorize?response_type=code&amp;prompt=admin_consent&amp;client_id=8d84f6d8-29a4-4484-a670-589b32400278&amp;redirect_uri=https%3a%2f%2fmy.omniture.com%2fsc15%2farb%2flogin.html&amp;resource=https%3a%2f%2fanalysis.windows.net%2fpowerbi%2fapi&amp;locale=en_US).

## Alcanzar el límite de API

La creación de informes en Power BI funciona con la API de informes de Analytics, por lo que se aplican límites de umbral de API.
