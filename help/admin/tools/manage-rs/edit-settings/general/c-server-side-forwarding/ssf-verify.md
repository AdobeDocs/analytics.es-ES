---
description: Para comprobar que el reenvío del lado del servidor está correctamente habilitado, deberá inspeccionar la respuesta HTTP de la solicitud de seguimiento de Analytics. Estas instrucciones ilustran qué indicadores deben estar presentes para garantizar que el reenvío del lado del servidor esté habilitado correctamente.
solution: Analytics
title: Comprobar la implementación del reenvío del lado del servidor
feature: Report Suite Settings
exl-id: 21db4572-da3c-43aa-a774-86a089656695
role: Admin
TQID: https://experienceleague.adobe.com/FpB4dk9D87gc24t5KG6WRJ-r8GFOvOEUlRTTjc6XFYI
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 246
ht-degree: 33%

---

# Comprobar la implementación del reenvío del lado del servidor

Para comprobar que el reenvío del lado del servidor está correctamente habilitado, deberá inspeccionar la respuesta HTTP de la solicitud de seguimiento de Analytics. Esto se puede hacer con las herramientas para desarrolladores de un explorador o con una herramienta de proxy como Charles Web Debugger. Las siguientes instrucciones ilustran qué indicadores deben estar presentes para garantizar que el reenvío del lado del servidor esté correctamente habilitado.

Para comprobar el estado del reenvío del lado del servidor:

1. Cargue una página de prueba que contenga código AppMeasurement actualizado.
1. En las herramientas de depuración del navegador o mediante el software proxy, inspeccione la respuesta HTTP de la solicitud de seguimiento de Analytics (puede filtrarla fácilmente seleccionando cualquier ruta que contenga &quot;b/ss&quot;).
1. Inspeccione la respuesta HTTP. Si la respuesta contiene datos de Audience Manager (como se muestra a continuación), el reenvío del lado del servidor funciona.

![](/help/admin/tools/manage-rs/edit-settings/general/c-server-side-forwarding/assets/ssf-succeed.png)

>[!CAUTION]
>
>Si la respuesta contiene el par clave-valor `"status":"SUCCESS"` o una imagen 2 x 2, el reenvío del lado del servidor no está configurado correctamente. Compruebe que el servicio de identidad esté correctamente implementado, que haya implementado el módulo AppMeasurement, que el grupo de informes aplicable esté asignado al ID de organización correcto y que el reenvío del lado del servidor esté habilitado en las herramientas de administración de Analytics.

>[!MORELIKETHIS]
>
>* [Charles Web Debugger](https://www.charlesproxy.com/)
