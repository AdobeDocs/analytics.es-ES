---
description: Administre a los usuarios de Analytics y sus recursos en Adobe Admin Console.
title: Administración de usuarios y recursos de Analytics
feature: Admin Tools
exl-id: 849a8279-4850-4458-bdd2-85052a17ee21
role: Admin
TQID: 'https://experienceleague.adobe.com/d8CK9Vf-eaEU6P9386J1eO-JpD5u4l3VoqRcMwvXcW0'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
    internal-label: Dashboards
  - id: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
    internal-label: Admin Tools
subfeature_v2:
  - id: d124af73-4061-4b84-9063-ae2b60f2c1f3
    internal-label: User management
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: 8badbfc74bdc95a8ab673d4f00fe13e0829e64bb
workflow-type: tm+mt
source-wordcount: '399'
ht-degree: 5%
---
# Administrar cuentas de usuario, recursos y caducidades heredados

Puede administrar cuentas de usuario heredadas, su estado de migración, los datos de caducidad, la transferencia de recursos a otros usuarios y mucho más mediante **[!UICONTROL Administración] > [!UICONTROL Todos los administradores] > [!UICONTROL Usuarios y administradores de Analytics]**.

La pantalla Usuarios muestra una lista de los usuarios actuales de Adobe Analytics, con las siguientes columnas:

| Columna | Descripción |
|---|---|
| [!UICONTROL ID de usuario] | El ID de usuario que utiliza el usuario para iniciar sesión en Adobe Analytics. |
| [!UICONTROL Nombre] | El nombre del usuario. |
| [!UICONTROL Estado de la migración] | Estado de la migración de una cuenta de usuario heredada a una Enterprise ID o Adobe ID.  El estado puede ser No iniciado, En cola o Migrado. |
| [!UICONTROL Correo electrónico] | Dirección de correo electrónico del usuario. |
| [!UICONTROL Inicio de sesión heredado] | El estado del inicio de sesión heredado, que puede ser Enabled o Disabled. |
| [!UICONTROL Fecha de creación] | Marca de tiempo del momento en el que se creó la cuenta de usuario en Adobe Analytics. |
| [!UICONTROL Último acceso de Analytics] | Marca de tiempo del último acceso de la cuenta de usuario a Adobe Analytics, |
| [!UICONTROL Caducidad] | Fecha de caducidad de la cuenta de usuario o Ninguno si la cuenta de usuario no caduca. |

![Usuarios](assets/users.png)

- Para buscar un usuario específico, usa el campo ![Buscar](/help/assets/icons/Search.svg) *Buscar por título*.
- Para filtrar la lista según el estado de migración, seleccione ![Chevron](/help/assets/icons/ChevronDown.svg) **[!UICONTROL Estado de migración]**.
- Para filtrar la lista según el estado de inicio de sesión heredado, seleccione ![Chevron](/help/assets/icons/ChevronDown.svg) **[!UICONTROL Inicio de sesión heredado]**.
- Para cambiar la visualización de las columnas, seleccione ![Configuración de columna](/help/assets/icons/ColumnSetting.svg) y seleccione las columnas en la ventana emergente.

Puede aplicar varias acciones al seleccionar uno o varios usuarios de la lista:

| Acción | Descripción |
|---|---|
| ![Migrar](/help/assets/icons/Briefcase.svg) **[!UICONTROL Migrar]** | Puede migrar uno o varios usuarios a Enterprise ID o Adobe ID. |
| ![Calendario bloqueado](/help/assets/icons/CalendarLocked.svg) **[!UICONTROL Establecer caducidad]** | Puede establecer una fecha de caducidad para el uso del inicio de sesión heredado de Adobe Analytics para los usuarios seleccionados.  Seleccione la fecha para utilizar una ventana emergente de calendario para especificar la fecha. Seleccione **[!UICONTROL Listo]** para confirmar la caducidad. |
| ![Transferir recursos](/help/assets/icons/Switch.svg) **[!UICONTROL Transferir recursos]** | Esta acción solo está disponible al seleccionar un usuario. Si el usuario tiene recursos que se pueden transferir, puede seleccionar los elementos de la cuenta (como marcadores, tableros, etc.). Seleccione **[!UICONTROL Transferir]** para completar la transferencia.<br/>![Transfiere recursos](assets/transfer-assets.png) |
| ![Eliminar cuentas](/help/assets/icons/Delete.svg) **[!UICONTROL Eliminar cuentas]** | Se muestra un cuadro de diálogo para confirmar la eliminación de las cuentas seleccionadas. Seleccione **[!UICONTROL Aceptar]** para eliminar las cuentas. Seleccione **[!UICONTROL Cancelar]** para cancelar. |
| ![Exportar a CSV](/help/assets/icons/FileCSV.svg) **[!UICONTROL Exportar a CSV]** | Esta acción descarga inmediatamente un archivo que contiene una lista de valores separados por comas de los usuarios seleccionados con sus detalles (nombre, estado de migración, correo electrónico, etc.). |

