---
description: Para comprobar que el reenvío del lado del servidor esté correctamente habilitado, debe inspeccionar la respuesta HTTP a la solicitud de seguimiento de Analytics. Estas instrucciones ilustran qué indicadores deben estar presentes para garantizar que el reenvío del lado del servidor esté habilitado correctamente.
solution: Analytics
title: Comprobar la implementación del reenvío del lado del servidor
feature: Server-Side Forwarding
exl-id: 21db4572-da3c-43aa-a774-86a089656695
role: Admin
source-git-commit: def7d071de1765acf524a638a8f8d13ae69e1a1f
workflow-type: tm+mt
source-wordcount: '235'
ht-degree: 86%

---

# Comprobar la implementación del reenvío del lado del servidor

Para comprobar que el reenvío del lado del servidor esté correctamente habilitado, debe inspeccionar la respuesta HTTP a la solicitud de seguimiento de Analytics. Puede hacerse empleando las herramientas para desarrolladores de un navegador o una herramienta para proxys, como Charles Web Debugger. Las siguientes instrucciones ilustran qué indicadores deben estar presentes para garantizar que el reenvío del lado del servidor esté correctamente habilitado.

Para comprobar el estado del reenvío del lado del servidor:

1. Cargue una página de prueba que contenga código de AppMeasurement actualizado.
1. En las herramientas de depuración del navegador, o utilizando su software proxy, inspeccione la respuesta HTTP de la solicitud de seguimiento de Analytics (puede filtrarla fácilmente seleccionando cualquier ruta que contenga “b/ss”).
1. Inspeccione la respuesta HTTP. Si la respuesta contiene datos de Audience Manager (como se ilustra a continuación), el reenvío del lado del servidor está funcionando.

![](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-server-side-forwarding/assets/ssf-succeed.png)

>[!CAUTION]
>
>Si la respuesta contiene el par clave-valor `"status":"SUCCESS"` o una imagen 2 x 2, el reenvío del lado del servidor no está configurado correctamente. Compruebe que el servicio de identidad esté correctamente implementado, que haya implementado el módulo AppMeasurement, que el grupo de informes aplicable esté asignado al ID de organización correcto y que el reenvío del lado del servidor esté habilitado en las herramientas de administración de Analytics.

>[!MORELIKETHIS]
>
>* [Charles Web Debugger](https://www.charlesproxy.com/)
