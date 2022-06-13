---
description: Problemas comunes al utilizar Report Builder con Power BI.
title: Solución de problemas de integración de Power BI
feature: Report Builder
role: User, Admin
exl-id: adb13a0e-99fb-48f5-add2-204d155e467f
source-git-commit: b98fbf52ab9fefef9c19e82f440ca9f5a81f933f
workflow-type: tm+mt
source-wordcount: '554'
ht-degree: 66%

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

## Report Builder debe estar autorizado para acceder a los recursos de su organización. Este acceso solo lo puede conceder un administrador. Solicite a un administrador que le conceda permiso.

Pida a un administrador de Microsoft que revise la configuración &quot;Los usuarios pueden registrar la aplicación&quot; que se encuentra en: **[!UICONTROL Microsoft Azure]** > **[!UICONTROL Azure Active Directory]** > **[!UICONTROL Configuración de usuario permite opciones]**. Si esta opción está configurada en No, ese administrador puede registrar estos tipos de aplicaciones.

Los usuarios pueden otorgar acceso utilizando el siguiente [vínculo](https://login.microsoftonline.com/common/oauth2/authorize?response_type=code&amp;prompt=logint&amp;client_id=8d84f6d8-29a4-4484-a670-589b32400278&amp;redirect_uri=https%3a%2f%2fmy.omniture.com%2fsc15%2farb%2flogin.html&amp;resource=https%3a%2f%2fanalysis.windows.net%2fpowerbi%2fapi&amp;locale=en_US).

Los administradores pueden acceder a cada uno de ellos utilizando el siguiente [vínculo](https://login.microsoftonline.com/common/oauth2/authorize?response_type=code&amp;prompt=admin_consent&amp;client_id=8d84f6d8-29a4-4484-a670-589b32400278&amp;redirect_uri=https%3a%2f%2fmy.omniture.com%2fsc15%2farb%2flogin.html&amp;resource=https%3a%2f%2fanalysis.windows.net%2fpowerbi%2fapi&amp;locale=en_US).

## Alcance del límite de API

La creación de informes en Power BI funciona con la API de informes de Analytics, por lo que se aplican límites de umbral de API. Para las API de Analytics 2.0, el límite de aceleración se establece en 120 llamadas por minuto, por usuario, independientemente del grupo de informes o la empresa. Cuando se cruza el límite del acelerador, el servidor devuelve un estado HTTP 429 al usuario con este contenido del mensaje:

```
too many requests
{"error_code":"429050","message":"Too many requests"}
```

Adobe recomienda que *adhere to* las siguientes directrices:

* Realice varias solicitudes más pequeñas en lugar de una solicitud grande y única.
* Solicite datos una vez y almacénelos en caché.
* No sondee los datos nuevos con más rapidez que un intervalo de 30 minutos.
* Extraiga los datos históricos e incremente con regularidad en lugar de solicitar todo el conjunto de datos.

Adobe recomienda que *evita* lo siguiente:

* Solicitar tantos datos como sea posible en una única solicitud
* Solicite un año de datos en la granularidad de día todos los días para obtener una ventana móvil de 12 meses. Adobe recomienda que, en su lugar, solicite los datos del nuevo día y los combine con los datos existentes de días anteriores.
* Impulse una página web con un widget de rendimiento del sitio realizando una solicitud de API cada vez que se carga la página web
* Migración de 1.4
