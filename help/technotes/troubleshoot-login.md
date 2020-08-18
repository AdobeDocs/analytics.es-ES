---
title: Solución de problemas de inicio de sesión en Adobe Analytics
description: Pasos a seguir cuando no se puede iniciar sesión en Adobe Analytics.
translation-type: tm+mt
source-git-commit: 0870ace3fea8e3ef650d2de2960006a0d655cf9f
workflow-type: tm+mt
source-wordcount: '511'
ht-degree: 3%

---


# Solución de problemas de inicio de sesión en Adobe Analytics

Adobe Analytics utiliza varios métodos de autenticación para iniciar sesión:

* Adobe ID a través del Experience Cloud
* ID de Analytics heredado
* Inicio de sesión único

**Si accede con regularidad a Analytics y al inicio aleatorio con problemas de inicio de sesión, la eliminación de las cookies y la caché del navegador resuelve la mayoría de los problemas.**

En ocasiones, los problemas de disponibilidad pueden afectar a la capacidad para iniciar sesión. Compruebe [status.adobe.com](https://status.adobe.com) para ver si hay algún incidente abierto. De lo contrario, utilice la sección adecuada en función del método de autenticación de su organización.

## Adobe ID

Solución de problemas con el inicio de sesión en Adobe Analytics mediante el Experience Cloud.

1. Vaya a [experience.adobe.com](https://experience.adobe.com). Si no puede acceder a este sitio, es posible que su organización no permita este dominio a través del servidor de seguridad. Trabaje con el equipo de TI de su organización para permitirlo. Consulte [IPs y dominios utilizados en Adobe Experience Cloud](https://helpx.adobe.com/es/analytics/kb/adobe-ip-addresses.html) para obtener información útil para el equipo de TI.

2. Autentique con Adobe ID: Haga clic en **[!UICONTROL Iniciar sesión con un Adobe ID]**. Si no puede iniciar sesión, doble compruebe que su dirección de correo electrónico esté escrita correctamente. De lo contrario, haga clic en **[!UICONTROL Restablecer contraseña]** y siga las indicaciones para restablecer la contraseña de Adobe ID.

3. Acceso a Analytics después de autenticar: Haga clic en el icono de 9 cuadrícula en la parte superior derecha y, a continuación, haga clic en Analytics. Si no tiene esta opción o está atenuada, trabaje con un administrador de productos de su organización para asegurarse de que dispone de los permisos adecuados para acceder a Analytics.

## ID de Analytics heredado

En ocasiones, un usuario de su organización recibe el siguiente mensaje de error cuando inicia sesión:

*Como medida de seguridad, esta cuenta se ha bloqueado debido a demasiados intentos fallidos de iniciar sesión.*

Si la eliminación de las cookies o la caché del navegador no resuelve el problema, trabaje con un administrador de Analytics de su organización para restablecer la contraseña del usuario.

>[!IMPORTANT]
>
>Los siguientes pasos para restablecer la contraseña de un usuario solo se aplican a los ID de Analytics heredados, no a Adobe ID. Si su organización utiliza Adobe ID, puede administrar las cuentas de usuario en [adminconsole.adobe.com](https://adminconsole.adobe.com).

1. Inicie sesión en Adobe Analytics con una cuenta que tenga derechos administrativos.
2. Vaya a **[!UICONTROL Administración]** > Administración **[!UICONTROL de usuarios]**.
3. Haga clic en la ficha **[!UICONTROL Usuarios]** y, a continuación, haga clic en **[!UICONTROL Editar]** al lado del usuario deseado.
4. Cambie la contraseña a cualquier valor y marque la casilla **[!UICONTROL Requerir que el usuario cambie la contraseña en el próximo inicio de sesión]**.
5. Informar al usuario de la nueva contraseña.

## Inicio de sesión único

Póngase en contacto con un administrador de su organización para resolver problemas de inicio de sesión único.

## Otros problemas de inicio de sesión

Si ninguno de los pasos anteriores funciona, determine la amplitud del problema de inicio de sesión:

* ¿Se produce el problema al usar un navegador diferente o es en todos los exploradores?
* ¿Ocurre el problema en un equipo diferente de la red o en varios equipos?
* Intente iniciar sesión con una red diferente, como una conexión de datos móvil, una biblioteca o una red doméstica. ¿Está el problema presente en las redes?

Si el problema está aislado en la red, trabaje con el equipo de TI de su organización para resolverlo. Si no se limita a una sola red, póngase en contacto con el Servicio de atención al cliente de Adobe.
