---
description: Obtenga información sobre cómo copiar solicitudes de referencia.
title: Cómo copiar solicitudes de referencia
uuid: b6f64630-868f-455b-8682-471ff9fc596e
feature: Report Builder
role: User, Admin
exl-id: 3cd77325-7461-4345-a672-64c03ea1ae5b
source-git-commit: fb39f906d6c08713e4dc8211c917b2942502868e
workflow-type: tm+mt
source-wordcount: '530'
ht-degree: 80%

---

# Copiar solicitudes de referencia

Una solicitud de referencia utiliza los valores de las celdas como entrada para parámetros como, por ejemplo, un filtro de datos o un filtro relacional.

Para propagar o copiar y pegar solicitudes de referencia en la hoja de cálculo:
* Debe crear al menos una solicitud válida en la hoja de cálculo.
* Los datos producidos por la solicitud deben contener una celda cuyo valor dependa de una solicitud en otra celda (mediante un desglose o filtro coincidente) o de un filtro que tome datos introducidos en una celda.

También se pueden crear solicitudes que hagan referencia a filtros de entrada desde solicitudes en diferentes hojas de cálculo, pero no en diferentes libros. Por ejemplo, una solicitud de la Hoja 2 puede utilizar un grupo de informes de una celda determinada de la Hoja 1 y un intervalo de fechas de una celda de una solicitud en la Hoja 2. La nueva salida se puede situar en cualquier hoja o en una nueva hoja del mismo libro. Cuando se pega una solicitud relativa, si un filtro de entrada reside en una hoja de cálculo distinta de la hoja en la que se sitúa el resultado de la solicitud copiada, el filtro se pega como filtro absoluto.

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

   Al pegar las solicitudes que incluyen una celda de entrada, entre las opciones de [!UICONTROL Pegar solicitudes] se encuentran:

   **Utilizar celda de entrada absoluta:** Pega una copia de la solicitud o solicitudes y el formato asociado con las celdas seleccionadas en la zona de pegado que se seleccione. La celda de entrada (a la que se hace referencia en una de las solicitudes originales) no se pega. En su lugar, la celda de entrada permanece en la misma posición que antes.

   **Utilizar celda de entrada relativa:** Pega una copia de la solicitud o solicitudes y el formato asociado con las celdas seleccionadas en la zona de pegado que se seleccione, incluyendo una copia de la celda de entrada. La relación espacial de la solicitud o solicitudes con la celda de entrada es la misma que en las solicitudes originales. Sin embargo, aunque las celdas recién pegadas cuentan ahora con una copia de las solicitudes, no tienen contenido al principio. Esto sucede porque cuando se vuelve a crear la celda de entrada en la operación de pegado, no se asocia ningún dato con la celda de entrada. Para mostrar los datos en las solicitudes recién pegadas, se debe introducir un valor en la celda de entrada y después actualizar las solicitudes.
