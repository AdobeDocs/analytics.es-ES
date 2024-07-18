---
description: Obtenga información sobre cómo guardar informes con solicitudes incrustadas.
title: Guardar un libro con solicitudes
uuid: 31611031-0982-4124-9fc7-7888124aa603
feature: Report Builder
role: User, Admin
exl-id: 192ac2f6-cfb8-447b-8fc1-19ad786ef924
source-git-commit: 66b7de0b008364e47253d319785c204ca479ab26
workflow-type: tm+mt
source-wordcount: '276'
ht-degree: 78%

---

# Guardar un libro con solicitudes

Cuando crea informes con solicitudes incrustadas, puede guardarlos con **Archivo** > **Guardar** o **Archivo** > **Guardar como** en Excel. El Report Builder detecta si el informe contiene solicitudes. Cuando seleccione una de las opciones de guardado, complete el formulario **Guardar libro como**.

* En cualquier trabajo extenso realizado con aplicaciones de Windows, Adobe recomienda guardar las solicitudes en la hoja de cálculo de forma regular y periódica para evitar perder inesperadamente las solicitudes de la hoja de datos.
* En el nombre del libro puede incluir un número de versión para así mantener un historial de trabajo. Por ejemplo, asigne el siguiente nombre al primer libro [!DNL web_forecast_01_01.xlsx].
* Si ya ha guardado el informe, el formulario [!UICONTROL Guardar plantilla] no se muestra al guardar el informe por segunda vez. Si el informe no contiene solicitudes, este cuadro de diálogo no se mostrará. En su lugar aparecerá el formulario de Excel [!UICONTROL Guardar como].

## Nombres de archivo y ubicación {#section_2406629E9B644CE08430826948977D5D}

El formulario [!UICONTROL Guardar plantilla] tiene algunas de las mismas funciones que el cuadro de diálogo estándar de Excel [!UICONTROL Archivo] > [!UICONTROL Guardar como]; por ejemplo, los dos incluyen un cuadro de texto para indicar el nombre de archivo del informe de la hoja de cálculo utilizando la extensión de archivo convencional [!DNL .xls]..

Cualquier nombre de archivo utilizado debe incluir 255 caracteres o menos. Asimismo, el nombre del archivo no puede contener los siguientes caracteres:

\ ? | > &lt; : / &#42; &#39; &quot;

Finalmente, no se pueden utilizar caracteres Unicode que no estén incluidos en el conjunto de caracteres extendidos ASCII.

Al guardar un archivo en una ubicación de las unidades de red o locales, es posible indicar la ruta completa en el cuadro de texto, o bien hacer clic en el botón Examinar ![browse_button.gif](assets/browse_button.gif) junto al cuadro de texto [!UICONTROL Guardar como].
