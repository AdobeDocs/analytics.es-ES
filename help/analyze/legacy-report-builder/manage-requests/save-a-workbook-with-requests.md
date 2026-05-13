---
description: Obtenga información sobre cómo guardar informes con solicitudes incrustadas.
title: Guardar un libro con solicitudes
uuid: 31611031-0982-4124-9fc7-7888124aa603
feature: Report Builder
role: User, Admin
exl-id: 192ac2f6-cfb8-447b-8fc1-19ad786ef924
TQID: https://experienceleague.adobe.com/0UMDDWbeilsUp-yB-tzMVcWkGfUXtf4lh2ciaAg4AEk
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
subfeature_v2:
  - id: ac8a38fa-dec3-4581-8f64-178fde9f64e8
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 276
ht-degree: 31%

---

# Guardar un libro con solicitudes

{{legacy-arb}}

Cuando crea informes con solicitudes incrustadas, puede guardarlos con **Archivo** > **Guardar** o **Archivo** > **Guardar como** en Excel. Report Builder detecta si el informe contiene solicitudes. Cuando seleccione una de las opciones de guardado, complete el formulario **Guardar libro como**.

* Como práctica recomendada para cualquier trabajo extenso con aplicaciones de Windows, Adobe recomienda guardar las solicitudes en la hoja de cálculo con frecuencia y regularidad para evitar una pérdida inesperada de solicitudes en la hoja de cálculo.
* Al asignar un nombre al libro, considere la posibilidad de utilizar un número de versión en el nombre de archivo para poder conservar un historial de trabajo. Por ejemplo, asigne el siguiente nombre al primer libro [!DNL web_forecast_01_01.xlsx].
* Si ya guardó el informe, el formulario [!UICONTROL Guardar plantilla] no se mostrará al guardar el informe por segunda vez. Si el informe no contiene solicitudes, no se muestra este cuadro de diálogo. En su lugar, se muestra el formulario estándar de Excel [!UICONTROL Guardar como].

## Nombres de archivo y ubicación {#section_2406629E9B644CE08430826948977D5D}

El formulario [!UICONTROL Guardar plantilla] tiene algunas de las mismas funciones que el cuadro de diálogo estándar de Excel [!UICONTROL Archivo] > [!UICONTROL Guardar como]; por ejemplo, los dos incluyen un cuadro de texto para indicar el nombre de archivo del informe de la hoja de cálculo utilizando la extensión de archivo convencional [!DNL .xls]..

Cualquier nombre de archivo que utilice debe contener 255 caracteres o menos. Además, el nombre de archivo no puede contener los siguientes caracteres:

\ ? | > &lt; : / &#42; &#39; &quot;

Por último, no puede utilizar caracteres Unicode que no sean el conjunto de caracteres ASCII extendidos.

Al guardar un archivo en una ubicación de las unidades de red o locales, es posible indicar la ruta completa en el cuadro de texto, o bien hacer clic en el botón Examinar ![browse_button.gif](assets/browse_button.gif) junto al cuadro de texto [!UICONTROL Guardar como].
