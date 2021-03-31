---
description: Una solicitud de referencia utiliza los valores de las celdas como entrada para parámetros como, por ejemplo, un filtro de datos o un filtro relacional.
title: Copiar solicitudes de referencia
uuid: b6f64630-868f-455b-8682-471ff9fc596e
feature: Report Builder
role: Profesional empresarial, administrador
translation-type: tm+mt
source-git-commit: 894ee7a8f761f7aa2590e06708be82e7ecfa3f6d
workflow-type: tm+mt
source-wordcount: '546'
ht-degree: 99%

---


# Copiar solicitudes de referencia

Una solicitud de referencia utiliza los valores de las celdas como entrada para parámetros como, por ejemplo, un filtro de datos o un filtro relacional.

Para propagar o copiar y pegar las solicitudes de referencia en la hoja de cálculo, debe haber creado al menos una solicitud válida en la hoja de cálculo. Asimismo, los datos generados por la solicitud deben contener una celda cuyo valor sea dependiente de una solicitud en otra celda (utilizando un filtro coincidente o de desglose), o bien, dependiente de un filtro que adopte la entrada de los datos introducidos en una celda.

También se pueden crear solicitudes que hagan referencia a filtros de entrada desde solicitudes en diferentes hojas de cálculo, pero no en diferentes libros. Por ejemplo, una solicitud de la Hoja 2 puede utilizar un grupo de informes de una celda determinada de la Hoja 1 y un intervalo de fechas de una celda de una solicitud en la Hoja 2. La nueva salida se puede situar en cualquier hoja o en una nueva hoja del mismo libro. Cuando se pega una solicitud relativa, si un filtro de entrada reside en una hoja de cálculo distinta de la hoja en la que se sitúa el resultado de la solicitud copiada, el filtro se pega como filtro absoluto.

>[!NOTE]
>
>No se puede generar la misma solicitud en varias hojas de cálculo. Asimismo, el sistema no puede pegar algunas solicitudes copiadas en libros nuevos porque las solicitudes contienen filtros de entrada de otras hojas de cálculo. Los filtros de entrada incluyen grupos de informes de celdas, intervalos de fechas de celdas, filtros de celdas y otros parámetros relacionados.

**Para copiar solicitudes de referencia**

1. Seleccione las celdas que contengan las solicitudes que desee copiar, incluyendo la celda de entrada o las que hacen referencia a la celda.
1. Haga clic con el botón derecho en las celdas resaltadas y seleccione **[!UICONTROL Copiar solicitudes]** en el menú contextual.

   Tras seleccionar el área donde están ubicadas las solicitudes y las celdas de entrada, el sistema resalta las celdas que tienen estos elementos.
1. Seleccione una celda o un rango de celdas contiguas para rellenarlas con las solicitudes pegadas.

   Asegúrese de que la celda o el rango de celdas seleccionado no contenga otros datos o solicitudes.
1. Haga clic con el botón derecho en la celda o en la celda superior izquierda del rango de celdas y seleccione **[!UICONTROL Pegar solicitudes]**.

   Al pegar las solicitudes que incluyen una celda de entrada, entre las opciones de [!UICONTROL Pegar solicitudes] se encuentran:

   **Utilizar celda de entrada absoluta:** Pega una copia de la solicitud o solicitudes y el formato asociado con las celdas seleccionadas en la zona de pegado que se seleccione. La celda de entrada (a la que se hace referencia en una de las solicitudes originales) no se pega. En su lugar, la celda de entrada permanece en la misma posición que antes.

   **Utilizar celda de entrada relativa:** Pega una copia de la solicitud o solicitudes y el formato asociado con las celdas seleccionadas en la zona de pegado que se seleccione, incluyendo una copia de la celda de entrada. La relación espacial de la solicitud o solicitudes con la celda de entrada es la misma que en las solicitudes originales. Sin embargo, aunque las celdas recién pegadas cuentan ahora con una copia de las solicitudes, no tienen contenido al principio. Esto sucede porque cuando se vuelve a crear la celda de entrada en la operación de pegado, no se asocia ningún dato con la celda de entrada. Para mostrar los datos en las solicitudes recién pegadas, se debe introducir un valor en la celda de entrada y después actualizar las solicitudes.
