---
description: El modo sin conexión devuelve datos de marcador de posición para acelerar el proceso de creación y edición de solicitudes.
title: Modo sin conexión para crear y editar solicitudes
uuid: 4eb1f754-b6da-4896-a64f-b737563925b8
feature: Report Builder
role: User, Admin
exl-id: f18859e3-19e4-48af-963f-0bb4d1b46380
source-git-commit: 25eccb2b9fe3827e62b0ae98d9bebf7a97b239f5
workflow-type: ht
source-wordcount: '201'
ht-degree: 100%

---

# Modo sin conexión para crear y editar solicitudes

El modo sin conexión devuelve datos de marcador de posición para acelerar el proceso de creación y edición de solicitudes.

Cuando crea o edita una nueva solicitud, se realizan llamadas de la API de informes para recuperar la respuesta. Esto hace que el proceso de creación de solicitudes sea más lento ya que tiene que esperar para que se devuelvan los datos antes de pasar al siguiente paso. El modo sin conexión devuelve solo datos del marcador de posición, por lo que no se tiene que realizar ninguna llamada de la API.

Para activar el modo sin conexión:

1. Haga clic en **[!UICONTROL Opciones]** en el menú de Report Builder.

   ![Modo sin conexión](assets/offline_mode.png)

1. Active la casilla junto a **[!UICONTROL Activar el modo fuera de línea para la creación y edición de solicitudes]**.
1. En el campo **[!UICONTROL Mostrar los datos de métrica como]**, introduzca los datos del marcador de posición que desee que se devuelvan en su solicitud. Por ejemplo, introduzca &quot;1&quot;.
1. Haga clic en **[!UICONTROL Aceptar]**.
1. Ahora cree y ejecute su solicitud (en modo sin conexión) mediante el Asistente para solicitudes.
1. Su solicitud con &quot;1&quot; como datos de marcador de posición tendrán un aspecto como este:

   ![Ejemplo del modo sin conexión](assets/offline_mode_example.png)

   >[!IMPORTANT]
   >
   >Asegúrese de desactivar el modo sin conexión antes de ejecutar sus solicitudes con datos reales. Para ello, simplemente vuelva a **[!UICONTROL Opciones]** y quite la marca de activación.
