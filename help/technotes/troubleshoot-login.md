---
title: Inicio de sesión para resolver problemas en Adobe Analytics
description: Pasos a seguir cuando no se puede iniciar sesión en Adobe Analytics.
exl-id: e670a043-c55b-4717-9b60-613ea4d04382
source-git-commit: d198e8ef0ec8415a4a555d3c385823baad6104fe
workflow-type: tm+mt
source-wordcount: '611'
ht-degree: 98%

---

# Inicio de sesión para resolver problemas en Adobe Analytics

Adobe Analytics utiliza varios métodos de autenticación para iniciar sesión:

* Adobe ID a través de Experience Cloud
* ID de Analytics heredado
* Inicio de sesión único

**Si accede con regularidad a Analytics y comienza a encontrar problemas de inicio de sesión de forma aleatoria, la mayoría de los problemas se resuelven al borrar las cookies y la caché del explorador.**

Ocasionalmente, los problemas de disponibilidad pueden afectar a la capacidad de iniciar sesión. Compruebe en [status.adobe.com](https://status.adobe.com) si hay algún incidente abierto. De lo contrario, utilice la sección adecuada según el método de autenticación de su organización.

## Adobe ID

Solucione los problemas con el inicio de sesión en Adobe Analytics mediante Experience Cloud.

1. Vaya a [experience.adobe.com](https://experience.adobe.com). Si no puede acceder a este sitio, es posible que su organización no permita este dominio a través del cortafuegos. Colabore con el equipo informático de su organización para posibilitarlo. Consulte [IP y dominios utilizados en Adobe Experience Cloud](https://helpx.adobe.com/es/analytics/kb/adobe-ip-addresses.html) para obtener información útil que proporcionar a su equipo de TI.

2. Autentíquese con Adobe ID: Haga clic en **[!UICONTROL Iniciar sesión con un Adobe ID]**. Si no puede iniciar sesión, compruebe que su dirección de correo electrónico esté escrita correctamente. De lo contrario, haga clic en **[!UICONTROL Restablecer contraseña]** y siga las indicaciones para restablecer la contraseña de Adobe ID.

3. Obtenga acceso a Analytics después de autenticarse: Haga clic en el icono de 9 cuadrículas en la parte superior derecha y, a continuación, haga clic en Analytics. Si no tiene esta opción o está atenuada, trabaje con un administrador de productos de su organización para asegurarse de que tiene los permisos correctos para acceder a Analytics.

## ID de Analytics heredado

Un usuario de su organización puede recibir el siguiente error cuando intenta iniciar sesión:

*Como medida de seguridad, esta cuenta se ha bloqueado debido a la cantidad de intentos fallidos de iniciar sesión.*

Si la eliminación de las cookies o la caché del explorador no resuelve el problema, póngase en contacto con un administrador de Analytics de su organización para restablecer la contraseña del usuario.

>[!IMPORTANT]
>
>Los siguientes pasos para restablecer la contraseña de un usuario solo se aplican a los ID de Analytics heredados, no a los de Adobe ID. Si su organización utiliza Adobe ID, puede administrar las cuentas de usuario en [adminconsole.adobe.com](https://adminconsole.adobe.com).

1. Inicie sesión en Adobe Analytics con una cuenta que tenga derechos administrativos.
2. Vaya a **[!UICONTROL Administración]** > **[!UICONTROL Todos los administradores]** > **[!UICONTROL Administración de usuarios]**.
3. Haga clic en la pestaña **[!UICONTROL Uuarios]** y luego en **[!UICONTROL Editar]** junto al usuario deseado.
4. Cambie la contraseña a cualquier valor y marque la casilla **[!UICONTROL Requerir al usuario que cambie la contraseña en el próximo inicio de sesión]**.
5. Informe al usuario de la nueva contraseña.

## Inicio de sesión único

Póngase en contacto con un administrador de su organización para resolver los problemas de inicio de sesión único.

## Inicios de sesión caducados

Un usuario de su organización puede recibir el siguiente error cuando intenta iniciar sesión:

*Error: Este inicio de sesión ha caducado.*

Este error funciona según lo previsto. Adobe Analytics proporciona a los administradores la capacidad de establecer un intervalo de fechas en el que una cuenta de usuario sea válida. Si la fecha actual se encuentra fuera del intervalo de fechas válido para la cuenta, no podrá iniciar sesión. Trabaje con un administrador de Analytics de su organización para ampliar el intervalo de fechas válido del inicio de sesión. El Servicio de atención al cliente de Adobe no está autorizado a cambiar los intervalos de fechas de inicio de sesión válidos para las cuentas de usuario.

## Otros problemas de inicio de sesión

Si ninguno de los pasos anteriores funciona, determine la amplitud del problema de inicio de sesión:

* ¿Ocurre el problema al usar un explorador diferente o es en todos los exploradores?
* ¿Ocurre el problema en un equipo diferente de la red o en varios equipos?
* Intente iniciar sesión en una red diferente, como una conexión de datos móviles, una biblioteca o una red doméstica. ¿Está el problema presente en todas las redes?

Si el problema está aislado en su red, trabaje con el equipo informático de su organización para resolverlo. Si no se limita a una sola red, póngase en contacto con el Servicio de atención al cliente de Adobe.
