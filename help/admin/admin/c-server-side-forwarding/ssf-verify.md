---
description: Para comprobar que el reenvío del lado del servidor esté correctamente habilitado, debe inspeccionar la respuesta HTTP a la solicitud de seguimiento de Analytics. Puede hacerse empleando las herramientas para desarrolladores de un navegador o una herramienta para proxys, como Charles Web Debugger. Las siguientes instrucciones ilustran qué indicadores debe haber presentes para garantizar que el reenvío del lado del servidor esté correctamente habilitado.
solution: Audience Manager
title: Comprobar la implementación del reenvío del lado del servidor
uuid: e37296cc-0120-486a-a4ca-78d648cf6a11
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Comprobar la implementación del reenvío del lado del servidor

Para comprobar que el reenvío del lado del servidor esté correctamente habilitado, debe inspeccionar la respuesta HTTP a la solicitud de seguimiento de Analytics. Puede hacerse empleando las herramientas para desarrolladores de un navegador o una herramienta para proxys, como Charles Web Debugger. Las siguientes instrucciones ilustran qué indicadores debe haber presentes para garantizar que el reenvío del lado del servidor esté correctamente habilitado.

Para comprobar el estado del reenvío del lado del servidor:

1. Cargue una página de prueba que contenga código de AppMeasurement actualizado.
1. En las herramientas de depuración del navegador, o utilizando su software proxy, inspeccione la respuesta HTTP de la solicitud de seguimiento de Analytics (puede filtrarla fácilmente seleccionando cualquier ruta que contenga “b/ss”).
1. Inspeccione la respuesta HTTP. Si la respuesta contiene datos de Audience Manager (como se ilustra a continuación), el reenvío del lado del servidor está funcionando.

![](assets/ssf-succeed.png)

>[!CAUTION]
>
>Si la respuesta contiene el par clave-valor `"status":"SUCCESS"` o una imagen 2 x 2, el reenvío del lado del servidor no está configurado correctamente. Compruebe que el servicio de identidad esté correctamente implementado, que haya implementado el módulo AppMeasurement, que el grupo de informes aplicable esté asignado a la organización IMS correcta y que el reenvío del lado del servidor esté habilitado en Admin Console de Analytics.

>[!MORELIKETHIS]
>
>* [Charles Web Debugger](https://www.charlesproxy.com/)

