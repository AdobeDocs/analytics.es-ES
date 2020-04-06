---
description: Información sobre las tres formas de iniciar sesión en Report Builder.
title: Inicio de sesión en Report Builder
topic: Report builder
uuid: 9a21b791-e323-46d2-b850-2d67babe964b
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Inicio de sesión en Report Builder

Información sobre las tres formas de iniciar sesión en Report Builder.

Currently, the following login options are available when you click **[!UICONTROL Sign In]** to Report Builder.

![](assets/login_screen.png)

* [Estándar ](/help/analyze/report-builder/setup/login.md#section_6D54B8ADAE7F416BB83F5082B3771CFA)
* [Inicio de sesión único ](/help/analyze/report-builder/setup/login.md#section_6970A5F926774976B85FFE576610E85F)
* [Experience Cloud y el inicio de sesión único ](/help/analyze/report-builder/setup/login.md#section_1FA230F35AB54021A874A7A28DE4C850)

## Estándar {#section_6D54B8ADAE7F416BB83F5082B3771CFA}

Use este inicio de sesión si desea iniciar sesión en Report Builder con sus credenciales de Adobe Analytics.

**Inicio de sesión de Report Builder: definiciones de campo**

| Campo | Definición |
|--- |--- |
| Empresa | Las credenciales de inicio de sesión de Compañía que se utilizan para Adobe Analytics. |
| Nombre de usuario | El nombre de usuario de inicio de sesión que utiliza para Adobe Analytics. Las tareas programadas para un usuario están vinculadas al nombre de usuario. Las tareas programadas se pueden ver desde cualquier equipo si se inicia sesión en Report Builder con las mismas credenciales de inicio de sesión. |
| Contraseña | La contraseña de Analytics. |
| Recordarme | La información de inicio de sesión se cifra y se almacena en un archivo de perfiles de usuario en el equipo donde se encuentra instalado Report Builder. Debido a que la información de inicio de sesión se guarda, cualquier usuario que utilice el mismo equipo que el creador del informe que abre una hoja de cálculo que contiene un informe, podrá actualizar y editar los datos. Si comparte el equipo con otros usuarios y desea que los datos de la hoja de cálculo sean privados, no active esta opción.  Para desactivar la configuración de inicio de sesión automático, haga clic en **[!UICONTROL Log in With Different Credentials]** la barra de herramientas y desactive **[!UICONTROL Remember Me]**. |
| Usar un servidor proxy | Active esta opción si accede a Internet a través de un servidor proxy y se requiere que proporcione un nombre de usuario y una contraseña proxy. |

## Inicio de sesión único {#section_6970A5F926774976B85FFE576610E85F}

Este inicio de sesión único (heredado) solo inicia sesión en Adobe Analytics, no en todo Experience Cloud.

También puede escribir un dominio y el sistema reconocerá el dominio y le redirigirá a la página de inicio de sesión de su compañía para iniciar sesión en Adobe Analytics.

## Experience Cloud {#section_1FA230F35AB54021A874A7A28DE4C850}

El inicio de sesión de Experience Cloud le permite utilizar su Enterprise ID (correo electrónico y contraseña) para iniciar sesión en Adobe Experience Cloud. Haga clic en **[!UICONTROL Sign In]** > **[!UICONTROL Sign in with an Enterprise ID]** para que se le redirija a la página de inicio de sesión único de su compañía. Para obtener más información sobre Enterprise ID, haga clic [aquí](https://helpx.adobe.com/es/enterprise/kb/enterprise-id-faq.html#whatis).

![](assets/adobe_id_login.png)

>[!NOTE] El inicio de sesión de Experience Cloud se basa en una sesión y un token, que caduca a los 30 días.

