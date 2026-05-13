---
description: Obtenga información sobre cómo copiar solicitudes de referencia.
title: Cómo copiar solicitudes de referencia
feature: Report Builder
role: User, Admin
exl-id: 3cd77325-7461-4345-a672-64c03ea1ae5b
TQID: https://experienceleague.adobe.com/A-ef3rd0b7WMBRqBgmxFWpa35x8R7qYF1dMkF5gx5Ec
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
source-wordcount: 533
ht-degree: 23%

---

# Copiar solicitudes de referencia

{{legacy-arb}}

Una solicitud de referencia utiliza los valores de las celdas como entrada para parámetros como, por ejemplo, un filtro de datos o un filtro relacional.

Para propagar o copiar y pegar solicitudes de referencia en la hoja de cálculo:

* Debe crear al menos una solicitud válida en la hoja de cálculo.

* Los datos producidos por la solicitud deben contener una celda cuyo valor dependa de una solicitud en otra celda (mediante un desglose o filtro coincidente) o de un filtro que tome datos introducidos en una celda.

También puede crear solicitudes que hagan referencia a filtros de entrada desde solicitudes de diferentes hojas de cálculo, pero no desde libros diferentes. Por ejemplo, una solicitud de la Hoja 2 puede utilizar un grupo de informes de una celda determinada de la Hoja 1 y un intervalo de fechas de una celda de una solicitud de la Hoja 2. El nuevo resultado se puede colocar en una hoja o en una hoja nueva dentro del mismo libro. Al pegar una solicitud relativa, si un filtro de entrada reside en una hoja de cálculo distinta de la hoja en la que se encuentra la salida de la solicitud copiada, el filtro se pega como un filtro absoluto.

>[!NOTE]
>
>No se puede generar una única solicitud en varias hojas de cálculo. Además, el sistema no puede pegar algunas de las solicitudes copiadas en libros nuevos porque las solicitudes contienen filtros de entrada de otras hojas de cálculo. Los filtros de entrada incluyen grupos de informes de celdas, intervalos de fechas de celdas, filtros de celdas y otros parámetros relacionados.

**Para copiar solicitudes de referencia**

1. Seleccione las celdas que contengan las solicitudes que desee copiar, incluyendo la celda de entrada o las que hacen referencia a la celda.
1. Haga clic con el botón derecho en las celdas resaltadas y seleccione **[!UICONTROL Copiar solicitudes]** en el menú contextual.

   Tras seleccionar el área donde están ubicadas las solicitudes y las celdas de entrada, el sistema resalta las celdas que tienen estos elementos.
1. Seleccione una celda o un rango de celdas contiguas para rellenarlas con las solicitudes pegadas.

   Asegúrese de que la celda o el rango de celdas seleccionado no contenga otros datos o solicitudes.
1. Haga clic con el botón derecho en la celda o en la celda superior izquierda del rango de celdas y seleccione **[!UICONTROL Pegar solicitudes]**.

   Al pegar solicitudes que incluyen una celda de entrada, las opciones en [!UICONTROL Pegar solicitudes] incluyen:

   **Utilizar celda de entrada absoluta:** Pega una copia de las solicitudes y el formato asociados con las celdas seleccionadas en el área de pegado resaltada. La celda de entrada (la celda a la que se hace referencia en una de las solicitudes originales) no se pega. En su lugar, la celda de entrada permanece en la misma posición que antes.

   **Utilizar celda de entrada relativa:** Pega una copia de las solicitudes y el formato asociados con las celdas seleccionadas en el área de pegado resaltada, incluida una copia de la celda de entrada. La relación espacial de las solicitudes con la celda de entrada es la misma que en las solicitudes originales. Sin embargo, aunque las celdas recién pegadas ahora tienen una copia de las solicitudes, inicialmente no tienen contenido. Esto se debe a que, cuando se vuelve a crear la celda de entrada en la operación de pegado, no se asocia ningún dato a la celda de entrada. Para mostrar los datos de las solicitudes recién pegadas, debe introducir un valor en la celda de entrada y, a continuación, actualizar las solicitudes.
