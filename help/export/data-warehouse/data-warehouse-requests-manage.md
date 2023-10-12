---
description: El administrador de solicitudes permite ver, duplicar y volver a priorizar solicitudes.
title: Administrar solicitudes de Data Warehouse
feature: Data Warehouse
uuid: cdeb764f-56f9-43ec-9228-8ed5a2b58909
exl-id: a399d366-8402-4f4f-9b9f-14b218cd074a
source-git-commit: 48455ca071b2137d4d1d9f8d6d5dce77aee25b5e
workflow-type: tm+mt
source-wordcount: '927'
ht-degree: 16%

---

# Administrar solicitudes de Data Warehouse

{{release-limited-testing}}

>[!NOTE]
>
>Si su organización aún no tiene la nueva experiencia de Data Warehouse, que estará disponible próximamente para todos los clientes, utilice la información de [Administrar solicitudes de Data Warehouse (experiencia antigua)](#manage-data-warehouse-requests-old-experience) al final de esta página.


Puede administrar las solicitudes de Data Warehouse que haya realizado. Las secciones siguientes describen las actividades que puede realizar al administrar solicitudes. <!-- just those you have made? I think you can see other people's requests (you can filter by them). What can you do with other people's requests? Just view them?-->

## Ver solicitudes

1. En Adobe Analytics, seleccione [!UICONTROL **Herramientas**] > [!UICONTROL **Data Warehouse**].

   La página Data Warehouse muestra todas las solicitudes que ha realizado. <!-- just those you have made? -->Los datos se muestran en cada columna. Puede [configurar qué columnas](#configure-columns) son visibles.

   <!-- add screenshot of main page -->

<!-- describe columns? -->

1. (Opcional) Haga clic en el nombre de la solicitud para ver un cuadro de diálogo que muestre la siguiente información: <!-- Check this -->

   * Cuando una solicitud comenzó a procesarse

   * Velocidad limitada: Su organización tiene demasiadas solicitudes de Data Warehouse en ejecución. La solicitud se detiene hasta que se completen otras solicitudes de datos.

## Editar solicitudes

Tenga en cuenta lo siguiente al editar solicitudes:

* Solo se pueden editar las solicitudes configuradas para ejecutarse en una programación.

* No se pueden editar todos los campos asociados con la solicitud. Los campos que no se pueden editar aparecen atenuados.

Para editar una solicitud programada:

1. En Adobe Analytics, seleccione [!UICONTROL **Herramientas**] > [!UICONTROL **Data Warehouse**].

1. En la página Data Warehouse, seleccione la solicitud que desee editar.

   ![Administración de una solicitud](assets/dw-manage-request.png)

1. Seleccione [!UICONTROL **Editar**].

1. Edite la solicitud según desee. Las opciones de configuración atenuadas no se pueden editar.

   Para obtener información sobre cada opción de configuración, consulte [Creación de una solicitud de Data Warehouse](/help/export/data-warehouse/create-request/t-dw-create-request.md).

1. Seleccionar [!UICONTROL **Guardar cambios**].

## Ver el historial de una solicitud

Puede ver el historial de cualquier informe que se haya ejecutado.

1. En Adobe Analytics, seleccione [!UICONTROL **Herramientas**] > [!UICONTROL **Data Warehouse**].

1. En la página Data Warehouse, seleccione la solicitud cuyo historial desee ver.

   ![Administración de una solicitud](assets/dw-manage-request.png)

1. Seleccionar [!UICONTROL **Ver historial**].

   El [!UICONTROL **Ver solicitud de Data Warehouse**] Esta página muestra una lista de los envíos de informes individuales.

   ![Página historial de solicitudes](assets/dw-request-history.png)

1. Seleccione una entrega de informes y, a continuación, seleccione cualquiera de las siguientes opciones:

   | Opción | Función |
   |---------|----------|
   | [!UICONTROL **Detalles del destino**] | Muestra los detalles de cuenta y ubicación asociados con la solicitud. Esta es la cuenta y la ubicación configuradas anteriormente, tal como se describe en [Configuración del destino de un informe para una solicitud de Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md). |
   | [!UICONTROL **Cancelar informe**] | Cancela el informe. No se pueden cancelar los informes cuyo estado sea [!UICONTROL **Completado**] o [!UICONTROL **Cancelado**]. |
   | [!UICONTROL **Volver a ejecutar el informe**] | Ejecuta de nuevo el informe con los datos tal como estaban cuando se envió originalmente. Puede volver a ejecutar un informe que tenga cualquiera de los siguientes estados: [!UICONTROL **Cancelado**], [!UICONTROL **Completado**], [!UICONTROL **Error - Procesando**], o [!UICONTROL **Error: Error Al Enviar**]. |
   | [!UICONTROL **Volver a enviar el informe**] | Reenvía el archivo de informe generado anteriormente. Puede reenviar un informe que tenga cualquiera de los siguientes estados: [!UICONTROL **Completado**] o [!UICONTROL **Error: Error Al Enviar**]. |

## Copiar solicitudes

Al copiar una solicitud, todas las opciones de configuración se copian de la solicitud original.

1. En Adobe Analytics, seleccione [!UICONTROL **Herramientas**] > [!UICONTROL **Data Warehouse**].

1. En la página Data Warehouse, seleccione la solicitud que desee copiar.

   ![Administración de una solicitud](assets/dw-manage-request.png)

1. Seleccionar [!UICONTROL **Copiar**].

   Aparece la página Copiar solicitud de Data Warehouse. Todas las opciones de configuración se copian de la solicitud original.

1. Actualice las opciones de configuración asociadas con la solicitud.

   Para obtener información sobre cada opción de configuración, consulte [Creación de una solicitud de Data Warehouse](/help/export/data-warehouse/create-request/t-dw-create-request.md).

1. Seleccionar [!UICONTROL **Guardar cambios**].

## Cancelar solicitudes

Solo se pueden cancelar las solicitudes configuradas para ejecutarse en una programación.

Para cancelar una solicitud programada:

1. En Adobe Analytics, seleccione [!UICONTROL **Herramientas**] > [!UICONTROL **Data Warehouse**].

1. En la página Data Warehouse, seleccione la solicitud que desee editar.

   ![Administración de una solicitud](assets/dw-manage-request.png)

1. Seleccionar [!UICONTROL **Cancelar**].

   La solicitud ya no se ejecutará a la hora programada.

## Configuración de columnas

Puede configurar la información que se muestra para cada solicitud añadiendo o eliminando columnas.

1. Seleccione el **Configuración de columnas** en la parte superior derecha de la página de Data Warehouse.

   ![Configuración de columnas](assets/dw-configure-columns.png)

   Las columnas disponibles son las siguientes:

   | Columna disponible | Descripción |
   |---------|----------|
   | Nombre de la solicitud | El nombre de la persona que creó la solicitud. |
   | Grupo de informes | El grupo de informes asociado con la solicitud. |
   | Solicitado por | El usuario que creó la solicitud. |
   | Solicitar fecha | La fecha en la que se realizó la solicitud. |
   | Estado | Los siguientes estados están disponibles:<ul><li><p>**Completado**: la solicitud se ejecutó correctamente.</p></li><li><p>**Cancelado**: la solicitud fue cancelada por el usuario.</p></li><li><p>**Programado**: la solicitud está configurada para ejecutarse en una programación.</p></li><!-- Are there other statuses? Failed? --> |

   {style="table-layout:auto"}

1. Asegúrese de que todas las columnas que desee mostrar estén seleccionadas. Las columnas seleccionadas aparecen en la página de Data Warehouse y muestran la información relevante.

## Filtrado y ordenación de solicitudes

1. Seleccione el **Filtrar** en el carril izquierdo de la página de Data Warehouse.

   ![Filtrar solicitudes](assets/dw-filter.png)

1. Expanda el [!UICONTROL **Grupos de informes**], [!UICONTROL **Propietario**], o [!UICONTROL **Estado**] , luego seleccione cómo desea filtrar las solicitudes.

## Búsqueda de solicitudes

1. En el campo de búsqueda situado en la parte superior de la página de Data Warehouse, especifique el nombre de la solicitud que desea ver.

   Las solicitudes se filtran a medida que escribe.

## Administrar solicitudes de Data Warehouse (experiencia antigua)

>[!NOTE]
>
>La siguiente información solo se aplica si su organización aún no tiene la nueva experiencia de Data Warehouse, que estará disponible próximamente para todos los clientes de Analytics.


El administrador de solicitudes permite ver, duplicar y volver a priorizar solicitudes.

En Data Warehouse, seleccione la ficha **[!UICONTROL Administrador de solicitudes]**.

Al trabajar en esta ficha, puede

* Ver solicitudes de informes recientes por nombre de informe, segmento aplicado, solicitante, fecha y estado de la solicitud.
* Duplicar solicitudes. Haga clic en **[!UICONTROL Duplicar]** junto a la solicitud.

  >[!NOTE]
  >
  >Esta acción duplica solo la solicitud, no la programación ni los detalles de la entrega.

* Buscar informes por nombre de informe o por nombre de inicio de sesión del solicitante.
* Volver a priorizar los informes al arrastrarlos y colocarlos en una nueva ubicación dentro de la cola.
* Para ver cuándo comenzó a procesarse una solicitud, haga clic en el ID de una solicitud programada y revise el menú emergente que se abre.

Haga clic en un trabajo para ver solicitudes individuales para ese trabajo.

* Velocidad limitada: Su organización tiene demasiadas solicitudes de Data Warehouse en ejecución. La solicitud se detiene hasta que se completen otras solicitudes de datos.