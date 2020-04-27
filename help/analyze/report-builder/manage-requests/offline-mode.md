---
description: El modo sin conexión devuelve datos de marcador de posición para acelerar el proceso de creación y edición de solicitudes.
title: Modo sin conexión para crear y editar solicitudes
topic: Report builder
uuid: 4eb1f754-b6da-4896-a64f-b737563925b8
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Modo sin conexión para crear y editar solicitudes

El modo sin conexión devuelve datos de marcador de posición para acelerar el proceso de creación y edición de solicitudes.

Cuando crea o edita una nueva solicitud, se realizan llamadas de la API de informes para recuperar la respuesta. Esto hace que el proceso de creación de solicitudes sea más lento ya que tiene que esperar para que se devuelvan los datos antes de pasar al siguiente paso. El modo sin conexión devuelve solo datos del marcador de posición, por lo que no se tiene que realizar ninguna llamada de la API.

Para activar el modo sin conexión:

1. Click **[!UICONTROL Options]** in the Report Builder menu.

   ![](assets/offline_mode.png)

1. Marque la casilla de verificación situada junto a **[!UICONTROL Turn on offline mode for creating and editing requests]**.
1. In the **[!UICONTROL Display Metric Data as]** field, enter the placeholder data that you want returned in your request. Por ejemplo, introduzca &quot;1&quot;.
1. Haga clic en **[!UICONTROL OK]**.
1. Ahora cree y ejecute su solicitud (en modo sin conexión) mediante el Asistente para solicitudes.
1. Su solicitud con &quot;1&quot; como datos de marcador de posición tendrán un aspecto como este:

   ![](assets/offline_mode_example.png)

   >[!IMPORTANT]
   >
   >Asegúrese de desactivar el modo sin conexión antes de ejecutar sus solicitudes con datos reales. To do so, just go back to **[!UICONTROL Options]** and remove the checkmark.

