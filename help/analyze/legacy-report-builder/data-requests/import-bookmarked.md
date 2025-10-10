---
description: Todos los informes marcados y los informes del tablero ahora se enumeran como dimensiones en el paso 1 del Asistente para solicitudes y se pueden importar como solicitudes de Report Builder.
title: Importación de informes marcados e informes del panel de control
feature: Report Builder
role: User, Admin
exl-id: 19813950-2495-4a75-aacb-587b59bf2484
source-git-commit: ae6ffed05f5a33f032d0c7471ccdb1029154ddbd
workflow-type: tm+mt
source-wordcount: '241'
ht-degree: 65%

---

# Importación de informes marcados e informes del panel de control

{{legacy-arb}}

Todos los informes marcados y los informes del tablero ahora se enumeran como dimensiones en el paso 1 del Asistente para solicitudes y se pueden importar como solicitudes de Report Builder.

Cuando selecciona un informe marcado, el Asistente para solicitudes rellena todas las dimensiones y métricas que definen este informe marcado. El intervalo de fechas, la granularidad y el segmento seleccionado también se actualizan en función del marcador seleccionado.

Este es el modo en el que el Paso 1 del Asistente para solicitudes muestra un tablero y sus informes breves:

![Captura de pantalla que muestra el resaltado del Paso 1 de 2 del Asistente para solicitudes. Recupere sus paneles y recupere sus marcadores.](assets/import_dashboard_reportlet.png)

Al hacer clic en **[!UICONTROL Recuperar los tableros]** o **[!UICONTROL Recuperar los marcadores]**, se recuperan los datos de los tableros y/o los marcadores y se pegan en la hoja de cálculo.

>[!NOTE]
>
>Solo se importan los datos, de modo que si un marcador contiene un gráfico o si el informe breve del tablero consiste únicamente en un gráfico, solo se importarán los datos utilizados para rellenar el gráfico.

Una vez que haya creado una solicitud mediante la importación de un informe breve del panel (o un marcador), la solicitud quedará asociada a la dimensión primaria del informe breve (o marcador). Como resultado, si edita la solicitud, la vista de árbol ya no selecciona el nodo de vista de árbol del informe breve del tablero (o nodo de marcador): selecciona su dimensión principal en su lugar.

