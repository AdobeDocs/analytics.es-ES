---
description: Obtenga información sobre cómo agregar, eliminar o reemplazar métricas en una solicitud preexistente o en un grupo de solicitudes.
title: Cómo editar métricas en varias solicitudes
feature: Report Builder
role: User, Admin
exl-id: e537b67a-aa07-4acd-a476-7497426e2f7d
TQID: https://experienceleague.adobe.com/epK-BLSIpnZV1-0eqPxb2aGXSbon4Oc1mRDnRljpCxI
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 598
ht-degree: 6%

---

# Editar métricas en varias solicitudes

{{legacy-arb}}

Agregar, quitar o reemplazar métricas en una solicitud preexistente o en un grupo de solicitudes.

## Agregación de métricas {#section_3FBDA9668039404895059618D70FCBCD}

Cuando agregue métricas, tenga en cuenta las siguientes directrices:

* Las métricas solo se pueden agregar a solicitudes de diseño de tabla dinámica.
Si algunas de las solicitudes seleccionadas son diseños personalizados, no se pueden añadir métricas. Si el diseño es personalizado, Report Builder no sabe en qué parte de la hoja de cálculo colocar la nueva métrica.
* Si selecciona solamente solicitudes de diseño personalizado, la opción **[!UICONTROL Agregar métricas]** no estará disponible.
* Añadir métricas aumenta el tamaño de una solicitud y puede hacer que se superponga con otra solicitud. Asegúrese de que la solicitud tenga espacio suficiente alrededor para permitir la adición de métricas.
* Si la métrica agregada ya está presente en una de las solicitudes seleccionadas, no se agregará a esa solicitud.

Para agregar una o más métricas

1. Seleccione una o más solicitudes en Excel y haga clic con el botón derecho para seleccionar **[!UICONTROL Editar métricas]**. También puede hacer clic en **[!UICONTROL Administrar]** > **[!UICONTROL Editar varios]** > `<choose metric>` > **[!UICONTROL Editar grupo]** para seleccionar el grupo de solicitudes que quiere modificar.
1. Seleccione **[!UICONTROL Agregar métricas]** y elija las que le interesan.

   ![Captura de pantalla que muestra la opción Editar solicitud, Agregar métricas seleccionada.](assets/add_metric.png)

1. Actualice la solicitud para ver los datos reales. Los datos sin conexión se muestran hasta que se actualizan los datos.

## Reemplazo de métricas

Cuando reemplace métricas, tenga en cuenta las siguientes directrices:

* Solo se permiten 1:1 sustituciones. No se permiten 1:many o varios:1.
* Si la métrica seleccionada no está presente en una de las solicitudes seleccionadas, la solicitud se deja sin cambios.
* La nueva métrica se coloca en la misma ubicación que la métrica sustituida.

   * **En un diseño de tabla dinámica**, si una solicitud de diseño de tabla dinámica genera fechas, visitas, visitantes, visitantes únicos diarios y *visitantes* son reemplazados por *ingresos*, el diseño de solicitud actualizado será: fecha, visita, ingresos y únicos diarios.
   * **En un diseño personalizado**, si la métrica de *visitantes* se mostraba en la celda F11, el diseño de solicitud actualizado mostrará *ingresos* en la misma celda F11.

* Si a la métrica sustituida se le ha aplicado alguna operación (promedio, texto prependiente, texto pospendiente, micrográficos), estas operaciones también se aplicarán a la nueva métrica.

Para reemplazar una métrica

1. Seleccione una o más solicitudes en Excel y haga clic con el botón derecho para seleccionar **[!UICONTROL Editar métricas]**. También puede hacer clic en **[!UICONTROL Administrar]** > **[!UICONTROL Editar varias]** > **`<choose metric>`** > **[!UICONTROL Editar grupo]** para seleccionar el grupo de solicitudes que desea modificar.

1. Seleccione **[!UICONTROL Reemplazar métrica]**.

   ![Captura de pantalla de la pantalla Editar grupo con la opción Reemplazar métrica seleccionada.](assets/replace_metric.png)

1. Seleccione la métrica que desea reemplazar y la métrica de reemplazo.
1. Actualice la solicitud. Los datos sin conexión se muestran hasta que se actualizan los datos.

## Eliminación de métricas {#section_D3CD5BAC7670416593B633B2B8423C60}

Cuando elimine métricas, tenga en cuenta las siguientes directrices:

* Si alguna de las métricas que selecciona para eliminar no está presente en una de las solicitudes seleccionadas, la solicitud se deja sin cambios.
* En un diseño dinámico, la eliminación de una métrica hace que el diseño cambie para las métricas que se encuentran después de la métrica eliminada. Por ejemplo, si una solicitud de diseño dinámico genera fechas, visitas, visitantes y visitas únicas diarias, y elimina *visitas*, el diseño actualizado para la solicitud mostrará: fecha, visitantes y visitas únicas diarias.

Para eliminar métricas

1. Seleccione una o más solicitudes en Excel y haga clic con el botón derecho para seleccionar **[!UICONTROL Editar métricas]**. También puede hacer clic en **[!UICONTROL Administrar]** > **[!UICONTROL Editar varias]** > **`<choose metric>`** > **[!UICONTROL Editar grupo]** para seleccionar el grupo de solicitudes que desea modificar.

1. Seleccione **[!UICONTROL Quitar métricas]**.

   ![Captura de pantalla que muestra la opción Editar grupo y eliminar métricas seleccionada.](assets/remove_metric.png)

1. Seleccione una o varias métricas para eliminarlas de la solicitud.
1. Actualice la solicitud. Hasta que actualice, verá datos sin conexión.
