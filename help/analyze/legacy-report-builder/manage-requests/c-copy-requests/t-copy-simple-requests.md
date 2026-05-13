---
description: Aprenda a copiar una solicitud simple.
title: Cómo copiar solicitudes simples
uuid: ff20560a-01ee-47e7-8bd1-b73edb010456
feature: Report Builder
role: User, Admin
exl-id: ceed28d5-cb7f-4343-96fd-2ce09f5a3515
TQID: https://experienceleague.adobe.com/Zd6s6l-sW40WlEtk2Z8AFcNLkC-l4wxcmo67XajqAJs
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
source-wordcount: 527
ht-degree: 18%

---

# Copiar solicitudes simples

{{legacy-arb}}

Copie una solicitud simple en lugar de una solicitud de referencia. Una solicitud simple es aquella que no contiene referencias a otra solicitud ni al contenido de una celda.

Una [solicitud de referencia](/help/analyze/legacy-report-builder/manage-requests/c-copy-requests/t-copy-referential-requests.md) utiliza los valores de las celdas como entrada para parámetros como, por ejemplo, un filtro de datos o un filtro relacional. Estos filtros utilizan la coincidencia o la tendencia y se basan en resultados de una solicitud anterior o en el contenido introducido por el usuario en una celda, denominada celda de entrada.

Para copiar una solicitud simple

1. Cree una solicitud válida.
1. Haga clic con el botón derecho en una de las celdas donde se asigna la solicitud, o bien seleccione una región de celdas que contenga solicitudes.

   Sea coherente a la hora de elegir una celda desde la que copiar en el grupo de celdas que abarca la solicitud. La opción preferida es la celda superior izquierda del conjunto de celdas incluidas en la solicitud y trabajar de izquierda a derecha. Esto se debe a que la hoja de cálculo de Excel tiene cientos de columnas y miles de filas disponibles para expansiones hacia la derecha y hacia abajo. Si decide iniciar una copia de solicitud desde la celda situada más a la derecha o inferior de un conjunto de celdas asociadas a una solicitud, el sistema no le permitirá pegar la solicitud si las celdas que desea pegar se extienden más allá del borde izquierdo o superior de la hoja de cálculo.
1. Seleccione **[!UICONTROL Copiar solicitud]**.
1. En otra parte de la hoja de cálculo, haga clic con el botón derecho en una celda vacía (una celda que no contenga solicitudes).

   Para evitar que se pierdan o dañen solicitudes ya creadas, no se pueden pegar celdas que contengan solicitudes a celdas asignadas actualmente a solicitudes. Si copia o corta celdas que contienen solicitudes, el menú contextual no hace que la opción [!UICONTROL Pegar solicitudes] esté disponible al hacer clic con el botón secundario en las celdas (o en el conjunto de celdas) que contienen solicitudes. Debe seleccionar una celda diferente como destino de la operación de pegado para que las solicitudes no se superpongan. Esto se aplica tanto si selecciona una sola celda con una solicitud de pegado como si selecciona una región de celdas que contenga solicitudes.
1. Haga clic en **[!UICONTROL Pegar solicitud]**.

   Una copia de la solicitud original se sitúa en la(s) celda(s), en una posición (o posiciones) relativa a la solicitud original.

   >[!NOTE]
   >
   >Solo se copian las solicitudes, no el contenido de las celdas. Si dispone de otra información no basada en solicitudes, pero relevante para comprender los datos mostrados en las celdas (como encabezados de columna de tabla o identificadores de fila), utilice los comandos estándar de Excel Copiar y Pegar.

   Dado que Excel utiliza diferentes portapapeles para copiar el contenido de las celdas y copiar solicitudes, puede copiar tanto el contenido de las celdas que no sean de solicitud como las solicitudes a continuación realizando una operación de copia/pegado de solicitudes/pegado de copia y copia en serie. Sin embargo, si aplica formato a las solicitudes de la hoja de cálculo y después copia y pega, Report Builder reproduce el formato original (por ejemplo, bordes, fuentes, etc.) en la región de pegado.

   Si modifica una solicitud que ha copiado o cortado en el portapapeles antes de pegarla, se eliminará del portapapeles. Por lo tanto, para mantener la solicitud en su estado original, no la modifique entre el momento en que la copia y el momento en que la pega.
