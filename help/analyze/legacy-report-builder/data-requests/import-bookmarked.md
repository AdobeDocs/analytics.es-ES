---
description: Todos los informes marcados y los informes del tablero ahora se enumeran como dimensiones en el paso 1 del Asistente para solicitudes y se pueden importar como solicitudes de Report Builder.
title: Importación de informes marcados e informes del panel de control
feature: Report Builder
role: User, Admin
exl-id: 19813950-2495-4a75-aacb-587b59bf2484
TQID: https://experienceleague.adobe.com/dnOYs7eOvv15K73EPrfRegz1vH9-B5p8xI8d86vPYe4
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
subfeature_v2:
  - id: ac8a38fa-dec3-4581-8f64-178fde9f64e8
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 241
ht-degree: 26%

---

# Importación de informes marcados e informes del panel de control

{{legacy-arb}}

Todos los informes marcados y los informes del tablero ahora se enumeran como dimensiones en el paso 1 del Asistente para solicitudes y se pueden importar como solicitudes de Report Builder.

Cuando selecciona un informe marcado, el Asistente para solicitudes rellena todas las dimensiones y métricas que definen este informe marcado. El intervalo de fechas, la granularidad y el segmento seleccionado también se actualizan en función del marcador seleccionado.

Así es como el Asistente para solicitudes: Paso 1 muestra un tablero y sus informes breves:

![Captura de pantalla que muestra el resaltado del Paso 1 de 2 del Asistente para solicitudes. Recupere sus paneles y recupere sus marcadores.](assets/import_dashboard_reportlet.png)

Al hacer clic en **[!UICONTROL Recuperar los paneles]** o **[!UICONTROL Recuperar los marcadores]**, los datos del panel o marcador existentes se recuperarán y pegarán en la hoja de cálculo.

>[!NOTE]
>
>Solo se importan los datos, de modo que si un marcador contiene un gráfico o si el informe breve del tablero consiste únicamente en un gráfico, solo se importarán los datos utilizados para rellenar el gráfico.

Una vez que haya creado una solicitud importando un informe breve del tablero (o un marcador), la solicitud se asociará a la dimensión principal del informe breve (o marcador). Como resultado, si edita la solicitud, la vista de árbol ya no selecciona el nodo de vista de árbol del informe breve del tablero (o nodo de marcador): selecciona su dimensión principal en su lugar.

