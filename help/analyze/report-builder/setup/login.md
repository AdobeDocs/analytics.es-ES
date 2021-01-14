---
description: Información sobre las tres formas de iniciar sesión en Report Builder.
title: Inicio de sesión en Report Builder
topic: Report builder
uuid: 9a21b791-e323-46d2-b850-2d67babe964b
translation-type: tm+mt
source-git-commit: 5b130de23d7826a266f34ed1830540c8c0865560
workflow-type: tm+mt
source-wordcount: '508'
ht-degree: 70%

---


# Inicio de sesión en Report Builder

>[!IMPORTANT]
>
>La versión 5.6.47 y posteriores de Report Builder solo admiten el inicio de sesión de Experience Cloud y no admiten inicios de sesión heredados como el inicio de sesión único de SiteCatalyst o el inicio de sesión estándar. Para el 30 de abril de 2021, todos los usuarios Report Builder deben actualizar el Añada del Report Builder a la versión 5.6.47 o posterior, que incluye una actualización crítica del proceso de inicio de sesión.

Para iniciar sesión en Report Builder, utilice su cuenta de inicio de sesión de Experience Cloud.

## Experience Cloud {#section_1FA230F35AB54021A874A7A28DE4C850}

El inicio de sesión de Experience Cloud permite utilizar su Enterprise ID (correo electrónico y contraseña) para iniciar sesión en Adobe Experience Cloud. Haga clic en **[!UICONTROL Iniciar sesión]** > **[!UICONTROL Iniciar sesión con un Enterprise ID]** para redirigirse a la página de inicio de sesión único de su empresa. Para obtener más información sobre Enterprise ID, haga clic [aquí](https://helpx.adobe.com/es/enterprise/kb/enterprise-id-faq.html#whatis).

![](assets/adobe_id_login.png)

>[!NOTE]
>
>El inicio de sesión de Experience Cloud se basa en una sesión y un token, que caduca a los 30 días.

## Iniciar sesión en Report Builder

Para iniciar sesión en Report Builder

1. En Excel, haga clic en **[!UICONTROL Complementos]**.
1. Haga clic en **[!UICONTROL Iniciar sesión]**. Otras operaciones de inicio de sesión son las siguientes:

   * Haga clic en **[!UICONTROL Crear]**.
   * [Seleccione una solicitud en el Administrador](/help/analyze/report-builder/manage-requests/r-arb-manage-requests.md) de solicitudes y haga clic en  **** Addor  **[!UICONTROL Manage]**.
   * Haga clic con el doble en una solicitud en Excel.

1. Rellene los campos de la página [!UICONTROL Inicio de sesión] y, a continuación, haga clic en **[!UICONTROL Aceptar]**.

## Tipos de inicio de sesión heredados

>[!IMPORTANT]
>
>Para el 30 de abril de 2021, los tipos de inicio de sesión heredados no funcionarán. Todos los usuarios Report Builder deben actualizar el Añada de Report Builder a la versión 5.6.47 o posterior, que incluye una actualización crítica del proceso de inicio de sesión. **La versión 5.6.47 y posteriores de Report Builder solo admiten el inicio de sesión de Experience Cloud y no admiten inicios de sesión heredados, como el inicio de sesión estándar o el inicio de sesión único de SiteCatalyst.**

<!-- ![](assets/login_screen.png) -->

* [Estándar](/help/analyze/report-builder/setup/login.md#section_6D54B8ADAE7F416BB83F5082B3771CFA)
* [Inicio de sesión único de SiteCatalyst](/help/analyze/report-builder/setup/login.md#section_6970A5F926774976B85FFE576610E85F)

## Estándar {#section_6D54B8ADAE7F416BB83F5082B3771CFA}

Use este inicio de sesión si desea iniciar sesión en Report Builder con sus credenciales de Adobe Analytics.

**Inicio de sesión de Report Builder: definiciones de campo**

| Campo | Definición |
|--- |--- |
| Empresa | Credenciales de inicio de sesión de la empresa que utilice para Adobe Analytics. |
| Nombre de usuario | Nombre de usuario del inicio de sesión que use para Adobe Analytics. Las tareas programadas para un usuario se vinculan al nombre de usuario. Las tareas programadas se pueden ver desde cualquier equipo si se inicia sesión en Report Builder con las mismas credenciales de inicio de sesión. |
| Contraseña | Su contraseña de Analytics. |
| Recordarme | La información de inicio de sesión se cifra y se almacena en un archivo de perfiles de usuario en el equipo donde se encuentra instalado Report Builder. Debido a que la información de inicio de sesión se guarda, cualquier usuario que utilice el mismo equipo que el creador del informe que abre una hoja de cálculo que contiene un informe, podrá actualizar y editar los datos. Si comparte el equipo con otros usuarios y desea que los datos de la hoja de cálculo sean privados, no active esta opción.  Para desactivar el inicio de sesión automático, haga clic en **[!UICONTROL Iniciar sesión con credenciales diferentes]** en la barra de herramientas y desactive **[!UICONTROL Recordarme]**. |
| Usar un servidor proxy | Active esta opción si accede a Internet mediante un servidor proxy y se solicita que introduzca una contraseña y nombre de usuario de proxy. |

## Inicio de sesión único {#section_6970A5F926774976B85FFE576610E85F}

Con este inicio de sesión único (heredado), solo se inicia sesión en Adobe Analytics, no en todo Experience Cloud.

También puede escribir un dominio que el sistema reconozca para que se le redirija a la página de inicio de sesión de su empresa y pueda iniciar sesión en Adobe Analytics.
