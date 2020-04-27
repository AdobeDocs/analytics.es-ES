---
description: Se puede copiar una solicitud simple en vez de una solicitud de referencia. Una solicitud simple no contiene referencias a otra solicitud ni al contenido de una celda.
title: Copiar solicitudes simples
topic: Report builder
uuid: ff20560a-01ee-47e7-8bd1-b73edb010456
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Copiar solicitudes simples

Se puede copiar una solicitud simple en vez de una solicitud de referencia. Una solicitud simple no contiene referencias a otra solicitud ni al contenido de una celda.

Una [solicitud de referencia](/help/analyze/report-builder/manage-requests/c-copy-requests/t-copy-referential-requests.md) utiliza los valores de las celdas como entrada para parámetros como, por ejemplo, un filtro de datos o un filtro relacional. Estos filtros utilizan la coincidencia o la tendencia y se basan en resultados de una solicitud anterior o en el contenido introducido por el usuario en una celda, denominada celda de entrada.
1. Cree una solicitud válida.
1. Haga clic con el botón derecho en una de las celdas donde se asigna la solicitud, o bien seleccione una región de celdas que contenga solicitudes.

   Sea coherente a la hora de seleccionar una celda desde la que copiar en el grupo de celdas que incluye la solicitud. La opción preferida es la celda superior y situada más a la izquierda del conjunto de celdas que incluye la solicitud, y trabajar de izquierda a derecha. Esto sucede porque la hoja de cálculo de Excel contiene cientos de columnas y miles de filas disponibles para la expansión hacia la derecha y hacia abajo. Si decide iniciar una copia de solicitud desde la celda inferior o situada más a la derecha en un conjunto de celdas asociadas con una solicitud, el sistema no permitirá pegar la solicitud si las celdas que se van a pegar sobrepasan el borde superior o izquierdo de la hoja de cálculo.
1. Select **[!UICONTROL Copy Request]**.
1. En otra parte de la hoja de cálculo, haga clic con el botón derecho en una celda vacía (una celda que no contenga solicitudes).

   Para evitar que se pierdan o se dañen las solicitudes creadas, no se permite pegar celdas que contengan solicitudes en celdas asignadas actualmente a solicitudes. If you copy or cut cells containing requests, the shortcut menu does not make the [!UICONTROL Paste Requests] option available when right clicking on cells (or the set of cells) containing requests. Se debe seleccionar una celda distinta como destino de la operación de pegado para que las solicitudes no se superpongan. Esto es así tanto si se selecciona una sola celda con una solicitud para pegar, como si se selecciona una región de celdas que contenga solicitudes.
1. Haga clic en **[!UICONTROL Paste Request]**.

   Una copia de la solicitud original se sitúa en la(s) celda(s), en una posición (o posiciones) relativa a la solicitud original.

   >[!NOTE]
   >
   >Solo se copian las solicitudes, no el contenido de las celdas. Si dispone de otra información que no se base en las solicitudes, pero que resulte relevante para comprender los datos mostrados en las celdas (por ejemplo, encabezados de columna de tabla o identificadores de fila), utilice los comandos estándar Copiar y Pegar de Excel.

   Debido a que Excel utiliza diferentes portapapeles para copiar el contenido de celdas y el contenido de solicitudes, puede copiar el contenido de celdas que no sean de solicitudes y posteriormente las solicitudes utilizando consecutivamente copiar/pegar y copiar solicitudes/pegar solicitudes. Sin embargo, si aplica formato a las solicitudes de la hoja de cálculo y después copia y pega, Report Builder reproducirá el formato original (p. ej., bordes, fuentes, etc.) en la zona de pegado.

   Si se modifica una solicitud copiada o cortada en el portapapeles antes de pegar la solicitud, la solicitud se elimina del portapapeles. Por lo tanto, para conservar la solicitud en su estado original, no la modifique entre el momento en que la copie y la pegue.
