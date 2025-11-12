---
description: Obtenga información sobre cómo ver, duplicar y volver a priorizar solicitudes de Data Warehouse.
title: Administrar solicitudes de Data Warehouse
feature: Data Warehouse
uuid: cdeb764f-56f9-43ec-9228-8ed5a2b58909
exl-id: a399d366-8402-4f4f-9b9f-14b218cd074a
source-git-commit: ca84a5f807545d7196e2e0e90d3209c32d3fd789
workflow-type: tm+mt
source-wordcount: '1148'
ht-degree: 4%

---

# Administrar solicitudes de Data Warehouse

Puede ver y administrar las solicitudes de Data Warehouse que haya realizado. Solo los administradores pueden ver y administrar las solicitudes realizadas por otros usuarios de su organización.

Las secciones siguientes describen las actividades que puede realizar al administrar solicitudes.

## Ver solicitudes

De manera predeterminada, solo puede ver las solicitudes que cree, a menos que los usuarios hayan elegido hacer sus solicitudes visibles para otros miembros de la organización (como se describe en [Configuración general de las solicitudes de Data Warehouse](/help/export/data-warehouse/create-request/dw-general-settings.md)). Los administradores del sistema pueden ver todas las solicitudes.

Para ver solicitudes de Data Warehouse:

1. En Adobe Analytics, seleccione [!UICONTROL **Herramientas**] > [!UICONTROL **Data Warehouse**].

   La página Data Warehouse muestra todas las solicitudes que ha realizado. Los datos se muestran en cada columna. Puede [configurar qué columnas](#configure-columns) son visibles.

   <!-- add screenshot of main page -->

<!-- describe columns? -->

1. (Opcional) Haga clic en el nombre de la solicitud para ver un cuadro de diálogo que muestre la siguiente información: <!-- Check this -->

   * Cuando una solicitud comenzó a procesarse

   * Velocidad limitada: Su organización tiene demasiadas solicitudes de Data Warehouse en ejecución. La solicitud se detiene hasta que se completen otras solicitudes de datos.

## Editar solicitudes

Tenga en cuenta lo siguiente al editar solicitudes:

* Solo se pueden editar las solicitudes configuradas para ejecutarse en una programación.

* No se pueden editar todos los campos asociados con la solicitud. Los campos que no se pueden editar aparecen atenuados.

* Los administradores que editan la solicitud de otro usuario deben elegir una cuenta y una ubicación nuevas a las que puedan acceder.

Para editar una solicitud programada:

1. En Adobe Analytics, seleccione [!UICONTROL **Herramientas**] > [!UICONTROL **Data Warehouse**].

1. En la página Data Warehouse, seleccione la solicitud que desee editar.

   ![Administrar una solicitud](assets/dw-manage-request.png)

1. Seleccione [!UICONTROL **Editar**].

1. Edite la solicitud según desee. Las opciones de configuración atenuadas no se pueden editar.

   Para obtener información sobre cada opción de configuración, consulte [Crear una solicitud de Data Warehouse](/help/export/data-warehouse/create-request/t-dw-create-request.md).

1. Seleccione [!UICONTROL **Guardar cambios**].

## Ver el historial de una solicitud

Puede ver el historial de cualquier solicitud de Data Warehouse que haya realizado.

1. En Adobe Analytics, seleccione [!UICONTROL **Herramientas**] > [!UICONTROL **Data Warehouse**].

1. En la página Data Warehouse, seleccione la solicitud cuyo historial desee ver.

   ![Administrar una solicitud](assets/dw-manage-request.png)

1. Seleccione [!UICONTROL **Ver historial**].

   La página [!UICONTROL **Ver solicitud de Data Warehouse**] muestra una lista de envíos de informes individuales asociados a la solicitud.

   Seleccione el icono **Configurar columna** ![Configurar icono de columna](assets/configure-column-icon.png) para ocultar columnas o mostrar columnas que no se muestran de forma predeterminada.

   ![Página de historial de solicitudes](assets/dw-request-history.png)

   Las columnas disponibles son las siguientes:

   | Columna | Descripción |
   |---------|----------|
   | [!UICONTROL **Fecha de creación**] | La fecha y la hora de creación del informe.<p>Esto se muestra en la zona horaria del usuario que inició la solicitud.</p> |
   | [!UICONTROL **Fecha de inicio**] | La fecha y la hora de inicio del informe.<p>Esto se muestra en la zona horaria del usuario que inició la solicitud.</p> |
   | [!UICONTROL **Fecha de finalización**] | La fecha y la hora en que se completó el informe.<p>Esto se muestra en la zona horaria del usuario que inició la solicitud.</p> |
   | [!UICONTROL **Fecha de actualización**] | La fecha y la hora de la última actualización del informe.<p>Esto se muestra en la zona horaria del usuario que inició la solicitud.</p> |
   | [!UICONTROL **Estado**] | El estado del envío del informe. Los estados posibles son:<ul><li>[!UICONTROL **Creado**]: el informe se creó, pero aún no se ha procesado.</li><li>[!UICONTROL **Pendiente**]: el informe está esperando a procesarse.</li><li>[!UICONTROL **Procesando**]: el informe se está procesando en este momento.</li><li>[!UICONTROL **Completado**]: el informe se completó y ya está disponible.</li><li>[!UICONTROL **Programado**]: el informe está programado pero aún no se ha iniciado.</li><li>[!UICONTROL **Cancelado**]: el usuario canceló el informe.</li><li>[!UICONTROL **Error - Procesando**:] El informe encontró un error y no se pudo procesar.</li><li>[!UICONTROL **Error - Error al enviar**]: el informe se generó correctamente pero no se pudo entregar. Comprueba la [configuración de tu destino](/help/export/data-warehouse/create-request/dw-request-report-destinations.md) y vuelve a enviar el informe.</li></ul>. |
   | [!UICONTROL **De**] | La fecha de inicio del lapso de tiempo general incluido en el informe.<p>Esto se muestra en la zona horaria del grupo de informes.</p> |
   | [!UICONTROL **Hasta**] | La fecha de finalización del lapso de tiempo general incluido en el informe. <p>Esto se muestra en la zona horaria del grupo de informes.</p> |
   | [!UICONTROL **ID de solicitud heredada**] | El ID que se utiliza para identificar un informe en la interfaz heredada de Data Warehouse. Este ID puede ser necesario al ponerse en contacto con el Servicio de atención al cliente de Adobe. |
   | [!UICONTROL **Id. de informe**] | Identificador que se utiliza para identificar un informe en la interfaz de Data Warehouse actual. Este ID puede ser necesario al ponerse en contacto con el Servicio de atención al cliente de Adobe. |


1. Seleccione una entrega de informes y, a continuación, seleccione cualquiera de las siguientes opciones:

   | Opción | Función |
   |---------|----------|
   | [!UICONTROL **Detalles del destino**] | Muestra los detalles de cuenta y ubicación asociados con la solicitud. Ésta es la cuenta y la ubicación configuradas anteriormente, tal como se describe en [Configuración de un destino de informe para una solicitud de Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md). |
   | [!UICONTROL **Cancelar informe**] | Cancela el informe. No puede cancelar informes que tengan un estado de [!UICONTROL **Completado**] o [!UICONTROL **Cancelado**]. |
   | [!UICONTROL **Volver a ejecutar informe**] | Ejecuta de nuevo el informe con los datos tal como estaban cuando se envió originalmente. Puede volver a ejecutar un informe que tenga cualquiera de los siguientes estados: [!UICONTROL **Cancelado**], [!UICONTROL **Completado**], [!UICONTROL **Error al procesar**] o [!UICONTROL **Error al no enviar**]. |
   | [!UICONTROL **Reenviar informe**] | Reenvía el archivo de informe generado anteriormente. Puede reenviar un informe que tenga cualquiera de los siguientes estados: [!UICONTROL **Completado**] o [!UICONTROL **Error - Error al enviar**]. |

## Copiar solicitudes

Al copiar una solicitud, todas las opciones de configuración se copian de la solicitud original.

1. En Adobe Analytics, seleccione [!UICONTROL **Herramientas**] > [!UICONTROL **Data Warehouse**].

1. En la página Data Warehouse, seleccione la solicitud que desee copiar.

   ![Administrar una solicitud](assets/dw-manage-request.png)

1. Seleccione [!UICONTROL **Copiar**].

   Se muestra la página Copiar solicitud de Data Warehouse. Todas las opciones de configuración se copian de la solicitud original.

1. Actualice las opciones de configuración asociadas con la solicitud.

   Para obtener información sobre cada opción de configuración, consulte [Crear una solicitud de Data Warehouse](/help/export/data-warehouse/create-request/t-dw-create-request.md).

1. Seleccione [!UICONTROL **Guardar cambios**].

## Cancelar solicitudes

Solo se pueden cancelar las solicitudes configuradas para ejecutarse en una programación.

Para cancelar una solicitud programada:

1. En Adobe Analytics, seleccione [!UICONTROL **Herramientas**] > [!UICONTROL **Data Warehouse**].

1. En la página Data Warehouse, seleccione la solicitud que desee editar.

   ![Administrar una solicitud](assets/dw-manage-request.png)

1. Seleccione [!UICONTROL **Cancelar**].

   La solicitud ya no se ejecutará a la hora programada.

## Configuración de columnas

Puede configurar la información que se muestra para cada solicitud añadiendo o eliminando columnas.

1. Seleccione el icono **Configure columns** en la esquina superior derecha de la página de Data Warehouse.

   ![Configurar columnas](assets/dw-configure-columns.png)

   Las columnas disponibles son las siguientes:

   | Columna disponible | Descripción |
   |---------|----------|
   | Nombre de la solicitud | El nombre de la persona que creó la solicitud. |
   | Grupo de informes | El grupo de informes asociado con la solicitud. |
   | Solicitado por | El usuario que creó la solicitud. |
   | Fecha de solicitud | La fecha en la que se realizó la solicitud. |
   | Estado | Los siguientes estados están disponibles:<ul><li><p>**Completada**: la solicitud se ejecutó correctamente.</p></li><li><p>**Cancelada**: el usuario canceló la solicitud.</p></li><li><p>**Programada**: la solicitud está configurada para ejecutarse en una programación.</p></li><li><p>**Error**: no se pudo completar la solicitud. Si la solicitud continúa fallando, póngase en contacto con Atención al cliente.</p></li></ul> |

   {style="table-layout:auto"}

1. Asegúrese de que todas las columnas que desee mostrar estén seleccionadas. Las columnas seleccionadas aparecen en la página de Data Warehouse y muestran la información relevante.

## Filtrado y ordenación de solicitudes

1. Seleccione el icono **Filter** en el carril izquierdo de la página de Data Warehouse.

   ![Filtrar solicitudes](assets/dw-filter.png)

1. Expanda las secciones [!UICONTROL **Grupos de informes**], [!UICONTROL **Propietario**] o [!UICONTROL **Estado**] y, a continuación, seleccione cómo desea filtrar las solicitudes.

## Búsqueda de solicitudes

1. En el campo de búsqueda que hay en la parte superior de la página de Data Warehouse, especifique el nombre de la solicitud que desea ver.

   Las solicitudes se filtran a medida que escribe.