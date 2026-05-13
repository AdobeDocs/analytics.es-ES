---
description: Problemas comunes al utilizar Report Builder con Power BI.
title: Solución de problemas de integración de Power BI
feature: Report Builder
role: User, Admin
exl-id: adb13a0e-99fb-48f5-add2-204d155e467f
TQID: https://experienceleague.adobe.com/Q4n08pGcqBwhUl5q3VnWhuVcW9E-tdvv3LoHSLoGleA
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32id: c153fd90-23e1-4614-81d3-3cc7571227f7id: f73667dc-d296-4875-8975-ac3fdc3adc42id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: c1579802-ddd4-4214-8a91-97b2066abe11
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 382
ht-degree: 40%

---

# Solución de problemas de integración de Power BI

{{legacy-arb}}

Investigue y resuelva problemas comunes al usar Report Builder con Power BI.

## Error al publicar en Power BI

Los libros programados que requieren la publicación en Power BI dependen de los servicios de Power BI para estar en funcionamiento. Dos razones principales para que no se publique son:

* Es posible que los servicios de Power BI no estén operativos.
* El usuario que programó el libro ya no tiene credenciales de cuenta de Microsoft válidas.

Cada tarea programada de Report Builder intenta ejecutarse hasta tres veces:

* Después del primer intento fallido, recibirá este mensaje: &quot;No hemos podido publicar este libro de trabajo programado en Microsoft Power BI. Lo intentaremos de nuevo en breve&quot;.
* Después del segundo intento fallido, no recibirá ningún mensaje.
* Después del tercer intento fallido, aparece el siguiente mensaje: &quot;No hemos podido publicar este libro en Power BI&quot;.

## Errores en las visualizaciones en Power BI

Estas son las principales razones que pueden provocar errores en las visualizaciones al publicar en Power BI solicitudes de Report Builder:

* Se editó una solicitud en Report Builder (p. ej., se cambiaron métricas o dimensiones) y después se volvió a publicar en Power BI. La edición de solicitudes puede interrumpir las visualizaciones.
* Ha eliminado una solicitud que se utilizaba en una visualización.

>[!IMPORTANT]
>
>Report Builder requiere un administrador para autorizar el acceso a los recursos de su organización. Si necesita acceso, pida a un administrador que le conceda permiso.
> Un administrador de Microsoft puede revisar la configuración *Los usuarios pueden registrar la aplicación* que se encuentra en: **[!UICONTROL Microsoft Azure]** > **[!UICONTROL Azure Active Directory]** > **[!UICONTROL Configuración de usuario permite opciones]**. Si esta opción se establece en **No**, el administrador puede registrar este tipo de aplicaciones.

Los usuarios pueden conceder acceso iniciando sesión en su [cuenta de Microsoft Power BI](https://login.microsoftonline.com/common/oauth2/authorize?response_type=code&prompt=logint&client_id=8d84f6d8-29a4-4484-a670-589b32400278&redirect_uri=https%3a%2f%2fmy.omniture.com%2fsc15%2farb%2flogin.html&resource=https%3a%2f%2fanalysis.windows.net%2fpowerbi%2fapi&locale=en_US).

Los administradores pueden conceder acceso a cada uno iniciando sesión en su [cuenta de Microsoft Power BI del administrador](https://login.microsoftonline.com/common/oauth2/authorize?response_type=code&prompt=admin_consent&client_id=8d84f6d8-29a4-4484-a670-589b32400278&redirect_uri=https%3a%2f%2fmy.omniture.com%2fsc15%2farb%2flogin.html&resource=https%3a%2f%2fanalysis.windows.net%2fpowerbi%2fapi&locale=en_US).

## Alcanzar el límite de API

La creación de informes en Power BI funciona con la API de informes de Analytics, por lo que se aplican límites de umbral de API.
