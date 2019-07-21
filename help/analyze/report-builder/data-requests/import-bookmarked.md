---
description: Todos los informes marcados y los informes del tablero ahora se enumeran como dimensiones en el paso 1 del Asistente para solicitudes y pueden importarse como solicitudes del Creador de informes.
seo-description: Todos los informes marcados y los informes del tablero ahora se enumeran como dimensiones en el paso 1 del Asistente para solicitudes y pueden importarse como solicitudes del Creador de informes.
seo-title: Importar informes marcados y informes breves de tablero
solution: Analytics
title: Importar informes marcados y informes breves de tablero
topic: Creador de informes
uuid: 0 fdbdb 2 e -5 db 7-4 f 64-b 571-23482 ba 3606 d
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Importar informes marcados y informes breves de tablero

Todos los informes marcados y los informes del tablero ahora se enumeran como dimensiones en el paso 1 del Asistente para solicitudes y pueden importarse como solicitudes del Creador de informes.

Cuando selecciona un informe marcado, el Asistente para solicitudes rellena todas las dimensiones y métricas que definen este informe marcado. El intervalo de fechas, la granularidad y el segmento seleccionado también se actualizan según el marcador seleccionado..

Este es el modo en el que el Paso 1 del Asistente para solicitudes muestra un tablero y sus informes breves:

![](assets/import_dashboard_reportlet.png)

When you click **[!UICONTROL Retrieve your Dashboards]** or **[!UICONTROL Retrieve your Bookmarks]**, your existing dashboard and/or bookmark data is retrieved and pasted in the worksheet.

>[!NOTE]
>
>En el Creador de informes, la lista de tableros y marcadores disponibles está limitada al usuario pero también a los que se aplican al grupo de informes seleccionado en el paso 1 del asistente. Por el contrario, en los informes y análisis de marketing obtiene acceso a todos los marcadores y tableros que le son accesibles, independientemente de qué grupos de informes utilicen dichos tableros y marcadores.

>[!NOTE]
>
>Solo se importan los datos, por lo que si el marcador contiene un gráfico, o si el informe breve del tablero consiste únicamente en un gráfico, solo se importarán los datos utilizados para rellenar el gráfico.

Una vez que haya creado una solicitud mediante la importación de un informe breve del panel (o un marcador), la solicitud quedará asociada a la dimensión primaria del informe breve (o marcador). Como resultado, si edita la solicitud, la vista de árbol ya no selecciona el nodo de vista de árbol del informe breve del tablero (o nodo de marcador): selecciona su dimensión principal en su lugar.

El bookmarklet importado configurará adecuadamente el grupo de informes, el segmento seleccionado, la dimensión y las métricas seleccionadas con los mismos parámetros expuestos en el marcador Informes y análisis. 

>[!IMPORTANT]
>
>El intervalo de fechas se establecerá en el mismo intervalo de fechas, pero como un intervalo de fechas estático, incluso si este intervalo de fechas era un intervalo de fechas móvil en el marcador de Informes y análisis.

