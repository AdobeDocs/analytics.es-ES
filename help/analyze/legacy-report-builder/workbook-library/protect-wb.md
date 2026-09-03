---
description: Obtenga información sobre cómo proteger todas las solicitudes de un libro contra las solicitudes de adición y edición bloqueando el libro.
title: Bloquear y desbloquear libros
uuid: ef5c276c-5f74-4741-b6fa-4c79eda29f62
feature: Report Builder
role: User, Admin
exl-id: b5a83532-9fa7-4f1f-b744-e5d74781fffb
TQID: https://experienceleague.adobe.com/0UyYFqVn5qAIimI3obHdsBbTsRirLl6llZf8Y3endLo
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 475
ht-degree: 22%

---

# Bloquear y desbloquear libros

{{legacy-arb}}

Puede proteger todas las solicitudes de un libro contra las solicitudes de adición y edición bloqueando el libro. Esto permite la edición de libros sin conexión al pausar todas las solicitudes de informe para una edición más eficiente.

Como analista, bloquear un libro le permite proteger las solicitudes del libro contra la manipulación por parte de otros usuarios de su organización. Al mismo tiempo, esos usuarios pueden seguir actualizando las solicitudes del libro.

Para proteger un libro contra la edición, haga clic en **[!UICONTROL Bloqueado]** en la barra de herramientas de Report Builder ( ![](assets/locked_icon.png)).

Para desproteger un libro, haga clic en **[!UICONTROL Desbloqueado]** ( ![](assets/unlocked_icon.png)).

Puede desbloquear un libro bloqueado si cuenta con uno de los siguientes permisos:

* Usted es administrador, o
* Usted es la persona que bloqueó inicialmente el libro. En este caso, no tiene que ser administrador.

>[!NOTE]
>
>No puede agregar una solicitud a un libro protegido a menos que tenga los permisos para desbloquear el libro.

Cuando un libro está bloqueado contra la edición de solicitudes,

* Los usuarios no pueden crear ni agregar solicitudes.
* Los usuarios no pueden editar solicitudes a través del Asistente para solicitudes.
* Los usuarios no pueden editar solicitudes mediante las funciones Editar varias solicitudes.
* Los usuarios no pueden cortar, copiar ni pegar solicitudes. Sin embargo, los usuarios aún pueden utilizar el menú contextual nativo de Excel Cortar/Copiar/Pegar para cortar/copiar/pegar el contenido de las solicitudes.
* Los usuarios pueden actualizar las solicitudes, ya sea de forma individual o como parte de un grupo.
* Si la solicitud utiliza valores de entrada de celdas (intervalo de fechas, segmento, filtros), los usuarios pueden cambiar estos valores en las celdas y, por lo tanto, editar indirectamente las solicitudes actualizándolas.

Si intenta editar un libro protegido a través del menú contextual, o **[!UICONTROL Administrador de solicitudes]** o **[!UICONTROL Editar varias solicitudes]**, puede que tenga o no permiso para hacerlo:

* Si no tiene permisos para desbloquear una solicitud, verá un mensaje que indica que no tiene derechos para desbloquear y editar el libro.

  ![Captura de pantalla que muestra el mensaje de error cuando no tiene permisos para desbloquear una solicitud.](assets/locked_workbook_error.png)

## Flujo de trabajo {#section_260D05FF632B41DB97DB43E2ADBE2E75}

Supongamos que el libro A tiene una solicitud que está bloqueada y que la creó el usuario A.

**Ejemplo 1: usuario administrador (o usuario A)**

1. El usuario inicia sesión en Report Builder y abre el libro
1. El libro A está bloqueado actualmente, por lo que el botón “Crear solicitud” está desactivado en la barra de herramientas, junto con todos los demás botones cuyas funciones están desactivadas por el bloqueo.
1. Si el usuario intenta utilizar uno de los botones desactivados, aparece un mensaje que indica que el libro está bloqueado actualmente.
1. El usuario puede desbloquear el libro, lo que habilita la funcionalidad de edición completa.
1. Después del desbloqueo, el libro permanece desbloqueado hasta que se vuelva a bloquear explícitamente.

**Ejemplo 2: usuario no administrador (usuario B)**

1. El usuario inicia sesión en Report Builder y abre el libro
1. El usuario no puede agregar ni editar la solicitud.
1. El usuario no puede desbloquear el libro.
