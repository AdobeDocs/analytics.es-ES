---
description: Puede proteger todas las solicitudes de un libro contra la adición y edición de solicitudes bloqueando el libro. Esto permite la edición de libros sin conexión al pausar todas las solicitudes de informe para una edición más eficiente.
title: Bloquear/desbloquear libros
topic: Report builder
uuid: ef5c276c-5f74-4741-b6fa-4c79eda29f62
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Bloquear/desbloquear libros

Puede proteger todas las solicitudes de un libro contra la adición y edición de solicitudes bloqueando el libro. Esto permite la edición de libros sin conexión al pausar todas las solicitudes de informe para una edición más eficiente.

Como analista, el bloqueo de un libro le permite proteger las solicitudes de libro contra la manipulación por parte de otros usuarios dentro de la organización. Al mismo tiempo, esos usuarios pueden seguir actualizando las solicitudes del libro.

To protect a workbook against editing, click **[!UICONTROL Locked]** on the Report Builder toolbar ( ![](assets/locked_icon.png)

).

To unprotect a workbook, click **[!UICONTROL Unlocked]** ( ![](assets/unlocked_icon.png)

).

Puede desbloquear un libro bloqueado si cuenta con uno de los siguientes permisos:

* Es administrador o
* Es la persona que bloqueó el libro por primera vez. En este caso, no es necesario que sea administrador.

>[!NOTE] No puede añadir una solicitud a un libro protegido a menos que tenga los permisos para desbloquear el libro.

Cuando un libro está bloqueado contra la edición de solicitudes,

* Los usuarios no pueden crear ni agregar solicitudes.
* Los usuarios no pueden editar solicitudes a través del Asistente para solicitudes.
* Los usuarios no pueden editar solicitudes a través de las funciones Editar varias solicitudes.
* Los usuarios no pueden cortar, copiar ni pegar solicitudes. Sin embargo, los usuarios pueden seguir utilizando el menú contextual nativo de Excel Cortar/Copiar/Pegar para cortar/copiar/pegar el contenido de las solicitudes.
* Los usuarios pueden actualizar las solicitudes de forma individual o como parte de un grupo.
* Si la solicitud utiliza valores de entrada de celdas (intervalo de fechas, segmento, filtros), los usuarios pueden cambiar estos valores en las celdas y, por tanto, editar indirectamente las solicitudes actualizándolas.

Si intenta editar un libro protegido (a través del menú contextual o **[!UICONTROL Request Manager]**, o **[!UICONTROL Edit Multiple Requests]**), puede que se le permita o no:

* Si no tiene permisos para desbloquear las solicitudes, aparecerá este mensaje:

   ![](assets/locked_workbook_error.png)

* Si dispone de los permisos necesarios, no se mostrará ningún mensaje y podrá editar la solicitud.

## Flujo de trabajo {#section_260D05FF632B41DB97DB43E2ADBE2E75}

Supongamos que el libro A tiene una solicitud que está bloqueada y que la creó el usuario A.

**Ejemplo 1: usuario administrador (o usuario A)**

1. El usuario inicia sesión en Report Builder y abre el libro
1. El libro A está bloqueado actualmente, por lo que el botón “Crear solicitud” está desactivado en la barra de herramientas, junto con todos los demás botones cuyas funciones están desactivadas por el bloqueo.
1. Si el usuario intenta utilizar uno de los botones desactivados, aparece un mensaje que indica que el libro está bloqueado actualmente.
1. El usuario puede desbloquear el libro, lo que permite la funcionalidad de edición completa.
1. Después del desbloqueo, el libro permanece desbloqueado hasta que se vuelve a bloquear explícitamente.

**Ejemplo 2: usuario no administrador (usuario B)**

1. El usuario inicia sesión en Report Builder y abre el libro
1. El usuario no puede agregar o editar la solicitud.
1. El usuario no puede desbloquear el libro.

