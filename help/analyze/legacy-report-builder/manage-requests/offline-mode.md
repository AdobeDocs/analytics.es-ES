---
description: Aprenda a utilizar el modo sin conexión para devolver datos de marcador de posición.
title: Cómo habilitar el modo sin conexión
uuid: 4eb1f754-b6da-4896-a64f-b737563925b8
feature: Report Builder
role: User, Admin
exl-id: f18859e3-19e4-48af-963f-0bb4d1b46380
TQID: https://experienceleague.adobe.com/HKk--fSRTABpRb8Q9yOeySHyAVSR-W2Ktzldmp7UeJQ
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 200
ht-degree: 15%

---

# Modo sin conexión para crear y editar solicitudes

{{legacy-arb}}

El modo sin conexión devuelve datos de marcador de posición para acelerar el proceso de creación y edición de solicitudes.

Al crear o editar una nueva solicitud, se realizan llamadas a la API de informes para recuperar la respuesta. A veces, estas llamadas ralentizan el proceso de creación de solicitudes porque tiene que esperar a que se devuelvan los datos antes de pasar al siguiente paso. El modo sin conexión solo devuelve datos de marcador de posición y no se realizan API.

Para habilitar el modo sin conexión

1. Haga clic en **[!UICONTROL Opciones]** en el menú de Report Builder.

   ![Captura de pantalla de la pantalla Opciones con el código sin conexión seleccionado.](assets/offline_mode.png)

1. Marque la casilla que está junto a **[!UICONTROL Activar el modo sin conexión para crear y editar solicitudes]**.
1. En el campo **[!UICONTROL Mostrar datos de métrica como]**, escriba los datos de marcador de posición que desee que se devuelvan en la solicitud. Por ejemplo, introduzca &quot;1&quot;.
1. Haga clic en **[!UICONTROL Aceptar]**.
1. Cree y ejecute la solicitud en modo sin conexión mediante el Asistente para solicitudes. La siguiente captura de pantalla muestra un ejemplo de una solicitud con &quot;1&quot; como datos de marcador de posición.

   ![Captura de pantalla que muestra el ejemplo del modo sin conexión usando 1 como marcador de posición.](assets/offline_mode_example.png)

   >[!IMPORTANT]
   >
   >Asegúrese de desactivar el modo sin conexión antes de ejecutar sus solicitudes con datos reales.
