---
description: Todos los informes marcados y los informes del tablero ahora se enumeran como dimensiones en el paso 1 del Asistente para solicitudes y pueden importarse como solicitudes de Report Builder.
title: Importación de informes marcados e informes del panel
feature: Report Builder
role: User, Admin
exl-id: 19813950-2495-4a75-aacb-587b59bf2484
source-git-commit: 1ee50c6a2231795b2ad0015a79e09b7c1c74d850
workflow-type: tm+mt
source-wordcount: '341'
ht-degree: 100%

---

# Importación de informes marcados e informes del panel

Todos los informes marcados y los informes del tablero ahora se enumeran como dimensiones en el paso 1 del Asistente para solicitudes y pueden importarse como solicitudes de Report Builder.

Cuando selecciona un informe marcado, el Asistente para solicitudes rellena todas las dimensiones y métricas que definen este informe marcado. El intervalo de fechas, la granularidad y el segmento seleccionado también se actualizan según el marcador seleccionado..

Este es el modo en el que el Paso 1 del Asistente para solicitudes muestra un tablero y sus informes breves:

![](assets/import_dashboard_reportlet.png)

Al hacer clic en **[!UICONTROL Recuperar los tableros]** o **[!UICONTROL Recuperar los marcadores]**, se recuperan los datos de los tableros y/o los marcadores y se pegan en la hoja de cálculo.

>[!NOTE]
>
>En Report Builder, la lista de paneles y marcadores disponibles está limitada al usuario, pero también a los que se aplican al grupo de informes que ha seleccionado en el paso 1 del asistente. Por el contrario, en los informes y análisis de marketing obtiene acceso a todos los marcadores y paneles que le son accesibles, independientemente de qué grupos de informes utilicen dichos paneles y marcadores.

>[!NOTE]
>
>Solo se importan los datos, de modo que si un marcador contiene un gráfico o si el informe breve del tablero consiste únicamente en un gráfico, solo se importarán los datos utilizados para rellenar el gráfico.

Una vez que haya creado una solicitud mediante la importación de un informe breve del panel (o un marcador), la solicitud quedará asociada a la dimensión primaria del informe breve (o marcador). Como resultado, si edita la solicitud, la vista de árbol ya no selecciona el nodo de vista de árbol del informe breve del tablero (o nodo de marcador): selecciona su dimensión principal en su lugar.

El bookmarklet importado configurará adecuadamente el grupo de informes, el segmento seleccionado, la dimensión y las métricas seleccionadas con los mismos parámetros expuestos en el marcador Reports &amp; Analytics.

>[!IMPORTANT]
>
>El intervalo de fechas se establecerá en el mismo intervalo de fechas, pero como un intervalo de fechas estático, incluso si este intervalo de fechas era un intervalo de fechas móvil en el marcador de Reports &amp; Analytics.
