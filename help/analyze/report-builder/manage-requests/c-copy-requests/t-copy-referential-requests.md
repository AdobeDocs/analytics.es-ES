---
description: Una solicitud de referencia utiliza los valores de las celdas como entrada para parámetros como, por ejemplo, un filtro de datos o un filtro relacional.
title: Copiar solicitudes de referencia
topic: Report builder
uuid: b6f64630-868f-455b-8682-471ff9fc596e
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Copiar solicitudes de referencia

Una solicitud de referencia utiliza los valores de las celdas como entrada para parámetros como, por ejemplo, un filtro de datos o un filtro relacional.

Para propagar o copiar y pegar solicitudes de referencia en la hoja de cálculo, debe haber creado al menos una solicitud válida en la hoja de cálculo. Además, los datos generados por la solicitud deben contener una celda cuyo valor dependa de una solicitud de otra celda (mediante un filtro de desglose o de coincidencia) o de un filtro que tome la entrada de datos introducidos en una celda.

También puede crear solicitudes que hagan referencia a filtros de entrada de solicitudes de hojas de cálculo diferentes, pero no a libros diferentes. Por ejemplo, una solicitud de la Hoja 2 puede utilizar un grupo de informes de una celda determinada de la Hoja 1 y un intervalo de fechas de una celda de una solicitud de la Hoja 2. El nuevo resultado se puede colocar en una hoja o en una nueva hoja dentro del mismo libro. Al pegar una solicitud relativa, si un filtro de entrada reside en una hoja de cálculo diferente de la hoja de cálculo en la que se encuentra el resultado de la solicitud copiada, el filtro se pega como filtro absoluto.

>[!NOTE] No se puede generar la misma solicitud en varias hojas de cálculo. Además, el sistema no puede pegar algunas de las solicitudes copiadas en nuevos libros porque las solicitudes contienen filtros de entrada de otras hojas de cálculo. Los filtros de entrada incluyen grupos de informes de celdas, intervalos de fechas de celdas, filtros de celdas y otros parámetros relacionados.

**Para copiar solicitudes de referencia**

1. Seleccione las celdas que contengan las solicitudes que desee copiar, incluyendo la celda de entrada o las que hacen referencia a la celda.
1. Right-click within the highlighted cells and select **[!UICONTROL Copy Requests]** from the shortcut menu.

   Tras seleccionar el área donde están ubicadas las solicitudes y las celdas de entrada, el sistema resalta las celdas que tienen estos elementos.
1. Seleccione una celda o un rango de celdas contiguas para rellenarlas con las solicitudes pegadas.

   Asegúrese de que la celda o el rango de celdas seleccionado no contenga otros datos o solicitudes.
1. Right-click the single cell or the top left-most cell in the range of cells and select **[!UICONTROL Paste Requests]**.

   Al pegar solicitudes que incluyen una celda de entrada, las opciones de [!UICONTROL Paste Requests] incluyen:

   **Usar celda de entrada absoluta:** Pega una copia de la solicitud o solicitudes y el formato asociado con las celdas seleccionadas en la zona de pegado que se resalte. La celda de entrada (la celda a la que se hace referencia en una de las solicitudes originales) no se pega. En su lugar, la celda de entrada permanece en la misma posición que antes.

   **Usar celda de entrada relativa:** Pega una copia de la solicitud o solicitudes y el formato asociado con las celdas seleccionadas en la zona de pegado que se haya resaltado, incluida una copia de la celda de entrada. La relación espacial de la solicitud o solicitudes con la celda de entrada es la misma que en la solicitud o solicitudes originales. Sin embargo, aunque las celdas recién pegadas ahora tienen una copia de las solicitudes, no tienen contenido inicialmente. Esto se debe a que, cuando se vuelve a crear la celda de entrada en la operación de pegado, no se asocia ningún dato a la celda de entrada. Para mostrar los datos de las solicitudes recién pegadas, debe introducir un valor en la celda de entrada y luego actualizar las solicitudes.
