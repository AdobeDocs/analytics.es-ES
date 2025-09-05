---
description: Administre a los usuarios de Analytics y sus recursos en Adobe Admin Console.
title: Administración de usuarios y recursos de Analytics
feature: Admin Tools
exl-id: 849a8279-4850-4458-bdd2-85052a17ee21
role: Admin
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '407'
ht-degree: 4%

---

# Administrar cuentas de usuario, recursos y caducidades heredados

Puede administrar cuentas de usuario heredadas, su estado de migración, los datos de caducidad, la transferencia de recursos a otros usuarios y mucho más mediante **[!UICONTROL Administración] > [!UICONTROL Todos los administradores] > [!UICONTROL Usuarios y administradores de Analytics]**.

La pantalla Usuarios muestra una lista de los usuarios actuales de Adobe Analytics, con las siguientes columnas:

| Columna | Descripción |
|---|---|
| [!UICONTROL ID de usuario] | El ID de usuario que utiliza el usuario para iniciar sesión en Adobe Analytics. |
| [!UICONTROL Nombre] | El nombre del usuario. |
| [!UICONTROL Estado de la migración] | Estado de la migración de una cuenta de usuario heredada a una Enterprise ID o Adobe ID.  El estado puede ser No iniciado, En cola o Migrado. |
| [!UICONTROL Correo electrónico] | El correo electrónico del usuario. |
| [!UICONTROL Inicio de sesión heredado] | El estado del inicio de sesión heredado, que puede ser Enabled o Disabled. |
| [!UICONTROL Fecha de creación] | Marca de tiempo del momento en el que se creó la cuenta de usuario en Adobe Analytics. |
| [!UICONTROL Último acceso de Analytics] | Marca de tiempo del último acceso de la cuenta de usuario a Adobe Analytics, |
| [!UICONTROL Caducidad] | Fecha de caducidad de la cuenta de usuario o Ninguno si la cuenta de usuario no caduca. |

![Usuarios](assets/users.png)

- Para buscar un usuario específico, usa el campo ![Buscar](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Search_18_N.svg) *Buscar por título*.
- Para filtrar la lista según el estado de migración, seleccione ![Chevron](https://spectrum.adobe.com/static/icons/ui_18/ChevronSize100.svg) **[!UICONTROL Estado de migración]**.
- Para filtrar la lista según el estado de inicio de sesión heredado, seleccione ![Chevron](https://spectrum.adobe.com/static/icons/ui_18/ChevronSize100.svg) **[!UICONTROL Inicio de sesión heredado]**.
- Para cambiar la visualización de las columnas, seleccione ![Configuración de columna](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ColumnSettings_18_N.svg) y seleccione las columnas en la ventana emergente.

Puede aplicar varias acciones al seleccionar uno o varios usuarios de la lista:

| Acción | Descripción |
|---|---|
| ![Migrar](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Briefcase_18_N.svg) **[!UICONTROL Migrar]** | Puede migrar uno o varios usuarios a Enterprise ID o Adobe ID. |
| ![Calendario bloqueado](https://spectrum.adobe.com/static/icons/workflow_18/Smock_CalendarLocked_18_N.svg) **[!UICONTROL Establecer caducidad]** | Puede establecer una fecha de caducidad para el uso del inicio de sesión heredado de Adobe Analytics para los usuarios seleccionados.  Seleccione la fecha para utilizar una ventana emergente de calendario para especificar la fecha. Seleccione **[!UICONTROL Listo]** para confirmar la caducidad. |
| ![Transferir recursos](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Switch_18_N.svg) **[!UICONTROL Transferir recursos]** | Esta acción solo está disponible al seleccionar un usuario. Si el usuario tiene recursos que se pueden transferir, puede seleccionar los elementos de la cuenta (como marcadores, tableros, etc.). Seleccione **[!UICONTROL Transferir]** para completar la transferencia.<br/>![Transfiere recursos](assets/transfer-assets.png) |
| ![Eliminar cuentas](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg) **[!UICONTROL Eliminar cuentas]** | Se muestra un cuadro de diálogo para confirmar la eliminación de las cuentas seleccionadas. Seleccione **[!UICONTROL Aceptar]** para eliminar las cuentas. Seleccione **[!UICONTROL Cancelar]** para cancelar. |
| ![Exportar a CSV](https://spectrum.adobe.com/static/icons/workflow_18/Smock_FileCSV_18_N.svg) **[!UICONTROL Exportar a CSV]** | Esta acción descarga inmediatamente un archivo que contiene una lista de valores separados por comas de los usuarios seleccionados con sus detalles (nombre, estado de migración, correo electrónico, etc.). |

